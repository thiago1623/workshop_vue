<template>
    <b-card class="mb-3" :title="userInfo.name">
        <b-card-text>
            Correo: {{ userInfo.email }}
        </b-card-text>
        <b-card-text>
            Teléfono: {{ userInfo.phone }}
        </b-card-text>
        <b-card-text>
            Página web: <a href="#">{{ userInfo.website }}</a>
        </b-card-text>

        <div>
            <b-button variant="outline-secondary" size="sm" class="me-2" @click="$emit('edit')">
                <b-icon icon="pencil"></b-icon>
            </b-button>

            <b-button variant="outline-secondary" size="sm" class="me-2" @click="$emit('see')">
                <b-icon icon="eye"></b-icon>
            </b-button>

            <b-button variant="outline-secondary" size="sm" @click="$emit('delete')">
                <b-icon icon="trash"></b-icon>
            </b-button>
        </div>
    </b-card>
</template>

<script>
    export default {
        props: {
            userInfo: {
                type: Object,
                required: true
            },
        },
    }
</script>

<style lang="scss" scoped>

</style>