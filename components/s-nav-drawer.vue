<template>
	<div>
		<div
			:class="{ overlay: true, overlay__expanded: expanded }"
			@click="emitModel()"
		></div>
		<div :class="{ side: true, side__expanded: expanded }">
			<ul>
				<li>
					<nuxt-link to="/">
						Home
					</nuxt-link>
				</li>
			</ul>
		</div>
	</div>
</template>

<script>
export default {
	name: 'NavDrawer',

	props: {
		value: {
			type: Boolean,
		},
	},

	data() {
		return {
			expanded: false,
		}
	},

	watch: {
		value: {
			handler() {
				this.expanded = this.value
			},
		},
	},

	created() {
		this.setExpanded()
	},

	methods: {
		setExpanded() {
			this.expanded = this.value
		},

		emitModel() {
			this.expanded = false
			this.$emit('input', this.expanded)
		},
	},
}
</script>

<style lang="scss" scoped>
.overlay {
	position: absolute;
	// display: block;
	// background-color: red;
	left: 0;
	top: 0;
	height: 100vh;

	&__expanded {
		right: 200px;
	}
}

.side {
	position: absolute;
	top: 0;
	right: 0;
	height: 100vh;
	background-color: #000000d2;
	color: white;
	width: 200px;
	transform: scaleX(0);
	transform-origin: 100% 0%;
	transition: all 0.3s ease;

	ul {
		list-style: none;
	}

	&__expanded {
		transform: scaleX(1);
	}
}
</style>
