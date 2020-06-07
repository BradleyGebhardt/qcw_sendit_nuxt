<template>
	<div>
		<div
			:class="{ overlay: true, overlay__expanded: expanded }"
			@click="emitModel()"
		></div>
		<div :class="{ side: true, side__expanded: expanded }">
			<h1>Navigation</h1>
			<hr class="nav" />
			<ul>
				<li>
					<nuxt-link to="/">
						Home
					</nuxt-link>
				</li>
				<li>
					<nuxt-link to="/login">
						Login
					</nuxt-link>
				</li>
				<li>
					<nuxt-link to="/signup">
						Signup
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
$side-width: 250px;

.overlay {
	position: absolute;
	// display: block;
	// background-color: red;
	left: 0;
	top: 0;
	height: 100vh;

	&__expanded {
		right: $side-width;
	}
}

.side {
	position: absolute;
	top: 0;
	right: 0;
	height: 100vh;
	background-color: #000000d2;
	color: white;
	width: $side-width;
	transform: scaleX(0);
	transform-origin: 100% 0%;
	transition: all 0.3s ease;

	h1 {
		font-weight: 100;
		text-align: center;
	}

	ul {
		list-style: none;
		padding-top: 60px;

		li {
			text-align: center;
			color: white;
		}

		li:nth-of-type(even) {
			margin: 15px 0;
		}
	}

	&__expanded {
		transform: scaleX(1);
	}
}
</style>
