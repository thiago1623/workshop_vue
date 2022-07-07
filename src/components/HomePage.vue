<template>
<div>
    <b-row>
        <b-col md="12">
            <Header/>
        </b-col>
    </b-row>
    <b-row>
        <b-col md="12">
            <LoginAndProfilePage/>
        </b-col>
    </b-row>
</div>
</template>

<script>
import Header from './Header.vue'
import LoginAndProfilePage from './LoginAndProfile.vue'
export default {
    name: "HomePage",
    data() {
        return {};
    },
    props: [],
    components: {
        Header,
        LoginAndProfilePage
    },
    created() {},
    mounted() {},
    methods: {},
};
</script>

<style lang="css" scoped>
</style>
