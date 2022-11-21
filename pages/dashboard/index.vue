<template>
  <!-- <b-container fluid>
    <b-row>
      <b-col>
        <h1>Emperial Technologies</h1>
        <nuxt-link>
        <br />
      </b-col>
    </b-row>
  </b-container> -->
  <main>
    <h1>Home page</h1>
    <NuxtLink to="/about">
      About (internal link that belongs to the Nuxt App)
    </NuxtLink>
    <a href="https://nuxtjs.org">External Link to another page</a>
  </main>
</template>

<script>

export default {
  layout: "dashboard",
  data() {
    return {};
  },
  created() {
  },
  mounted() {
  },
  watch: {},
  methods: {},
};
</script>

<style>
h1 {
  font-size: 28px;
}
h4 {
  font-style: italic;
  font-size: 14px;
}
.pointer {
  cursor: pointer;
}
.district-labels {
  color: white;
  opacity: 0.8;
  font-size: 20px;
  font-weight: bold;
  text-align: center;
}
.label-div {
  text-align: center;
}

.site-labels {
  color: white;
  font-size: 10px;
  text-align: left;
}
.site-div {
  width: 200px;
  position: relative;
  top: 10px;
  font-weight: 700;
}
.card-font-style {
  font-size: 20px;
  font-weight: bold;
}
.card-border-style {
  border-radius: 0;
}
</style>
