<template>
  <section>
    <h1 class="header">Our Pricing</h1>
    <Switch @changePlan="changePlan" />
    <div class="container">
      <PriceItem
        v-for="item in items"
        :priceItem="item"
        :key="item.title"
        :montly="montly"
      />
    </div>
    <!-- <img src="../assets/bg-top.svg" alt="" class="top" /> -->
  </section>
</template>

<script lang="js">
import { ref } from "vue";
import Switch from "./components/Switch.vue";
import PriceItem from "./components/PriceItem.vue";
import data from "./data/data";

export default {
  components: { Switch, PriceItem },
  setup() {
    const items = ref(data);
    const montly = ref(true);

    const changePlan = (value) => {
      montly.value = value;
    };

    return {
      items,
      montly,
      changePlan,
    };
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
  /* background: url(../assets/bg-bottom.svg), var(--verylightgreyblue); */
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

.container {
  display: flex;
  flex-direction: row;
  align-items: center;
  justify-content: center;
  column-gap: 0;
  position: relative;
  z-index: 9999;
}
.top {
  position: absolute;
  z-index: -1;
  object-fit: contain;
  width: 100%;
  height: 100vh;
  object-position: top right;
}
img .top {
  display: none;
  position: relative;
  z-index: -1;
}

@media only screen and (max-width: 600px) {
  section {
    padding-bottom: 2rem;
    padding-top: 4rem;
    background: none;
  }
  .top {
    display: none;
  }
  .container {
    display: flex;
    flex-direction: column;
    row-gap: 1rem;
  }
}
</style>
