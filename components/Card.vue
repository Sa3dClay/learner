<template>
    <div v-if="post">
        <b-card
            class="mb-4"
            :header="post.title"
            header-class="text-center"
        >
            <b-img
                v-if="!show" fluid alt="nuxt js" class="mb-2"
                src="~/assets/img/undraw_nuxt_js_0fq9.svg"
            ></b-img>

            <b-card-text>
                {{ post.body }}
            </b-card-text>

            <b-button
                v-if="show"
                size="sm"
                variant="outline-primary"
                :to="{name: 'posts-id', params: {id: post.id}}"
                block
                pill
            >
                show
            </b-button>

            <b-button
                v-else
                size="sm"
                variant="outline-primary"
                to="/posts"
                block
                pill
            >
                back to posts
            </b-button>
        </b-card>
    </div>
</template>

<script>
export default {
    props: {
        post: Object,
        show: Boolean
    }
}
</script>
