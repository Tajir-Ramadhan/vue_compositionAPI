<template>
    <div class="post-list">
        <div v-for="post in posts" :id="post">
            <singlePost :post="post" />
        </div>
    </div>
</template>

<script >

import { onMounted } from 'vue';
import singlePost from './singlePost.vue'

export default{
    props: ['posts'],
    components: {singlePost},
    setup(){
        onMounted( () => {
            console.log("component Mounted")
        })
    }
}

</script>

<style >

</style>