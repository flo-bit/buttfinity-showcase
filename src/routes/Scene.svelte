<script>
	import { T, useThrelte } from '@threlte/core';

	import { Grid, interactivity, OrbitControls } from '@threlte/extras';
	import { Fog, Vector3 } from 'three';
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
	import { onMount } from 'svelte';
	import RotaryEncoder from '$lib/models/rotary-encoder.svelte';
	import Slider from '$lib/models/slider.svelte';
	import Buttplug from '$lib/models/buttplug.svelte';
	interactivity();

	let distance = $state(1);
	let down = $state(-3);
	let side = $state(0);

	function onResize() {
		if (window.innerWidth < 1000) {
			distance = 2;
			down = -8;
			side = 0;

		} else {
			distance = 1;
			down = -3;
			side = -2;
		}
		scene.fog = new Fog(0x000000, 20 * distance, 26 * distance);
	}

	const { scene } = useThrelte();

	onMount(() => {
		onResize();

		window.addEventListener('resize', onResize);

		scene.fog = new Fog(0x000000, 20 * distance, 26 * distance);

		return () => {
			window.removeEventListener('resize', onResize);
		};
	});
</script>

<T.PerspectiveCamera
	makeDefault
	position={[10 * distance, 5 * distance, -10 * distance]}
	near={0.1}
	far={100}
	oncreate={(ref) => {
		ref.lookAt(0, 1, 0);
	}}
>
	<!-- <OrbitControls /> -->
</T.PerspectiveCamera>

<T.Group position.y={down} position.x={side}>
	<SheetObject key="All">
		{#snippet children({ Transform })}
			<Transform>
				<RotatableObject>
					<T.Group scale={0.5}>
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
									<CapMxSwitch15x33 color="#b91c1c" />
								</Transform>
							{/snippet}
						</SheetObject>

						<SheetObject key="CapMxSwitch15x33-2">
							{#snippet children({ Transform })}
								<Transform>
									<CapMxSwitch15x33 color="#b45309" />
								</Transform>
							{/snippet}
						</SheetObject>

						<SheetObject key="CapMxSwitch15x15-1">
							{#snippet children({ Transform })}
								<Transform>
									<CapMxSwitch15x15 color="#be123c" />
								</Transform>
							{/snippet}
						</SheetObject>

						<SheetObject key="CapMxSwitch15x15-2">
							{#snippet children({ Transform })}
								<Transform>
									<CapMxSwitch15x15 color="#be185d" />
								</Transform>
							{/snippet}
						</SheetObject>

						<SheetObject key="CapMxSwitch15x15-3">
							{#snippet children({ Transform })}
								<Transform>
									<CapMxSwitch15x15 color="#a21caf" />
								</Transform>
							{/snippet}
						</SheetObject>

						<SheetObject key="CapMxSwitch15x15-4">
							{#snippet children({ Transform })}
								<Transform>
									<CapMxSwitch15x15 color="#7e22ce" />
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
									<CapRotaryEncoder color="#4d7c0f" accentColor="#84cc16" />
								</Transform>
							{/snippet}
						</SheetObject>

						<SheetObject key="CapRotaryEncoder2">
							{#snippet children({ Transform })}
								<Transform>
									<CapRotaryEncoder color="#047857" accentColor="#10b981" />
								</Transform>
							{/snippet}
						</SheetObject>

						<SheetObject key="RotaryEncoder">
							{#snippet children({ Transform })}
								<Transform>
									<RotaryEncoder />
								</Transform>
							{/snippet}
						</SheetObject>
						<SheetObject key="RotaryEncoder2">
							{#snippet children({ Transform })}
								<Transform>
									<RotaryEncoder />
								</Transform>
							{/snippet}
						</SheetObject>

						<SheetObject key="Slider">
							{#snippet children({ Transform, Sync })}
								<Transform>
									<Slider>
										<Sync visible />
									</Slider>
								</Transform>
							{/snippet}
						</SheetObject>

						<SheetObject key="MxKey1">
							{#snippet children({ Transform })}
								<Transform>
									<CherryMx />
								</Transform>
							{/snippet}
						</SheetObject>

						<SheetObject key="MxKey2">
							{#snippet children({ Transform })}
								<Transform>
									<CherryMx />
								</Transform>
							{/snippet}
						</SheetObject>

						<SheetObject key="MxKey3">
							{#snippet children({ Transform })}
								<Transform>
									<CherryMx />
								</Transform>
							{/snippet}
						</SheetObject>
						<SheetObject key="MxKey4">
							{#snippet children({ Transform })}
								<Transform>
									<CherryMx />
								</Transform>
							{/snippet}
						</SheetObject>
						<SheetObject key="MxKey5">
							{#snippet children({ Transform })}
								<Transform>
									<CherryMx />
								</Transform>
							{/snippet}
						</SheetObject>
						<SheetObject key="MxKey6">
							{#snippet children({ Transform })}
								<Transform>
									<CherryMx />
								</Transform>
							{/snippet}
						</SheetObject>

						{#each Array(34) as _, i}
							<SheetObject key="Buttplug{i}">
								{#snippet children({ Transform })}
									<Transform>
										<Buttplug />
									</Transform>
								{/snippet}
							</SheetObject>
						{/each}

						<Grid
							cellSize={2.1}
							cellColor="white"
							sectionThickness={0}
							fadeDistance={10}
							fadeOrigin={new Vector3(0, 0, 0)}
						/>
					</T.Group>
				</RotatableObject>
			</Transform>
		{/snippet}
	</SheetObject>
</T.Group>
