<template>
    <div>
        <h2>Create a Post</h2>
        <p>Title:</p>
        <input type="text" v-model.lazy='title'>
        <p>Content:</p>
        <textarea name="" id="" cols="30" rows="10" v-model='content'></textarea>
        <button @click='postEntry()'>Post</button>
    </div>
</template>

<script>
export default {
    name: 'Blog',
    data () {
        return {
            title: '',
            content: '',
        }
    },  
    props: {
            blogPosts: Array,
    },
    methods: {
        postEntry () {
            this.blogPosts.push({'title' : this.title, 'content': this.content});
            this.$emit('postEntry', this.blogPosts)
            // Make into a modal & add option to view
            alert('Your post has been submitted\nTitle: ' + this.title + '\nContent: ' + this.content);
            this.title = '';
            this.content = '';
        },
    },
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
</style>