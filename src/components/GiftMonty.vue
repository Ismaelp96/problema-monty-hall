<template>
  <div class="gift">
    <div class="gift-tie-1"></div>
    <div class="gift-tie-2"></div>
    <div class="gift-top"></div>
    <div class="gift-body"></div>
  </div>
</template>

<script>
export default {
  name: 'GiftMonty',
}
</script>

<style>
.gift {
  position: relative;
  display: flex;
  align-items: center;
  flex-direction: column;
  z-index: 10;
}

.gift-top {
  width: 10rem;
  height: 2.5rem;
  background-color: #7aa944;
}
.gift-body {
  width: 9rem;
  height: 6rem;
  background-color: #5c7e32;
}
.gift-tie-1 {
  position: absolute;
  width: 1.5rem;
  height: 8.5rem;
  background-color: red;
}
.gift-tie-2 {
  position: absolute;
  top: 4rem;
  width: 9rem;
  height: 1.5rem;
  background-color: red;
}
</style>
