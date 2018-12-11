<template lang="html">
    <h1>Hola mundo</h1>
</template>

<script>
import axios from 'axios'

import env from '../config/env'

export default {
    created () {
        axios.get(`${env.endpoint}/albums`).then((response) => {
            console.log(response.data);
        })
    }
}
</script>
