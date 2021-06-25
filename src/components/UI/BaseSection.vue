<template>
  <div>
    <div class="header">
      <hr />
      <span class="heading">{{ title }}</span>
      <hr />
    </div>
    <base-container>
      <slot></slot>
    </base-container>
  </div>
</template>

<script>
import BaseContainer from './BaseContainer.vue';
export default {
  components: {
    BaseContainer,
  },
  props: ['title'],
};
</script>

BaseContainer
<style scoped>
.header {
  display: flex;
  flex-direction: row;
  justify-content: space-between;
  align-items: center;
}
.heading {
  width: 20em;
  word-break: break-word;
  font-size: 2em;
}
hr {
  width: 50%;
  min-width: 3em;
  border-color: #42b983;
  margin: 0 2em;
}

@media only screen and (max-width: 500px) {
  hr {
    display: none;
  }
}
</style>
