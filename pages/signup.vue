<template>
	<div class="wrapper">
		<form @submit.prevent>
			<s-text-field v-model="user.email" label="Email" width="400" />
			{{ user.email }}
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
			},
		}
	},
}
</script>

<style lang="scss" scoped>
// @media screen and (max-width: 768px) {
// 	.wrapper {
// 		background-color: #564d65;
// 		height: 100%;
// 		margin: -50px 0;
// 		padding-top: 50px;

// 		form {
// 			padding-top: 50px;
// 		}
// 	}
// }
</style>
