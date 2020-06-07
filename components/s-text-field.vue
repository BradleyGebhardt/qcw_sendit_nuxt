<template>
	<div ref="wrapper" class="s-text-field">
		<input
			v-model="inputVal"
			name="input"
			:type="type"
			placeholder="placeholder"
			@input="emitValue"
		/>
		<label for="input">
			<span>{{ label }}</span>
		</label>
	</div>
</template>

<script>
export default {
	props: {
		value: {
			type: String,
			default: '',
		},

		width: {
			type: String,
			default: '100%',
		},

		type: {
			type: String,
			default: 'text',
		},

		label: {
			type: String,
			default: '',
		},

		placeholder: {
			type: String,
			default: 'yeet',
		},
	},

	data() {
		return {
			inputVal: '',
		}
	},

	created() {},

	mounted() {
		this.setWidth()
	},

	methods: {
		setModel() {
			this.inputVal = this.value
		},

		setWidth() {
			const width = Number(this.width)
			if (!isNaN(width)) this.$refs.wrapper.style.maxWidth = `${width}px`
			else this.$refs.wrapper.style.maxWidth = this.width
		},

		emitValue() {
			this.$emit('input', this.inputVal)
		},
	},
}
</script>

<style lang="scss" scoped>
@import '~/assets/scss/vars.scss';

.s-text-field {
	position: relative;
	height: 50px;
	width: 100%;
	color: white;

	input {
		width: 100%;
		height: 100%;
		border: none;
		padding-top: 20px;
		background-color: #24242d;
		color: white;
		padding-left: 2px;

		&::placeholder {
			color: #24242d;
		}

		&:focus {
			outline: none;
		}

		&:focus + label,
		&:not(:placeholder-shown) + label {
			&::after {
				transform: scaleX(1);
			}

			span {
				color: $green;
				transform: translateY(-150%);
			}
		}
	}

	label {
		position: absolute;
		bottom: 0;
		left: 0;
		width: 100%;
		height: 100%;
		pointer-events: none;
		border-bottom: 1px solid white;

		&::after {
			content: '';
			position: absolute;
			height: 100%;
			width: 100%;
			border-bottom: 3px solid #05a872;
			left: 0;
			bottom: -1px;
			transform: scaleX(0);
			transition: all 0.3s ease;
			transform-origin: 1;
		}

		span {
			position: absolute;
			bottom: 5px;
			left: 0px;
			transition: all 0.3s ease;
		}
	}
}
</style>
