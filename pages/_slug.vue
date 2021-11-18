<template>
  <div>
    <Header />
    <article>
      <nuxt-content :document="article" />
    </article>
  </div>
</template>

<script>
import Header from '~/components/Header.vue'
export default {
  components: { Header },
  async asyncData({ $content, params }) {
    const article = await $content('blog', params.slug).fetch()
    return { article }
  },
}
</script>

<style scoped>
article {
  display: block;
  margin: 0 auto;
  padding: 50px 30px;
  max-width: 800px;
}
h1 {
  font-size: 28px;
  font-weight: 900;
  margin-bottom: 30px;
}
</style>
