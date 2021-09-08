<template>
  <div class="alert alert-info">
    <h2>{{ title }}</h2>
    <p>{{ que }}</p>
  </div>
</template>

<script>
export default {
  name: "Que",
  props: {
    title: String,
    que: String,
  }
};
</script>
