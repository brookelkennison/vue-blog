// Next Steps:
//   Create an array for blog posts to get pushed to after posted.
//   Create an underline style under the page you are on
//   Create filter to filter blog posts



<template>
  <div id="app">
    <Header 
      @showCreatePosts="updateBlogBoolean" 
      @showBlogPosts="updateBlogBoolean">
    </Header>
    <Blog v-show="blogEntry" :blogPosts="blogPosts" ></Blog>
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
      // blogTitles: [],
      // blogContent: [],
    }
  },
  methods: {
    updateBlogBoolean (updatedBlogBoolean) {
      this.blogEntry = updatedBlogBoolean
    },
    updateBlogPosts (updatedBlogPosts) {
      this.blogPosts = updatedBlogPosts
      console.log(this.blogPosts.blogTitles.length)
    }
  }
}
</script>

<style>
</style>
