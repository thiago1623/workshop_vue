<template>
	<b-navbar toggleable="lg" type="dark" variant="dark" class="px-3">
		<b-navbar-toggle target="nav-collapse"></b-navbar-toggle>
		
        <b-navbar-brand href="#" class="fw-bold">Mi app web</b-navbar-brand>

		<b-collapse id="nav-collapse" class="ml-auto" is-nav>
			<b-navbar-nav class="float-right">
				<b-nav-item href="#">Usuarios</b-nav-item>
                
				<b-nav-item-dropdown text="Idioma" right>
					<b-dropdown-item href="#">EN</b-dropdown-item>
					<b-dropdown-item href="#">ES</b-dropdown-item>
					<b-dropdown-item href="#">RU</b-dropdown-item>
					<b-dropdown-item href="#">FA</b-dropdown-item>
				</b-nav-item-dropdown>

				<b-nav-item-dropdown right>
					<!-- Using 'button-content' slot -->
					<template #button-content>
						Usuario
					</template>
					<b-dropdown-item href="#">Profile</b-dropdown-item>
					<b-dropdown-item href="#">Sign Out</b-dropdown-item>
				</b-nav-item-dropdown>
			</b-navbar-nav>
		</b-collapse>
	</b-navbar>
</template>

<script>
export default {
	name: "MyHeader",
};
</script>

<style lang="css" scoped>

</style>
