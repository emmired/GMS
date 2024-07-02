<!-- SkeletonLoading.vue -->
<template>
  <div class="skeleton-loading">
    <div class="skeleton-item" v-for="n in itemCount" :key="n">

      <q-skeleton type="QAvatar" />
      <q-skeleton class="skeleton-text" width="" />
      <q-skeleton class="skeleton-text" width="" />
      <q-skeleton class="skeleton-text" width="" />
    </div>
  </div>

</template>

<script>
export default {
  props: {
    itemCount: {
      type: Number,
      default: 1 // Number of skeleton items to display
    }
  }
};
</script>

<style scoped>
.skeleton-loading {
  margin-top: 20px; /* Adjust spacing as needed */
}

.skeleton-item {
  display: flex;
  height: 60px;
  width: 100%;
  justify-content: space-between;
  align-items: center;
  padding: 0 40px 0 20px;
  margin-bottom: 10px;
  background-color: #cc4b4b;
  border-radius: 10px;
}
.skeleton-text{
  width: 25%;
  height: 10px;
}
</style>
