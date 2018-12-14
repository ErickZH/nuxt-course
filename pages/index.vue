<template lang="html">
    <div class="container">
        <h1 class="title">Albums</h1>
        <div class="columns is-multiline">
            <AlbumCard v-for="album in albums" :key="album.id" :album="album"/>
        </div>
    </div>
</template>

<script>
import axios from 'axios'

import env from '../config/env'

import AlbumCard from '../components/AlbumCard'

export default {
    data () {
        return {
            albums: []
        };
    },
    created () {
        axios.get(`${env.endpoint}/albums`).then((response) => {
            this.albums = response.data;
        })
    },
    components: {
        AlbumCard
    }
}
</script>
