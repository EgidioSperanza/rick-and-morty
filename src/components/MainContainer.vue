<template>
  <div class="personages-list">
    <div v-for="personage in personages" :key="personage.id">
      <card-box :personage="personage" />
    </div>
  </div>
</template>

<script>
import CardBox from "./CardBox.vue";

export default {
  props: {
    personages: Array,
  },

  components: {
    CardBox,
  },
};
</script>

<style scoped lang="scss">
.personages-list {
  display: flex;
  flex-wrap: wrap;
  justify-content: space-between;
  width: 80%;
  margin: 0 auto;
  padding-top: 20px;
}
</style>
