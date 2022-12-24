<template>
  <div class="door-area">
    <div class="door-frame" :class="{ selected: selected && !open }">
      <GiftMonty v-if="open && hasGift" />
    </div>
    <div class="door" :class="{ open }" @click="selected = !selected">
      <div class="number" :class="{ selected }">{{ number }}</div>
      <div class="knob" @click.stop="open = true" :class="{ selected }"></div>
    </div>
  </div>
</template>

<script>
import GiftMonty from './GiftMonty.vue'
export default {
  name: 'DoorMonty',
  components: { GiftMonty },
  props: {
    number: {},
    hasGift: { type: Boolean },
  },
  data: function () {
    return {
      open: false,
      selected: false,
    }
  },
}
</script>

<style>
:root {
  --door-border: 5px solid brown;
  --selected-border: 5px solid yellow;
}
.door-area {
  position: relative;
  width: 20rem;
  height: 31rem;
  border-bottom: 10px solid #aaa;
  margin-bottom: 2rem;
  font-size: 3rem;

  display: flex;
  justify-content: center;
}

.door-frame {
  position: absolute;
  height: 30rem;
  width: 18rem;

  border-left: var(--door-border);
  border-top: var(--door-border);
  border-right: var(--door-border);

  display: flex;
  justify-content: center;
  align-items: flex-end;

  transition: all 0.3s ease-in;
}
.door {
  position: absolute;
  top: 0.5rem;
  height: 29.5rem;
  width: 17rem;
  background-color: chocolate;

  display: flex;
  flex-direction: column;
  align-items: center;
  padding: 1.8rem;
}
.door .number {
  transition: color 0.3s ease-in;
}

.door .knob {
  height: 2rem;
  width: 2rem;
  border-radius: 50%;
  background-color: brown;
  align-self: flex-start;
  margin-top: 10rem;
  transition: background-color 0.3s ease;
}
.door-frame.selected {
  border-left: var(--selected-border);
  border-right: var(--selected-border);
  border-top: var(--selected-border);
  box-shadow: 0px 15px 15px yellow;
}

.door .knob.selected {
  background-color: yellow;
}

.door .number.selected {
  color: yellow;
}
.door.open {
  background-color: #0007;
}

.door.open .knob {
  opacity: 0;
  pointer-events: none;
}
.door.open .number {
  opacity: 0;
  pointer-events: none;
}
</style>
