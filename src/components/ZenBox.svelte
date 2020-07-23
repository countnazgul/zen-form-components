<script>
	export let state = false;
	export let label = '';
</script>

<style>
	input {
		vertical-align: -2px;
	}

	@keyframes ripple {
		0% {
			box-shadow: 0px 0px 0px 1px rgba(0, 0, 0, 0);
		}
		50% {
			box-shadow: 0px 0px 0px 15px rgba(0, 0, 0, 0.1);
		}
		100% {
			box-shadow: 0px 0px 0px 15px rgba(0, 0, 0, 0);
		}
	}
	.md-check {
		margin: 16px 0;
	}

	.md-check input[type='checkbox'] {
		display: none;
	}

	.md-check input[type='checkbox']:checked + label:before {
		border-color: #337ab7;
		animation: ripple 0.2s linear forwards;
	}

	.md-check input[type='checkbox']:checked + label:after {
		transform: scale(1);
	}
	.md-check label {
		display: inline-block;
		min-height: 20px;
		position: relative;
		padding: 0 30px;
		margin-bottom: 0;
		cursor: pointer;
		vertical-align: bottom;
	}
	.md-check label:before,
	.md-check label:after {
		position: absolute;
		content: '';

		transition: all 0.3s ease;
		transition-property: transform, border-color;
	}
	.md-check label:before {
		left: 0;
		top: 0;
		width: 20px;
		height: 20px;
		border: 2px solid rgba(0, 0, 0, 0.54);
	}
	.md-check label:after {
		top: 5px;
		left: 5px;
		width: 10px;
		height: 10px;
		transform: scale(0);
		background: #337ab7;
	}

	*,
	*:before,
	*:after {
		box-sizing: border-box;
	}
</style>

<label>
	<div class="md-check">
		<input type="checkbox" bind:checked={state} {label} id={label} />
		<label for={label}>{label}</label>
	</div>
</label>
