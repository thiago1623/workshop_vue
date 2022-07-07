<template>
<div>
<b-row v-if="!showContent && showLogin">
    <b-col md="12" class="d-flex justify-content-center mt-5">
        <b-card>
            <b-form>
                <b-form-group label="Nombre Completo" class="mt-3">
                    <b-form-text v-if="userData.title && userData.title.length > 150" text-variant="danger">
                        Solo puedes tener un maximo de 150 caracteres
                        <b-icon icon="info-circle"></b-icon>
                    </b-form-text>
                    <b-input maxlength="155" :state="userData.name && userData.name.length && userData.name.length <= 150 ? true : false" placeholder="Tu nombre" v-model="userData.name"></b-input>
                </b-form-group>

                <b-form-group label="Email" class="mt-3">
                    <b-input  type="email" :state="userData.email && userData.email.length ? true : false" placeholder="Tu Email" v-model="userData.email"></b-input>
                </b-form-group>

                <b-form-group label="Contraseña" class="mt-3">
                    <b-input type="password" :state="userData.password && userData.password.length ? true : false" placeholder="Contraseña" v-model="userData.password"></b-input>
                </b-form-group>

                <b-form-group label="url de tu foto" class="mt-3">
                    <b-input type="url" :state="userData.photo_url && userData.photo_url.length ? true : false" placeholder="URL de tu foto" v-model="userData.photo_url"></b-input>
                </b-form-group>

                <div class="text-center mt-5">
                    <b-button variant="dark" :disabled="!userData.name && !userData.email" @click="submitUserData()" class="px-4">Registrarse</b-button>
                </div>
            </b-form>
        </b-card>
    </b-col>
</b-row>
<b-row v-if="showContent && !showLogin">
    <b-col md="12" class="d-flex justify-content-center mt-5">
        <b-img  rounded="circle" alt="Circle image" style="width: 12rem; height: 12rem" :src="userData.photo_url"></b-img>
    </b-col>
    <b-col md="12" class="d-flex justify-content-center mt-5">
        <h1>¡Hola! {{userData.name}}</h1>
    </b-col>
    <b-col md="12" class="d-flex justify-content-center mt-5">
        <b-card>
            <h2 class="text-center">tus datos</h2>
            <b-form class="d-flex justify-content-center align-items-center">
                <b-form-group label="Nombre Completo" class="m-3">
                    <h3>{{userData.name}}</h3>
                </b-form-group>

                <b-form-group label="Email" class="m-3">
                    <h2>{{userData.email}}</h2>
                </b-form-group>
            </b-form>
        </b-card>
    </b-col>
    <b-col md="12" class="d-flex justify-content-center mt-5 mb-5" v-if="!hideTextArea">
        <b-card style="width: 30rem">
            <h2 class="text-center">Sobre ti</h2>
            <b-form class="d-flex justify-content-center align-items-center">
                <b-form-group  class="m-3">
                    <b-form-textarea   placeholder="Tu nombre" v-model="userData.about_you" style="width: 20rem"></b-form-textarea>
                    <div class="text-end mt-2">
                        <b-button variant="dark" class="px-4" @click="aboutYou(userData.about_you)">enviar</b-button>
                    </div>
                </b-form-group>
            </b-form>
        </b-card>
    </b-col>
</b-row>
<b-row v-if="contentAboutYou">
    <b-col md="12" class="d-flex justify-content-center mt-5 mb-5">
        <b-card class="text-center" style="min-width: 30rem; max-width: 50rem">
            <p>{{dataOnYou}}</p>
        </b-card>
    </b-col>
</b-row>
</div>
</template>

<script>
 export default {
   name: 'LoginAndProfilePage',
   data () {
     return {
        contentAboutYou: false,
        dataOnYou: null,
        hideTextArea: false,
        showContent: false,
        showLogin: true,
        userData: {
            name: null,
            email: null,
            password: null,
            photo_url: null,
            about_you: null,
        },
     }
   },
   props: [],
   components: {

   },
   created () {},
   mounted () {},
   methods: {
    submitUserData() {
        this.showContent = true
        this.showLogin = false
    },
    aboutYou(data) {
        this.dataOnYou = data
        if (this.dataOnYou.length) {
            this.contentAboutYou = true
            this.hideTextArea = true
        }
    }
   }
 }
</script>

<style lang="css" scoped>

</style>
