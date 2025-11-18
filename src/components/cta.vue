<style scoped>
.button {
  padding: 6px 16px;
  border: none;
  border-radius: 16px;
  font-family: var(--alternate-font);
  font-weight: 600;
  cursor: pointer;
  background: var(--accent);
  color: #121212;
  transition: all 1000ms;
  font-size: 15px;
  position: relative;
  overflow: hidden;
}

button:hover {
  color: #ffffff;
  transform: scale(1.1);
  box-shadow: 4px 5px 17px -4px var(--primary);
}

button::before {
  content: "";
  position: absolute;
  left: -50px;
  top: 0;
  width: 0;
  height: 100%;
  background-color: var(--primary);
  transform: skewX(45deg);
  z-index: -1;
  transition: width 1000ms;
}

button:hover::before {
  width: 250%;
}
</style>

<script setup>
defineProps({
    label: {
        type: String
    }
})
</script>

<template>
  <button class="button">{{ label }}</button>
</template>
