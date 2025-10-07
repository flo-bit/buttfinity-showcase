<script>
	import { T } from '@threlte/core';

	import {  Grid } from '@threlte/extras';
	import { Vector3 } from 'three';
	import { SheetObject } from '@threlte/theatre';
	import RotatableObject from './RotatableObject.svelte';
	import BaseBin from '../lib/models/base-bin.svelte';
	import CherryMx from '$lib/models/cherry-mx.svelte';
	import Lid2MxSwitches from '$lib/models/lid-2-mx-switches.svelte';
	import CapMxSwitch15x33 from '$lib/models/cap-mx-switch-15x33.svelte';
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
					<Lid2MxSwitches />
				</Transform>
			{/snippet}
		</SheetObject>

		<SheetObject key="MXSwitch1">
			{#snippet children({ Transform })}
				<Transform>
					<CherryMx />
				</Transform>
			{/snippet}
		</SheetObject>

		<SheetObject key="Cap1">
			{#snippet children({ Transform })}
				<Transform>
					<CapMxSwitch15x33 />
				</Transform>
			{/snippet}
		</SheetObject>

		<SheetObject key="MXSwitch2">
			{#snippet children({ Transform })}
				<Transform>
					<CherryMx />
				</Transform>
			{/snippet}
		</SheetObject>

		<SheetObject key="Cap2">
			{#snippet children({ Transform })}
				<Transform>
					<CapMxSwitch15x33 />
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