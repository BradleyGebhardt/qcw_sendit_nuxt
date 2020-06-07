<template>
	<div class="wrapper">
		<form @submit.prevent>
			<!-- Header -->
			<h1>
				Login to Send it
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

			<button class="next">
				Next
			</button>
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

	.email {
		margin: 30px auto;
	}

	.pass {
		margin: 30px auto;
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
		background-color: $green;
		color: white;
		border: none;
		margin: 0 auto;
		cursor: pointer;

		&:focus {
			outline: none;
		}

		&:hover {
			background-color: $button-hover;
		}
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
