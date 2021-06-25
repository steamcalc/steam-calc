<template>
  <div class="container" :class="maxWidth ? 'max-width' : ''">
    <slot></slot>
  </div>
</template>

<script>
export default {
  props: ['maxWidth'],
};
</script>

<style scoped>
.container {
  background-color: white;
  box-shadow: 0 2px 8px rgba(0, 0, 0, 0.26);
  border-radius: 12px;
  margin: 1rem 2rem;
  padding: 1rem;
}

@media screen and (max-width: 500px) {
  .container {
    margin: 1rem 0;
  }
}

.max-width {
  max-width: 40rem;
  margin: 2rem auto;
}
</style>
