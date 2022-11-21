<template>
<div>
  <b-container fluid class="px-0">
    <b-jumbotron header="About" lead="Emperial Technologies" :fluid="true"></b-jumbotron>
  </b-container>

    <h1>Home page</h1>
    <NuxtLink to="/dashboard/index">
      About (internal link that belongs to the Nuxt App)
    </NuxtLink>
    <a href="https://nuxtjs.org">External Link to another page</a>
  </div>
</template>

<script>
export default {
  layout: 'base'
}
</script>

<style></style>
