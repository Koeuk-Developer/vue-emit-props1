<template>
  <div class="container">
    <div class="mb-4">
    <div id="card" class="card" @click="handleClick(title)">
      <div class="card-body">
        <p class="card-name"> UserName role {{ userId }} | ID {{ id }}</p>
        <h4 class="card-title">{{ title }}</h4>
        <p class="card-text">{{ body }}</p>
      </div>
    </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "CardComponent",
  props: {
    userId: String,
    title: String,
    body: String,
    id: null,
  },
  // 
  methods: {
    handleClick(post) {
      this.$emit('dataPost', post);
    }
  }
};
</script>

<style>
#card:hover {
  background-color: #f1f1f1;
  cursor: pointer;
}
</style>
