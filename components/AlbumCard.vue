<template>
    <div>
        <h3>{{ album.title }}</h3>
        <a href="#">Ver album</a>
    </div>
</template>

<script>
export default {
    name: 'AlbumCard',
    props: {
        album: Object
    }
}
</script>

<style lang="css">
</style>
