<template>
    <div>
        <h2 class="text-center">API with Vue/Nuxt</h2>

        <hr>

        <b-row v-if="posts">
            <b-col
                cols="12" md="6" lg="4"
                v-for="post in posts"
                :key="post.id"
            >

                <!-- <b-jumbotron>
                    <h3>{{ post.title }}</h3>
                    
                    <p class="px-4">{{ post.body }}</p>
                </b-jumbotron> -->

                <Card :post="post" :show="show" />

            </b-col>
        </b-row>
    </div>
</template>

<!--
<script>
import axios from 'axios'

export default {
    data() {
        return {
            posts: []
        }
    },

    mounted() {
        axios.get('https://jsonplaceholder.typicode.com/posts')
            .then(response => {
                this.posts = response.data
            })
            .catch(error => {
                console.log(error)
            })
    }
}
</script>
-->

<script>
import axios from 'axios'
import Card from '@/components/Card'
import {mapGetters} from 'vuex'

export default {
    data() {
        return {
            show: true
        }
    },

    components: {
        Card
    },

    computed: {
        ...mapGetters([
            'posts'
        ])
    },

    async fetch({store}) {
        let {data} = await axios.get('https://jsonplaceholder.typicode.com/posts')
        
        store.dispatch('setPosts', data)
    },

    head: {
        title: 'posts'
    }
}
</script>
