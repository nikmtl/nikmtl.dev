<script lang="ts">
	import './layout.css';
	import favicon from '#lib/assets/favicon.svg';
	import avatar from '#lib/assets/avatar.jpg';
	import Heart from '@lucide/svelte/icons/heart';
	import { onMount } from 'svelte';
	import type { LayoutProps } from './$types';

	let { children }: LayoutProps = $props();

	let glowEl: HTMLDivElement | undefined = $state();

	onMount(() => {
		const reduced = window.matchMedia('(prefers-reduced-motion: reduce)').matches;
		if (reduced || !glowEl) return;

		let tx = window.innerWidth / 2;
		let ty = window.innerHeight / 2;
		let x = tx;
		let y = ty;

		const onMove = (e: PointerEvent) => {
			tx = e.clientX;
			ty = e.clientY;
		};
		window.addEventListener('pointermove', onMove);

		let frame: number;
		const loop = () => {
			x += (tx - x) * 0.08;
			y += (ty - y) * 0.08;
			if (glowEl) glowEl.style.transform = `translate(${x - 300}px, ${y - 300}px)`;
			frame = requestAnimationFrame(loop);
		};
		frame = requestAnimationFrame(loop);

		return () => {
			window.removeEventListener('pointermove', onMove);
			cancelAnimationFrame(frame);
		};
	});
</script>

<svelte:head>
	<link rel="icon" href={favicon} />
</svelte:head>

<div class="bg-vignette pointer-events-none fixed inset-0 z-0"></div>
<div
	bind:this={glowEl}
	class="motion-glow pointer-events-none fixed top-0 left-0 z-[1] h-[600px] w-[600px] rounded-full bg-glow will-change-transform"
></div>
<div class="bg-grain pointer-events-none fixed inset-0 z-[2] mix-blend-overlay opacity-[0.06]"></div>

<nav
	class="relative z-[3] flex items-center justify-between px-5 py-7 font-mono text-[13px] tracking-wide text-fg-dim sm:px-16"
>
	<a href="/" class="flex items-center gap-2.5 text-fg">
		<img
			src={avatar}
			alt="Dominik Mitzel"
			class="block h-[26px] w-[26px] rounded-full border border-white/8"
			width="26"
			height="26"
		/>
		<span>nikmtl.dev</span>
	</a>
	<div class="flex items-center gap-2">
		<span class="motion-pulse animate-pulse-dot h-[7px] w-[7px] rounded-full bg-accent shadow-[0_0_10px_#4da3ff]"
		></span>
		<span>building — 2026</span>
	</div>
</nav>

<main class="relative z-[3] flex flex-1 flex-col">
	{@render children()}
</main>

<footer
	class="relative z-[3] flex flex-col items-center justify-between gap-2 px-5 pt-6 pb-8 text-center font-mono text-xs tracking-wide text-fg-dim sm:flex-row sm:px-16 sm:text-left"
>
	<span class="inline-flex items-center gap-1.5">
		built with <Heart class="h-[13px] w-[13px] fill-accent text-accent" /> using SvelteKit
	</span>
	<div class="flex items-center gap-4">
		<a
			href="/privacy"
			class="border-b border-transparent text-fg-dim no-underline transition-colors duration-200 hover:border-white/8 hover:text-fg"
		>
			Privacy
		</a>
		<a
			href="/legal"
			class="border-b border-transparent text-fg-dim no-underline transition-colors duration-200 hover:border-white/8 hover:text-fg"
		>
			Legal
		</a>
	</div>
</footer>
