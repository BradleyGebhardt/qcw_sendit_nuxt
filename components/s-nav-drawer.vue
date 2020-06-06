<template>
	<div :class="{ side: true, side__expanded: expanded }">
		<ul>
			<li>
				<nuxt-link to="/">
					Home
				</nuxt-link>
			</li>
		</ul>
	</div>
</template>

<script>
export default {
	name: 'NavDrawer',

	props: {
		expanded: {
			type: Boolean,
			required: true,
		},
	},
}
</script>

<style lang="scss" scoped>
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
