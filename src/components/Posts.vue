<template>
    <div>
        <h2>Blog Posts</h2>
        <br>
        <div v-if="blogPosts.length == 0">
            <h3>There are currently no blog posts to show. Please add a post to view it!</h3>
        </div>
        <div v-for="blogPost in blogPosts" :key='blogPost.id'>
            <hr>
            <h3>Title: {{blogPost.title}}</h3>
            <p>Content: {{blogPost.content}}</p>
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
    methods: {
        deletePost(){
            console.log(this.blogPosts)
        }
    }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
</style>