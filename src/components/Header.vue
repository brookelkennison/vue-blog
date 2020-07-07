<template>
    <div>
        <header id="blog-header">
            <div>
                <h1>Vue Blog</h1>
            </div>
            <div id="menu-items">
                <p v-on:click="showBlogPosts()">Read the Blog</p>
                <p v-on:click="showCreatePosts()">Create a Post</p>
            </div>
        </header>
    </div>
</template>

<script>
export default {
    name: 'Header',
    data () {
        return {

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
        },
    }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
#blog-header {
    display: flex;
    flex-direction: row;
    align-items: center;
    justify-content: space-between;
}
#menu-items{
    display: flex;
    flex-direction: row;
}
p {
  margin: 10px;
  padding: 10px;
  border: 1px black solid;  
}
</style>