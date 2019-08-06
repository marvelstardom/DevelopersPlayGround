<template>
    <Layout class="layout">
        <h1>{{ $page.redditPost.title }}</h1>
        <img :src="$page.redditPost.img" alt="img" class="img">
    </Layout>
</template>

<page-query>
query RedditPost ($path: String) {
  redditPost: redditPost (path: $path) {
    title,
    path,
    img
  }
}
</page-query>

<script>
export default {
    metaInfo() {
       return {
           title: this.$page.redditPost.title
       } 
    }
}
</script>

<style scoped>
.layout {
    height: -webkit-fill-available;
}

.img {
    max-width: 300px;
    max-height: 300px;
}
</style>


