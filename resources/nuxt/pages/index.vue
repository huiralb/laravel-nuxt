<template>
  <div>
    <b-container>
      <h1>{{ user.name }}</h1>
    </b-container>
  </div>
</template>

<script>
export default {
  // https://github.com/nuxt-community/axios-module
  async asyncData({ app }) {
    const user = await app.$axios.$get("api/me")
    return { user }
  },
  data: () => {
    return { name: "world" }
  }
}
</script>