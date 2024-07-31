<template>
  <div class="container">
    <div class="mb-4">
      <div class="alert alert-primary" role="alert">
        {{ post }}
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "AlertComponent",
  props: {
    post: String,
  },
};
</script>

<style></style>
