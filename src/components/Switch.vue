<template>
  <div class="range">
    <p class="inactive" :class="{ active: monkey }">Monthly</p>
    <label class="switch">
      <input type="checkbox" />
      <span class="slider round" @click="monkey = !monkey"></span>
    </label>
    <p class="inactive" :class="{ active: !monkey }">Annually</p>
  </div>
</template>

<script>
export default {
  name: "Switch",
};
</script>

<style lang="scss" scoped>
.switch {
  position: relative;
  display: inline-block;
  min-width: 60px;
  min-height: 34px;
}

.switch input {
  opacity: 0;
  width: 0;
  height: 0;
}

.slider {
  position: absolute;
  cursor: pointer;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  background-color: #ccc;
  -webkit-transition: 0.4s;
  transition: 0.4s all ease-in-out;
}

.slider:before {
  position: absolute;
  content: "";
  height: 26px;
  width: 26px;
  left: 4px;
  bottom: 4px;
  background-color: white;
  -webkit-transition: 0.4s;
  transition: 0.4s;
}

input:checked + .slider {
  background: linear-gradient(180deg, hsl(236, 72%, 79%), hsl(237, 63%, 64%));
}

input:focus + .slider {
  box-shadow: 0 0 1px hsl(237, 63%, 64%);
}

input:checked + .slider:before {
  -webkit-transform: translateX(26px);
  -ms-transform: translateX(26px);
  transform: translateX(26px);
}

.slider.round {
  border-radius: 34px;
}

.slider.round:before {
  border-radius: 50%;
}

.range {
  display: flex;
  width: fit-content;
  height: fit-content;
  align-items: center;
  justify-content: center;
  column-gap: 1.5rem;
  padding: 2rem;
  padding-bottom: 3rem;
  position: relative;
  z-index: 3;
}

.inactive {
  color: var(--lightgreyblue);
  transition: all 0.2s ease-in-out;
}

.active {
  color: var(--greyblue);
  transition: all 0.2s ease-in-out;
}

</style>