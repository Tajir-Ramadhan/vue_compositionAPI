<template>
    <div class="post">
        <h3>{{ post.title }}</h3>
        <p>{{ snippet }}</p>
    </div>
</template>

<script>
import { computed } from 'vue';

export default {
    props: ['post'],
    setup(props) {
        const snippet = computed( () => {

            return props.post.body.substr(0,200) + '...'
        })
        console.log(props.post)

        return { snippet }
    }
}

</script>

<style >

</style>