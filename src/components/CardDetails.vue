<template>
  <div class="card" style="width: 18rem" @click="DisplayDetails">
    <div class="card text-center">
      <div class="card-header">
        <strong>{{ id }}</strong>
      </div>
      <div class="card-header">
        <strong>{{ name }}</strong>
      </div>
      <img :src="img" class="card-img-top" alt="..." />
    </div>
  </div>
</template>
<script>
export default {
  emits: ["toggleRecipeStatus"],
  props: {
    id: {
      type: Number,
      required: true,
    },
    name: {
      type: String,
      required: true,
    },
    img: {
      required: true,
    },
    description: {
      type: String,
      required: true,
    },
  },

  methods: {
    DisplayDetails() {
      // this.showRecipe = !this.showRecipe;
      this.$emit("toggleRecipeStatus", this.id);
    },
  },
};
</script>

<style>
.flex-box {
  display: flex;
}

.card {
  flex: 0.2;
  display: flex;
  flex-direction: column;
  margin-left: 5%;
}
</style>
