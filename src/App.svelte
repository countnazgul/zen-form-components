<script>
	import {
		ZenBox,
		ZenBoxGroup,
		ZenRadio,
	} from './components/components.module.js';

	let state = true;
	let label = 'Whatever here';

	let radioSelected = 'Radio Value 2';
	let radioOptions = ['Radio Value 1', 'Radio Value 2', 'Radio Value 3'];

	let radioSelected1 = 'Radio Value 2';
	let radioOptions1 = ['Radio Value 1', 'Radio Value 2', 'Radio Value 3'];

	let checkSelected = ['Check Value 1', 'Check Value 3'];
	let checkOptions = ['Check Value 1', 'Check Value 2', 'Check Value 3'];

	let codeExample = `import { ZenBox, ZenBoxGroup, ZenRadio} from './components/components.module.js';

<ZenBox bind:state {label} />

<ZenRadio options={radioOptions} vertical={true} bind:selected={radioSelected} />

<ZenRadio options={radioOptions} vertical={true} bind:selected={radioSelected} />
`;
</script>

<style>
	.grid {
		display: grid;
		grid-template-columns: minmax(min-content, 300px) auto;
	}

	.grid {
		display: grid;
		grid-template-rows: auto auto auto;
		gap: 10px;
	}

	pre {
		background-color: lightgray;
		font-size: 16px;
	}
</style>

<div>
	<div class="main-grid">
		<div>
			Checkbox:
			<div class="grid">
				<ZenBox bind:state {label} />
				{state}
			</div>
		</div>
		<div>
			Checkbox group:
			<div class="grid">
				<ZenBoxGroup
					options={checkOptions}
					bind:selected={checkSelected}
					vertical={true} />
				{checkSelected}
			</div>
		</div>
		<div>
			Radio group:
			<div class="grid">
				<ZenRadio
					options={radioOptions}
					vertical={true}
					bind:selected={radioSelected} />
				{radioSelected}
			</div>
		</div>

		<!-- <div>
			Radio group1:
			<div class="grid">
				<ZenRadio
					options={radioOptions1}
					vertical={true}
					bind:selected={radioSelected1} />
				{radioSelected1}
			</div>
		</div>		 -->
	</div>

	<pre>{codeExample}</pre>
</div>
