<script>
	import { T } from '@threlte/core';

	import {  Grid, interactivity, OrbitControls } from '@threlte/extras';
	import { Vector3 } from 'three';
	import { SheetObject } from '@threlte/theatre';
	import RotatableObject from './RotatableObject.svelte';
	import BaseBin from '../lib/models/base-bin.svelte';
	import CherryMx from '$lib/models/cherry-mx.svelte';
	import Lid2MxSwitches from '$lib/models/lid-2-mx-switches.svelte';
	import CapMxSwitch15x33 from '$lib/models/cap-mx-switch-15x33.svelte';
	import Baseplate from '$lib/models/baseplate.svelte';
	import BinEsp32 from '$lib/models/bin-esp32.svelte';
	import BaseBin2x1 from '$lib/models/base-bin-2x1.svelte';
	import BaseBin3u from '$lib/models/base-bin-3u.svelte';
	import LidSlider from '$lib/models/lid-slider.svelte';
	import Lid4MxSwitches from '$lib/models/lid-4-mx-switches.svelte';
	import LidRotaryEncoder from '$lib/models/lid-rotary-encoder.svelte';
	import CapMxSwitch15x15 from '$lib/models/cap-mx-switch-15x15.svelte';
	import CapSlider from '$lib/models/cap-slider.svelte';
	import CapRotaryEncoder from '$lib/models/cap-rotary-encoder.svelte';
	interactivity();
</script>


<T.PerspectiveCamera makeDefault position={[10, 10, 10]} near={0.1} far={100}   oncreate={(ref) => {
    ref.lookAt(0, 1, 0)
  }}>
    <!-- <OrbitControls  /> -->
</T.PerspectiveCamera>

<RotatableObject>

<T.Group position.y={-2} scale={0.6}>


	<SheetObject key="Baseplate">
		{#snippet children({ Transform })}
			<Transform>
				<Baseplate />
			</Transform>
		{/snippet}
	</SheetObject>

	<T.AmbientLight intensity={0.2} />

	<T.DirectionalLight intensity={1} position={[10, 10, -10]} />

		<SheetObject key="Box1">
			{#snippet children({ Transform })}
				<Transform>
                    <BaseBin />
				</Transform>
			{/snippet}
		</SheetObject>


		<SheetObject key="EspBox">
			{#snippet children({ Transform })}
				<Transform>
                    <BinEsp32 />
				</Transform>
			{/snippet}
		</SheetObject>


		<SheetObject key="Box2x1">
			{#snippet children({ Transform })}
				<Transform>
                    <BaseBin2x1 />
				</Transform>
			{/snippet}
		</SheetObject>


		<SheetObject key="SmallBox1">
			{#snippet children({ Transform })}
				<Transform>
                    <BaseBin3u />
				</Transform>
			{/snippet}
		</SheetObject>
		<SheetObject key="SmallBox2">
			{#snippet children({ Transform })}
				<Transform>
                    <BaseBin3u />
				</Transform>
			{/snippet}
		</SheetObject>


		<SheetObject key="LidSlider">
			{#snippet children({ Transform })}
				<Transform>
                    <LidSlider />
				</Transform>
			{/snippet}
		</SheetObject>



		<SheetObject key="Lid2MxSwitches">
			{#snippet children({ Transform })}
				<Transform>
                    <Lid2MxSwitches />
				</Transform>
			{/snippet}
		</SheetObject>


		<SheetObject key="Lid4MxSwitches">
			{#snippet children({ Transform })}
				<Transform>
                    <Lid4MxSwitches />
				</Transform>
			{/snippet}
		</SheetObject>


		<SheetObject key="LidRotaryEncoder1">
			{#snippet children({ Transform })}
				<Transform>
                    <LidRotaryEncoder />
				</Transform>
			{/snippet}
		</SheetObject>

		<SheetObject key="LidRotaryEncoder2">
			{#snippet children({ Transform })}
				<Transform>
                    <LidRotaryEncoder />
				</Transform>
			{/snippet}
		</SheetObject>

		<SheetObject key="CapMxSwitch15x33">
			{#snippet children({ Transform })}
				<Transform>
                    <CapMxSwitch15x33 />
				</Transform>
			{/snippet}
		</SheetObject>

		<SheetObject key="CapMxSwitch15x33-2">
			{#snippet children({ Transform })}
				<Transform>
                    <CapMxSwitch15x33 />
				</Transform>
			{/snippet}
		</SheetObject>

		<SheetObject key="CapMxSwitch15x15-1">
			{#snippet children({ Transform })}
				<Transform>
                    <CapMxSwitch15x15 />
				</Transform>
			{/snippet}
		</SheetObject>


		<SheetObject key="CapMxSwitch15x15-2">
			{#snippet children({ Transform })}
				<Transform>
                    <CapMxSwitch15x15 />
				</Transform>
			{/snippet}
		</SheetObject>


		<SheetObject key="CapMxSwitch15x15-3">
			{#snippet children({ Transform })}
				<Transform>
                    <CapMxSwitch15x15 />
				</Transform>
			{/snippet}
		</SheetObject>



		<SheetObject key="CapMxSwitch15x15-4">
			{#snippet children({ Transform })}
				<Transform>
                    <CapMxSwitch15x15 />
				</Transform>
			{/snippet}
		</SheetObject>


		<SheetObject key="CapSlider">
			{#snippet children({ Transform })}
				<Transform>
                    <CapSlider />
				</Transform>
			{/snippet}
		</SheetObject>


		<SheetObject key="CapRotaryEncoder1">
			{#snippet children({ Transform })}
				<Transform>
                    <CapRotaryEncoder />
				</Transform>
			{/snippet}
		</SheetObject>



		<SheetObject key="CapRotaryEncoder2">
			{#snippet children({ Transform })}
				<Transform>
                    <CapRotaryEncoder />
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