<template>
    <div>
        <b-row>
            <b-col sm="6" md="4" class="bg-light text-center"><h2 class="mt-3">My app</h2></b-col>
            <b-col sm="6" md="8" class="m-0 p-0 d-flex justify-content-end">
                <b-navbar type="light" class="m-0 p-0 d-flex justify-content-center" variant="light" style="height: 12vh; width: 100%">
                    <b-navbar-nav class="mt-2">
                        <b-nav-item href="#" class="h4 me-3">Inicio</b-nav-item>

                        <!-- Navbar dropdowns -->
                        <b-nav-item-dropdown text="Lenguaje" class="h5" right>
                            <b-dropdown-item href="#">EN</b-dropdown-item>
                            <b-dropdown-item href="#">ES</b-dropdown-item>
                            <b-dropdown-item href="#">RU</b-dropdown-item>
                            <b-dropdown-item href="#">FA</b-dropdown-item>
                        </b-nav-item-dropdown>

                        <b-nav-item-dropdown text="User" class="h5 ms-3" right>
                            <b-dropdown-item href="#">cuenta</b-dropdown-item>
                            <b-dropdown-item href="#">configuración</b-dropdown-item>
                        </b-nav-item-dropdown>

                        <b-nav-item href="#" class="h5 ms-3">Sobre nosotros</b-nav-item>
                    </b-navbar-nav>
                </b-navbar>
            </b-col>
        </b-row>
    </div>
</template>

<script>
export default {
    name: 'MyHeader',
    data() {
        return {

        }
    },
    props: [],
    components: {

    },
    created() { },
    mounted() { },
    methods: {

    }
}
</script>

<style lang="css" scoped>
</style>
