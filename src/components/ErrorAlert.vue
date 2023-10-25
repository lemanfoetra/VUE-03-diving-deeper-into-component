<template>
  <dialog open>
    <slot></slot>
  </dialog>
</template>

<style scoped>
dialog {
  position: fixed;
  top: 20vh;
  left: 30%;
  right: 40%;
  background-color: white;
  padding: 10px;
}
</style>

<script>
export default {
};
</script>