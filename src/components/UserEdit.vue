<template>
  <div class="component">
    <h3>You may edit the User here</h3>
    <p>User age: {{ userAge }}</p>
    <button @click="changeAgeFn">Change age</button>
  </div>
</template>

<script>
export default {
  props: ["userAge", "changeAgeFn"]
};
</script>

<style scoped>
div {
  background-color: lightgreen;
}
</style>
