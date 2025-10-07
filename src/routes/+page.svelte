<script>
	import { Canvas } from '@threlte/core';
	import Scene from './Scene.svelte';

	import { Sheet, Sequence, Project, Studio } from '@threlte/theatre';
	import state from './state.json';
	import { dev } from '$app/environment';
	import { onMount } from 'svelte';

	onMount(() => {
		window.addEventListener('keydown', (e) => {
			if (e.key === ' ') {
				e.preventDefault();
				window.location.reload();
			}
		});
	});
</script>

<div class="absolute inset-0 h-full w-full">
	<Canvas>
		<Project config={{ state }} name="Project A">
			<Studio enabled={false} />
			<Sheet>
				<Sequence autoplay delay={1000}>
					<Scene />
				</Sequence>
			</Sheet>
		</Project>
	</Canvas>
</div>
