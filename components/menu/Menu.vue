<template>
	<div>
		<div class="navbar-item">
			<div class="field is-grouped">
				<p class="control">
					<a v-if="!isUserLoggedIn" class="button" @click="showSignupModal">
						<span class="icon">
							<i class="fa fa-user-plus"></i>
						</span>
						<span>{{ signupLabel }}</span>
					</a>
				</p>
				<p class="control">
					<a v-if="!isUserLoggedIn" class="button" @click="showLoginModal">
						<span class="icon">
							<i class="fa fa-user"></i>
						</span>
						<span>{{ loginLabel }}</span>
					</a>
				</p>
			</div>
		</div>
		<div v-if="isUserLoggedIn" class="navbar-item has-dropdown is-hoverable">
			<a class="navbar-link">
			Bienvenido {{ getUserName }}
			</a>
			<div class="navbar-dropdown is-boxed">
				
				<a class="navbar-item" @click="logout">
					{{ logoutLabel }}
				</a>
			</div>
		</div>
	</div>
</template>

<script>
export default {
	name: 'VmMenu',
	data () {
		return {
			wishlistLabel: 'Favoritos',
			logoutLabel: 'Salir',
			loginLabel: 'Ingresar',
			signupLabel: 'Registro'
		}
	},

	computed: {
		isUserLoggedIn () {
			return this.$store.getters.isUserLoggedIn;
		},
		getUserName () {
			let name = this.$store.getters.getUserName;
			
			if (name === '') {
				return 'Usuario';
			} else {
				return name;
			}
		}
	},

	methods: {
		logout () {
			this.$store.commit('isUserLoggedIn', false);
			this.$store.commit('isUserSignedUp', false);
			this.$store.commit('removeProductsFromFavourite');

			// redirect to homepage
			this.$router.push({ name: 'index' });
		},
		showLoginModal () {
			this.$store.commit('showLoginModal', true);
		},
		showSignupModal () {
			this.$store.commit('showSignupModal', true);
		}
	}
}
</script>

