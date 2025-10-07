<script>
	import { T } from '@threlte/core';

	import { STLLoader } from 'three/examples/jsm/loaders/STLLoader.js';
	import { useLoader } from '@threlte/core';
	import { Edges, Grid, OrbitControls, Outlines } from '@threlte/extras';
	import { Vector3 } from 'three';
	import { SheetObject } from '@threlte/theatre';
	import { base } from '$app/paths';
	import RotatableObject from './RotatableObject.svelte';
	import BaseBin from '../lib/models/base-bin.svelte';

	const lid = useLoader(STLLoader).load(base + '/two-switches-lid.stl');

	const cap = useLoader(STLLoader).load(base + '/switch-cap-15x33.stl');

	const mxSwitch = useLoader(STLLoader).load(base + '/cherry-mx.stl');
</script>


<T.PerspectiveCamera makeDefault position={[10, 10, 10]} near={0.1} far={100}   oncreate={(ref) => {
    ref.lookAt(0, 1, 0)
  }}>
    <!-- <OrbitControls  /> -->
</T.PerspectiveCamera>

<RotatableObject>
<T.Group position.y={-2}>

	<T.AmbientLight intensity={0.2} />

	<T.DirectionalLight intensity={1} position={[10, 10, -10]} />

		<SheetObject key="Box">
			{#snippet children({ Transform })}
				<Transform>
                    <BaseBin />
				</Transform>
			{/snippet}
		</SheetObject>

		<SheetObject key="Lid">
			{#snippet children({ Transform })}
				<Transform>
					{#if $lid}
						<T.Mesh scale={0.1} rotation.x={-Math.PI / 2}>
							<T is={$lid} />
							<Edges color="white" thresholdAngle={30} scale={1.001} />
							<T.MeshToonMaterial color="#313131" />
							<Outlines color="white" width={2} angle={1} />
						</T.Mesh>
					{/if}
				</Transform>
			{/snippet}
		</SheetObject>

		<SheetObject key="MXSwitch1">
			{#snippet children({ Transform })}
				<Transform>
					{#if $mxSwitch}
						<T.Mesh scale={0.1} rotation.x={-Math.PI / 2}>
							<T is={$mxSwitch} />
							<Edges color="white" thresholdAngle={4} scale={1.001} />
							<T.MeshBasicMaterial color="#000" />
							<Outlines color="white" width={2} angle={1} />
						</T.Mesh>
					{/if}
				</Transform>
			{/snippet}
		</SheetObject>

		<SheetObject key="Cap1">
			{#snippet children({ Transform })}
				<Transform>
					{#if $cap}
						<T.Mesh scale={0.1} rotation.x={-Math.PI / 2}>
							<T is={$cap} />
							<T.MeshToonMaterial color="#550000" />
							<Outlines color="#ff2222" width={2} angle={1} />
						</T.Mesh>
					{/if}
				</Transform>
			{/snippet}
		</SheetObject>

		<SheetObject key="MXSwitch2">
			{#snippet children({ Transform })}
				<Transform>
					{#if $mxSwitch}
						<T.Mesh scale={0.1} rotation.x={-Math.PI / 2}>
							<T is={$mxSwitch} />
							<Edges color="white" thresholdAngle={4} scale={1.001} />
							<T.MeshBasicMaterial color="#000" />
							<Outlines color="white" width={2} angle={1} />
						</T.Mesh>
					{/if}
				</Transform>
			{/snippet}
		</SheetObject>

		<SheetObject key="Cap2">
			{#snippet children({ Transform })}
				<Transform>
					{#if $cap}
						<T.Mesh scale={0.1} rotation.x={-Math.PI / 2}>
							<T is={$cap} />
							<T.MeshToonMaterial color="#550000" />
							<Outlines color="#ff2222" width={2} angle={1} />
						</T.Mesh>
					{/if}
				</Transform>
			{/snippet}
		</SheetObject>

		<Grid
			cellSize={2.1}
			cellColor="white"
			sectionThickness={0}
			fadeDistance={10}
			fadeOrigin={new Vector3(0, 0, 0)}
		/>
</T.Group>


</RotatableObject>