<template>
  <Layout>
    <div>
      <h1>Posts 2</h1>
      <ul>
        <li v-for="edge in $page.posts.edges" :key="edge.node.id">
          <g-link :to="edge.node.path">{{ edge.node.title }}</g-link>
        </li>
      </ul>
    </div>
  </Layout>
</template>
<page-query>
query{
  posts: allPost{
    edges {
      node {
        id,
        title,
        path
      }
    }
  }
}
</page-query>
<script>
import axios from 'axios'
export default {
  name: 'Posts2',
  data () {
    return {}
  },
  // async created () {
  //   const { data } = axios.get('http://jsonplaceholder.typicode.com/posts')
  //   this.posts = data
  // }
}
</script>
<style scoped>

</style>