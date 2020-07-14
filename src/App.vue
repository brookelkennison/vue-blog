// Next Steps:
//   Save data using localStorage
//   Retitle Blog.vue to BlogCreate.vue
//   Create an underline style under the page you are on
//   Create filter to filter blog posts

<template>
  <div id="app">
    <Header 
      @showCreatePosts="updateBlogBoolean" 
      @showBlogPosts="updateBlogBoolean">
    </Header>
    <Blog v-show="blogEntry" :blogPosts="blogPosts" @postEntry="saveToLocal"></Blog>
    <Posts v-show="!blogEntry"  :blogPosts="blogPosts"></Posts>
  </div>
</template>

<script>
import Blog from './components/Blog.vue';
import Posts from './components/Posts.vue';
import Header from './components/Header.vue';

export default {
  name: 'App',
  components: {
    Header,
    Blog,
    Posts,
  },
  data() {
    return {
      blogEntry: false,
      blogPosts: [],
    }
  },
  mounted() {
    if (localStorage.getItem('blogPosts')) {
        this.blogPosts = JSON.parse(localStorage.getItem('blogPosts'))
    }     
  },
  methods: {
    updateBlogBoolean (updatedBlogBoolean) {
      this.blogEntry = updatedBlogBoolean
    },
    updateBlogPosts (updatedBlogPosts) {
      this.blogPosts = updatedBlogPosts
    },
    saveToLocal () {
      const parsed = JSON.stringify(this.blogPosts);
      localStorage.setItem('blogPosts', parsed);
      console.log(localStorage.getItem('blogPosts'))
    }
  }
}
</script>

<style>
</style>
