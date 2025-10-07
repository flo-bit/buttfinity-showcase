<script>
	import { Canvas } from '@threlte/core';
	import Scene from './Scene.svelte';

	import { Sheet, Sequence, Project, Studio } from '@threlte/theatre';
	import state from './state.json';
	import { dev } from '$app/environment';
</script>

<div class="absolute inset-0 h-full w-full">
	<Canvas>
		<Project config={{ state }} name="Project A">
			<Studio enabled={false} />
			<Sheet>
				<Sequence
					autoplay
					delay={1000}
					iterationCount={Infinity}
					range={[0, 6]}
					direction="alternate"
				>
					<Scene />
				</Sequence>
			</Sheet>
		</Project>
	</Canvas>
</div>
