<template>
    <div>
        <header>
            <h1>Vue Blog</h1>
            <p v-on:click="showBlogPosts()">Read the Blog</p>
            <p v-on:click="showCreatePosts()">Create a Post</p>
        </header>
    </div>
</template>

<script>
export default {
    name: 'Header',
    data () {
        return {
            handlers: {
                showForm: this.showCreatePosts,
                showBlog: this.showBlogPosts
            }
        }
    },
    props: {
        blogEntry: Boolean,
    },
    methods: {
        showCreatePosts: function () {
             this.$emit('showCreatePosts', true)
        },
        showBlogPosts: function () {
             this.$emit('showBlogPosts', false)
        }
    }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
</style>