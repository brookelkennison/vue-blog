<template>
  <div id="app">
    <Header 
      @showCreatePosts="updateBlogBoolean" 
      @showBlogPosts="updateBlogBoolean">
    </Header>
    <Blog v-show="blogEntry"></Blog>
    <Posts v-show="!blogEntry"></Posts>
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
    }
  },
  methods: {
    updateBlogBoolean: function (updatedBlogBoolean) {
      this.blogEntry = updatedBlogBoolean
    }
  }
}
</script>

<style>
</style>
