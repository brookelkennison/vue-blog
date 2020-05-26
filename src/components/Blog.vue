<template>
    <div>
        <h2>Create a Post</h2>
        <p>Title:</p>
        <input type="text" v-model.lazy='title'>
        <p>Content:</p>
        <textarea name="" id="" cols="30" rows="10" v-model='content'></textarea>
        <button v-on:click='postEntry()'>Post</button>
        <h4>{{title}}</h4>
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
    props: [
        
    ],
    methods: {
        postEntry () {
            console.log(this.title)
            console.log(this.content)
            alert('Your post has been submitted');
        }
    }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
</style>