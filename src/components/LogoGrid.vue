<template>
  <section class="grid">
    <div class="logo-wrap" v-for="(imageUrl, idx) in logoGrid.logo_grid_images" :key="idx">
      <g-image :src="imageUrl" alt="client logo" />
    </div>
  </section>
</template>

<script>
export default {
  data() {
    return {
      logoGrid: require("../../data/logo-grid.json")
    };
  }
};
</script>

<style scoped>
.grid {
  display: grid;
  grid-template-columns: repeat(4, 1fr);
  justify-items: center;
  grid-gap: 2rem;
  margin-top: 7rem;
}
.grid img {
  max-height: 100px;
  max-width: 180px;
  object-fit: contain;
}
.logo-wrap {
  display: flex;
  align-self: center;
  justify-content: center;
}
.mini-logo {
  height: 80px;
}

@media (max-width: 1000px) {
  .grid {
    grid-template-columns: repeat(3, 1fr);
  }
}

@media (max-width: 800px) {
  .grid {
    grid-template-columns: repeat(2, 1fr);
  }
}
</style>