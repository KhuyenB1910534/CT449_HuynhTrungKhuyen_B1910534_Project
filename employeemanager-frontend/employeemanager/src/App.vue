<script>
import Appheader from "@/components/Appheader.vue";
export default {
  components: {
    Appheader,
  },
};
</script>
<template>
  <div id="app">
    <Appheader />
    <div class="container mt-3">
      <router-view />
    </div>
  </div>
</template>
<style>
.page {
  max-width: 400px;

  margin: auto;
}
</style>