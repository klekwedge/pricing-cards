<template>
  <section>
    <h1 class="header">Our Pricing</h1>
    <Switch />
    <!-- <img src="../assets/bg-top.svg" alt="" class="top" /> -->
  </section>
</template>

<script lang="ts">
import Switch from "./components/Switch.vue";

export default {
  components: { Switch },
  setup() {
    return {};
  },
};
</script>

<style scoped>
section {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  width: 100%;
  min-height: 100vh;
  height: fit-content;
  background: url(../assets/bg-bottom.svg), var(--verylightgreyblue);
  background-repeat: no-repeat;
  background-position: bottom left;
  background-clip: content-box;
  background-size: 30%;
  font-family: "Montserrat";
  z-index: 0;
  position: relative;
}

.header {
  font-size: 2rem;
  color: var(--greyblue);
  position: relative;
  z-index: 3;
}
</style>
