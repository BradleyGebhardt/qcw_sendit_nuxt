<template>
	<div class="wrapper">
		<form @submit.prevent>
			<!-- Header -->
			<h1>
				Create an account with Send it
			</h1>

			<!-- Email -->
			<s-text-field
				v-model="user.email"
				label="Email"
				type="email"
				width="500"
				class="email"
			/>

			<!-- Password -->
			<s-text-field
				v-model="user.password"
				label="Password"
				type="password"
				width="500"
				class="pass"
			/>

			<!-- Password Confirmation -->
			<s-text-field
				v-model="confPass"
				label="Confirm password"
				type="password"
				width="500"
				class="pass"
			/>

			<nuxt-link to="/creator/inquire">
				<button class="next">
					Signup
				</button>
			</nuxt-link>
		</form>
	</div>
</template>

<script>
export default {
	name: 'SignupPage',

	data() {
		return {
			user: {
				email: '',
				password: '',
			},
			confPass: '',
		}
	},
}
</script>

<style lang="scss" scoped>
@import '~/assets/scss/vars.scss';

.wrapper {
	display: flex;
	flex-direction: column;
	align-content: center;
	justify-content: center;
	padding: 0 50px;
	height: calc(100% - 50px);

	h1 {
		text-align: center;
		color: white;
	}

	.s-text-field {
		margin: 40px auto;
	}

	form {
		padding: 20px;
		background-color: $card-light;
		box-shadow: 5px 5px 20px 2px black;
		width: 100%;
		max-width: 600px;
		margin: 0 auto;
	}

	button.next {
		display: block;
		width: 90%;
		padding: 10px 0;
		margin: 0 auto;
	}
}

@media screen and (max-width: 768px) {
	.wrapper {
		background-color: $card;
		height: 100%;
		margin: -50px 0;
		padding: 0;
		// padding-top: 50px;

		form {
			padding-top: 50px;
			box-shadow: none;
			background-color: #ffffff00;
		}

		button.next {
			width: 100%;
		}
	}
}
</style>
