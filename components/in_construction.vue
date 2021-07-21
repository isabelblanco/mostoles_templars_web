<template>
    <div>
        <v-row>
        <v-col cols="12" align="center">
        <p class="title text-h4 text-sm-h1">
            {{ this.content.TEXTOS.IN_CONSTRUCTION }}
        </p>
        </v-col>
    </v-row>
    <v-row>
        <v-col cols="12" align="center">
        <img :src="this.content.IMAGENES.logo_templars" alt="caballero templario">
        </v-col>
    </v-row>
    </div>
</template>

<script>
    export default {
        components: {
            name: 'in_construction'
        },
        props: {
            'content' : {
                type: Object,
                default: {}
            }
        }
    }
</script>

<style scoped>
  .title {
    color: #08a0c7;
    margin-top: 10%;
  }

  img {
    width: 100%;
  }
</style>