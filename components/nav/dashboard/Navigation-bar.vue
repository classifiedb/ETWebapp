<template>
  <div class="m-0 t-0 border-bottom border-bottom-dark">
    <b-navbar type="dark" variant="dark">
      <b-navbar-nav>
        <b-nav-item
          @click="$store.commit('toggleSidebar')"
          class="side-bar-toggle"
        >
          <i
            class="fas tw-text-2xl"
            :class="{
              'fa-angle-double-right': !$store.state.sidebar,
              'fa-angle-double-left': $store.state.sidebar,
            }"
          ></i>
        </b-nav-item>
      </b-navbar-nav>
    </b-navbar>
  </div>
</template>

<script>
export default {
  data() {
    return {};
  },
  computed: {},
  methods: {},
};
</script>

<style>
</style>