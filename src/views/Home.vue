<template>
  <div class="home">
    <img alt="Vue logo" src="@/assets/logo.png" />
    <base-section title="Why Us?">
      <div class="info-items">
        <info-item
          img-src="free.png"
          title="Free"
          description="know the value of your steam account completely free"
        ></info-item>
        <info-item
          img-src="free.png"
          title="No Login"
          description="know the worth of your steam account completely free"
        ></info-item>
        <info-item
          img-src="free.png"
          title="Full Privacy"
          description="know the worth of your steam account completely free"
        ></info-item>
      </div>
    </base-section>
  </div>
</template>

<script>
// @ is an alias to /src
import BaseSection from '@/components/UI/BaseSection.vue';
import InfoItem from '@/components/home/InfoItem.vue';

export default {
  components: {
    BaseSection,
    InfoItem,
  },
};
</script>

<style scoped>
.info-items {
  display: flex;
  flex-direction: row;
  justify-content: space-evenly;
  flex-wrap: wrap;
}
</style>
