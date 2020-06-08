<template>
	<div class="wrapper">
		<h2>
			Would you like to register as a creator?
		</h2>

		<div class="actions">
			<!-- Continue -->
			<nuxt-link to="/creator/register">
				<button class="next">
					Yes
				</button>
			</nuxt-link>

			<!-- Not creator -->
			<nuxt-link to="/">
				<button class="cancel">
					Not now
				</button>
			</nuxt-link>
		</div>
	</div>
</template>

<script>
export default {}
</script>

<style lang="scss" scoped>
@import '~/assets/scss/vars.scss';

.wrapper {
	color: white;
	height: calc(100vh - 50px);
	display: flex;
	flex-direction: column;
	max-width: 500px;
	margin: 0 auto;

	h2 {
		margin-top: 20px;
		text-align: center;
	}

	.actions {
		margin-top: -20px;
		height: 100%;
		display: flex;
		flex-direction: column;
		justify-content: center;
		padding: 0 50px;

		button {
			padding: 10px 0;
			border: none;
			width: 100%;

			&:focus {
				outline: none;
			}

			&.next {
				margin-bottom: 50px;
			}
		}
	}
}

@media screen and (max-width: 768px) {
	.wrappepr {
	}
}
</style>
