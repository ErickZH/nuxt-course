<template lang="html">
    <div class="container">
        <header>
            <nuxt-link to="/">Regresar</nuxt-link>
            <h1 class="title">{{ album.title }}</h1>
        </header>
        <div class="columns is-multiline">
            <div class="column is-one-quarter" v-for="photo in photos" :key="photo.id">
                <img :src="photo.url" :alt="photo.title">
            </div>
        </div>
    </div>
</template>

<script>
import router from 'vue-router'

import axios from 'axios'

import env from '../../config/env'

export default {
    name: 'AlbumIndvPage',
    data () {
        return {
            album: {},
            photos: [],
        };
    },
    created () {
        axios.get(`${env.endpoint}/albums/${this.$route.params.id}`).then((response) => {
            this.album = response.data;
        });

        axios.get(`${env.endpoint}/albums/${this.$route.params.id}/photos`).then((response) => {
            this.photos = response.data;
        });
    }
}
</script>

<style lang="css">
.container {
    text-align: center;
}
header {
    margin-top: 100px;
    margin-bottom: 100px;
}
</style>
