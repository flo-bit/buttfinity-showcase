<script>
	import { Canvas } from '@threlte/core';
	import Scene from './Scene.svelte';

	import { Sheet, Sequence, Project, Studio } from '@threlte/theatre';
	import state from './state.json';
	import { dev } from '$app/environment';
</script>

<div class="px-8 py-16 pointer-events-none z-10">
	<p class="mt-8 text-lg font-black text-rose-500 uppercase sm:text-xl">Buttfinity</p>

	<h1 class="mt-3 text-5xl font-thin tracking-tight text-pretty text-white lowercase sm:text-7xl">
		Buttons + Gridfinity
	</h1>

	<dl class="mt-10 max-w-xl space-y-8 border-l border-zinc-900 text-base/7 text-zinc-400">
		<div class="ml-8 pt-4">
			<dt class="relative pl-9 font-semibold tracking-tighter text-white uppercase">
				<svg
					xmlns="http://www.w3.org/2000/svg"
					data-slot="icon"
					aria-hidden="true"
					class="absolute top-1 left-1 size-5 text-rose-500"
					viewBox="0 0 24 24"
					><path
						fill="none"
						stroke="currentColor"
						stroke-linecap="round"
						stroke-linejoin="round"
						stroke-width="1"
						d="M9 17.25v1.007a3 3 0 0 1-.879 2.122L7.5 21h9l-.621-.621A3 3 0 0 1 15 18.257V17.25m6-12V15a2.25 2.25 0 0 1-2.25 2.25H5.25A2.25 2.25 0 0 1 3 15V5.25m18 0A2.25 2.25 0 0 0 18.75 3H5.25A2.25 2.25 0 0 0 3 5.25m18 0V12a2.25 2.25 0 0 1-2.25 2.25H5.25A2.25 2.25 0 0 1 3 12V5.25"
					/></svg
				>
				Macropad
			</dt>
			<dd class="pt-2 pl-9 font-light lowercase">Control your computer.</dd>
		</div>
		<div class="-ml-4 border-t border-zinc-900"></div>
		<div class="ml-8">
			<dt class="relative pl-9 font-semibold tracking-tighter text-white uppercase">
				<svg
					xmlns="http://www.w3.org/2000/svg"
					data-slot="icon"
					aria-hidden="true"
					class="absolute top-1 left-1 size-5 text-rose-500"
					viewBox="0 0 24 24"
					><path
						fill="none"
						stroke="currentColor"
						stroke-linecap="round"
						stroke-linejoin="round"
						stroke-width="1"
						d="M12 18v-5.25m0 0a6 6 0 0 0 1.5-.189m-1.5.189a6 6 0 0 1-1.5-.189m3.75 7.478a12.1 12.1 0 0 1-4.5 0m3.75 2.383a14.4 14.4 0 0 1-3 0M14.25 18v-.192c0-.983.658-1.823 1.508-2.316a7.5 7.5 0 1 0-7.517 0c.85.493 1.509 1.333 1.509 2.316V18"
					/></svg
				>
				Smart home
			</dt>
			<dd class="pt-2 pl-9 font-light lowercase">Automate your home.</dd>
		</div>
		<div class="-ml-4 border-t border-zinc-900"></div>
		<div class="ml-8 pb-4">
			<dt class="relative pl-9 font-semibold tracking-tighter text-white uppercase">
				<svg
					xmlns="http://www.w3.org/2000/svg"
					data-slot="icon"
					aria-hidden="true"
					class="absolute top-1 left-1 size-5 text-rose-500"
					viewBox="0 0 24 24"
					><path
						fill="none"
						stroke="currentColor"
						stroke-linecap="round"
						stroke-linejoin="round"
						stroke-width="1"
						d="m9 9l10.5-3m0 6.553v3.75a2.25 2.25 0 0 1-1.632 2.163l-1.32.377a1.803 1.803 0 1 1-.99-3.467l2.31-.66a2.25 2.25 0 0 0 1.632-2.163m0 0V2.25L9 5.25v10.303m0 0v3.75a2.25 2.25 0 0 1-1.632 2.163l-1.32.377a1.803 1.803 0 0 1-.99-3.467l2.31-.66A2.25 2.25 0 0 0 9 15.553"
					/></svg
				>
				Music
			</dt>
			<dd class="pt-2 pl-9 font-light lowercase">Use as a MIDI controller.</dd>
		</div>

        <div class="lg:ml-9 absolute lg:relative bottom-2 left-2 pointer-events-auto z-20">
		<a
			href="https://github.com/flo-bit/buttfinity"
			target="_blank"
			class="pointer-events-auto transform-all inline-flex touch-manipulation items-center justify-center gap-2 rounded-2xl border border-rose-500/15 bg-rose-200/50 px-3 py-1.5 text-sm font-medium whitespace-nowrap text-rose-950 shadow-lg inset-shadow-sm shadow-rose-500/5 inset-shadow-rose-700/5 outline-offset-2 backdrop-blur-md backdrop-brightness-105 duration-800 hover:scale-101 hover:cursor-pointer hover:bg-rose-200/60 hover:duration-300 focus-visible:scale-101 focus-visible:outline-2 focus-visible:outline-rose-500 active:scale-98 active:shadow-md active:duration-100 disabled:pointer-events-none disabled:opacity-60 disabled:shadow-md disabled:hover:scale-100 motion-safe:transition-all motion-safe:focus-visible:transition-transform dark:border-rose-500/15 dark:bg-rose-950/20 dark:text-rose-400 dark:shadow-rose-500/2 dark:inset-shadow-rose-500/2 dark:hover:bg-rose-950/25 [&_svg]:pointer-events-none [&_svg]:size-4 [&_svg]:shrink-0"
		>
			Build it!
		</a>
    </div>
	</dl>
</div>

<div class="absolute inset-0 h-full w-full">
	<Canvas>
		<Project config={{ state }} name="Plate A">
			<Studio enabled={false} />
			<Sheet>
				<Sequence autoplay delay={1000}>
					<Scene />
				</Sequence>
			</Sheet>
		</Project>
	</Canvas>
</div>
