<template>
  <div>
    <Header />
    <div class="home-page">
      <h2 class="latest">Latest posts</h2>
      <div class="articels">
        <div class="article" v-for="article of articles" :key="article">
          <nuxt-link :to="{ name: 'slug', params: { slug: article.slug } }">
            <div class="detail">
              <h3>{{ article.title }}</h3>
              <p>{{ article.description }}</p>
            </div>
          </nuxt-link>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  async asyncData({ $content, params }) {
    const articles = await $content('blog', params.slug)
      .only(['title', 'description', 'slug'])
      .sortBy('createdAt', 'asc')
      .fetch()
    return { articles }
  },
}
</script>
<style>
.home-page,
.latest {
  text-align: center;
  margin: 20px auto;
  display: flex;
  flex-direction: column;
  align-items: center;
}
.article {
  background-color: white;
  margin: 10px;
  width: 500px;
  height: 100px;
  padding: 10px;
  box-shadow: lightgrey 2px 2px 2px;
}
</style>
