<template>
	<div>
		<main-header></main-header>
		<!-- Explicar problema común al declarar nombre existente header -->

		<div class="container py-4">
			<b-row class="mb-4">
				<b-col>
					<h2 class="fw-bold">Listado de usuarios</h2>
				</b-col>

				<b-col>
					<b-input type="search" v-model="filterText" placeholder="Escribe para buscar" debounce="300"></b-input>
				</b-col>
			</b-row>

			<b-row>
				<b-col md="4" v-for="user in filteredUsers" :key="user.id">
					<user-card :user-info="user" @see="showUserDetails(user, false)" @edit="showUserDetails(user, true)" @delete="showDeleteConfirmation()"></user-card>
				</b-col>
			</b-row>

            <b-row class="py-5" v-if="!users.length || !filteredUsers.length">
                <h3 class="text-center">
                    {{ !users.length ?  "Cargando usuarios..." : "No existen usuarios para tu búsqueda" }}
                </h3>
            </b-row>
		</div>

		<custom-footer></custom-footer>

		<b-modal id="user-modal" hide-header centered scrollable>
			<div v-if="selectedUser">
				<h3>{{ selectedUser.name }}</h3>
				<pre>
                {{ selectedUser }}
            </pre
				>
			</div>
		</b-modal>
	</div>
</template>

<script>
import MainHeader from "../components/Header.vue";
import CustomFooter from "../components/Footer.vue";
import UserCard from "../components/UserCard.vue";

export default {
	name: "IndexPage",
	components: {
		MainHeader,
		CustomFooter,
		UserCard,
	},
	data() {
		return {
			editable: false,
            filterText: null,
			selectedUser: null,
			users: [],
		};
	},
    computed: {
		// Reacción ante cualquier cambio en el documento
        filteredUsers() {
            if (this.filterText) {
                return this.users.filter(user => user.name.toLowerCase().includes(this.filterText.toLowerCase()))
            } else {
                return this.users
            }
        }
    },
	methods: {
		getUsers() {
			this.axios
				.get("https://jsonplaceholder.typicode.com/users")
				.then((res) => { // Luego de que tenga la información
					this.users = res.data;
				})
				.catch((err) => {
					console.log("🚀 ~ file: Index.vue ~ line 30 ~ getUsers ~ err", err);
				});
		},
		showUserDetails(user, isEditable) {
			this.selectedUser = user;
			this.editable = isEditable;
			this.$bvModal.show("user-modal");
		},
		showDeleteConfirmation() {},
	},
	mounted() {
		this.getUsers();
	},
};
</script>

<style lang="scss" scoped></style>
