<template>
  <div>
    <router-link style='text-decoration-line: none;' to="/blog-create">
      <b-card class="create" bg-variant="light" border-variant="secondary" style="width: 12rem; height:15rem">
          +
        </b-card>
    </router-link>
  </div>
</template>

<script>
import { BCard } from "bootstrap-vue";
export default {
  components: {
    "b-card": BCard
  }
};
</script>

<style scoped>
.create{
    text-align: center;
    display: flex;
}
</style>