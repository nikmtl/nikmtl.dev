<script lang="ts">
	import Globe from '@lucide/svelte/icons/globe';
	import Mail from '@lucide/svelte/icons/mail';
</script>

<svelte:head>
	<title>Dominik Mitzel — Under Construction</title>
	<meta
		name="description"
		content="nikmtl.dev is under construction. Applied Computer Science student building clean, scalable digital products."
	/>
</svelte:head>

<div class="flex flex-1 flex-col items-center justify-center px-5 py-10 text-center">
	<div
		class="eyebrow motion-fade animate-rise-1 mb-[22px] font-mono text-xs tracking-[0.15em] text-fg-dim uppercase opacity-0"
	>
		status: building
	</div>

	<h1
		class="motion-fade animate-rise-2 m-0 max-w-[16ch] text-[clamp(2.6rem,9vw,7.5rem)] leading-[0.96] font-extrabold tracking-[-0.03em] opacity-0"
	>
		Under<br />constr<em class="text-accent not-italic">u</em>ction.
	</h1>

	<p
		class="motion-fade animate-rise-3 mt-6 max-w-[46ch] text-[clamp(0.95rem,1.3vw,1.15rem)] leading-relaxed text-fg-dim opacity-0"
	>
		<strong class="font-semibold text-fg">Dominik Mitzel</strong> — Applied Computer Science student based
		in Germany, currently rebuilding this corner of the internet. Clean, scalable things are on the
		way.
	</p>

	<div class="motion-fade animate-rise-4 mt-11 flex flex-wrap justify-center gap-3.5 opacity-0">
		<a
			href="https://github.com/nikmtl"
			target="_blank"
			rel="noopener"
			class="inline-flex items-center gap-2 rounded-full border border-accent bg-accent px-5 py-[11px] font-mono text-sm font-semibold text-bg transition-all duration-200 hover:-translate-y-0.5 hover:bg-accent-hover"
		>
			<svg viewBox="0 0 16 16" fill="currentColor" class="h-[15px] w-[15px]"
				><path
					d="M8 0C3.58 0 0 3.58 0 8c0 3.54 2.29 6.53 5.47 7.59.4.07.55-.17.55-.38 0-.19-.01-.82-.01-1.49-2.01.37-2.53-.49-2.69-.94-.09-.23-.48-.94-.82-1.13-.28-.15-.68-.52-.01-.53.63-.01 1.08.58 1.23.82.72 1.21 1.87.87 2.33.66.07-.52.28-.87.51-1.07-1.78-.2-3.64-.89-3.64-3.95 0-.87.31-1.59.82-2.15-.08-.2-.36-1.02.08-2.12 0 0 .67-.21 2.2.82.64-.18 1.32-.27 2-.27.68 0 1.36.09 2 .27 1.53-1.04 2.2-.82 2.2-.82.44 1.1.16 1.92.08 2.12.51.56.82 1.27.82 2.15 0 3.07-1.87 3.75-3.65 3.95.29.25.54.73.54 1.48 0 1.07-.01 1.93-.01 2.2 0 .21.15.46.55.38A8.01 8.01 0 0 0 16 8c0-4.42-3.58-8-8-8Z"
				/></svg
			>
			github
		</a>
		<a
			href="https://nikmtl.dev"
			target="_blank"
			rel="noopener"
			class="inline-flex items-center gap-2 rounded-full border border-white/8 bg-bg-soft px-5 py-[11px] font-mono text-sm text-fg transition-all duration-200 hover:-translate-y-0.5 hover:border-accent hover:bg-[#161616]"
		>
			<Globe class="h-[15px] w-[15px]" strokeWidth={1.3} />
			nikmtl.dev
		</a>
		<a
			href="https://www.linkedin.com/in/dominik-mitzel"
			target="_blank"
			rel="noopener"
			class="inline-flex items-center gap-2 rounded-full border border-white/8 bg-bg-soft px-5 py-[11px] font-mono text-sm text-fg transition-all duration-200 hover:-translate-y-0.5 hover:border-accent hover:bg-[#161616]"
		>
			<svg viewBox="0 0 16 16" fill="currentColor" class="h-[15px] w-[15px]"
				><path
					d="M14.5 14.5v-5.3c0-2.7-1.4-4-3.4-4-1.5 0-2.2.9-2.6 1.5V5.3H5.6c.1 1.1 0 9.2 0 9.2h2.9V9.6c0-.3 0-.5.1-.7.2-.5.7-1.1 1.6-1.1 1.1 0 1.6.9 1.6 2.1v4.6h2.7ZM2.4 4C3.4 4 4 3.3 4 2.5 4 1.7 3.4 1 2.4 1 1.5 1 .9 1.7.9 2.5c0 .8.6 1.5 1.5 1.5Zm1.4 10.5V5.3H1v9.2h2.8Z"
				/></svg
			>
			linkedin
		</a>
		<a
			href="mailto:contact@mtzel.com"
			class="inline-flex items-center gap-2 rounded-full border border-white/8 bg-bg-soft px-5 py-[11px] font-mono text-sm text-fg transition-all duration-200 hover:-translate-y-0.5 hover:border-accent hover:bg-[#161616]"
		>
			<Mail class="h-[15px] w-[15px]" strokeWidth={1.3} />
			email
		</a>
	</div>
</div>
