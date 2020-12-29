<template>
    <b-row align-h="center">
        <b-col cols="10" md="8" lg="6">
            <Card :post="post" :show="false" />
        </b-col>
    </b-row>
</template>

<script>
import axios from 'axios'
import Card from '@/components/Card'

export default {
    data() {
        return {
            post: {}
        }
    },

    components: {
        Card
    },

    async asyncData({params}) {
        let {data} = await axios.get(`https://jsonplaceholder.typicode.com/posts/${params.id}`)
        return {post: data}
    },

    head() {
        return {
            title: this.post.title
        }
    }
}
</script>
