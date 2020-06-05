<template>
    <div>
        <h2>Blog Posts</h2>
        <br>
        <div v-if="blogPosts.length == 0">
            <h3>There are currently no blog posts to show. Please add a post to view it!</h3>
        </div>
        <div v-for="posts in blogPosts" :key="posts">
            <hr>
            <h3>Title: {{posts.title}}</h3>
            <p>Content: {{posts.content}}</p>
            <hr>
        </div>
    </div>
</template>

<script>
export default {
    name: 'Posts',
    data () {
        return {
            blogLength: false,
        }
    },
    props: {
       blogPosts: Array,
    },
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
</style>