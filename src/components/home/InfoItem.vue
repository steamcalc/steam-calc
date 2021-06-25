<template>
  <div class="item">
    <img :src="require('@/assets/' + imgSrc)" />
    <h2>{{ title }}</h2>
    <p>{{ description }}</p>
  </div>
</template>

<script>
export default {
  props: ['imgSrc', 'title', 'description'],
};
</script>

<style scoped>
.item {
  max-width: 15em;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  margin: 1rem 0;
}
img {
  width: 8em;
  height: 8em;
}
h2 {
  margin: 0;
}
p {
  margin: 0;
  padding: 0;
}
</style>
