<template>
  <div class="item">
    <p class="tier">{{ $props.priceItem.title }}</p>
    <div class="pricing">
      <p class="monthly" v-show="monkey === true">{{ $props.priceItem.price.monthly }}</p>
      <p class="annually" v-show="monkey !== true">{{ $props.priceItem.price.annually }}</p>
    </div>
    <div>
      <p class="storage">{{ $props.priceItem.storage }}</p>
      <p class="users">{{ $props.priceItem.users }}</p>
      <p class="upload">{{ $props.priceItem.size }}</p>
    </div>
    <button>LEARN MORE</button>
  </div>
</template>
  
  <script>
export default {
  name: "PriceItem",
  props: ['priceItem']
};
</script>
  
  <style lang="scss" scoped>
.item {
  width: 22rem;
  height: 27rem;
  box-shadow: 0px 0px 20px 3px rgba(0, 0, 0, 0.144);
  padding: 2rem;
  position: relative;
  z-index: 3;
}
.item:nth-child(1) {
  border-top-left-radius: 12px;
  border-bottom-left-radius: 12px;
}

.item:nth-child(3) {
  border-top-right-radius: 12px;
  border-bottom-right-radius: 12px;
}

.special {
  height: 30rem;
  background-image: linear-gradient(hsl(236, 72%, 79%), hsl(237, 63%, 64%));
  color: var(--verylightgreyblue) !important;
  border-radius: 12px;
  padding: 2rem;
}

.item button {
  width: 100%;
  padding-top: 0.7rem;
  padding-bottom: 0.7rem;
  font-family: "Montserrat";
  font-weight: 700;
  color: white;
  border: none;
  font-size: 0.8rem;
  border-radius: 6px;
  background: linear-gradient(90deg, hsl(236, 72%, 79%), hsl(237, 63%, 64%));
  transition: 0.1s ease-in-out all;
}

.special button {
  color: hsl(237, 63%, 64%);
  background: var(--verylightgreyblue);
}

.monthly::before,
.annually::before {
  content: "$";
  font-size: 2rem;
  vertical-align: middle;
  padding-right: 0.5rem;
}
.users::after {
  content: " Users Allowed";
}

p {
  width: 100%;
  text-align: center;
  font-size: 1rem;
  font-weight: 600;
  color: var(--darkgreyblue);
}

.special p {
  color: var(--verylightgreyblue);
}

.tier {
  width: 100%;
  text-align: center;
  font-size: 1.2rem;
  font-weight: 600;
  color: var(--darkgreyblue);
  padding-bottom: 1rem;
}
.special .tier {
  color: var(--verylightgreyblue);
  padding-top: 1.5rem;
}

.monthly,
.annually {
  font-size: 3.2rem;
  font-weight: 700;
  color: var(--darkgreyblue);
}
.special .monthly,
.special .annually {
  color: var(--verylightgreyblue);
}
.special .storage,
.special .users,
.special .upload {
  padding: 0.8rem;
  border-top: 1px solid hsla(240, 80%, 98%, 0.205);
}
.storage,
.users,
.upload {
  padding: 0.8rem;
  border-top: 1px solid hsla(234, 14%, 74%, 0.39);
}
.storage {
  margin-top: 1rem;
}
.upload {
  border-bottom: 1px solid hsla(234, 14%, 74%, 0.39);
  margin-bottom: 2rem;
}
.special .upload {
  border-bottom: 1px solid hsla(240, 80%, 98%, 0.205);
}
.upload::before {
  content: "Send up to ";
}
.storage::after {
  content: " Storage";
}

.item button:active {
  border: 1px solid hsl(237, 63%, 64%);
  color: hsl(237, 63%, 64%);
  background: transparent;
}

.special button:active {
  border: 1px solid white;
  color: white;
  background: transparent;
}

.monthly,
.annually {
  animation: monkeynation 0.3s cubic-bezier(0.18, 0.89, 0.32, 1.28);
}

@keyframes monkeynation {
  0% {
    scale: 0.1;
    opacity: 0;
  }
  100% {
    scale: 1;
    opacity: 1;
  }
}

@media only screen and (max-width: 600px) {
  .item {
    border-radius: 12px;
  }
}
</style>