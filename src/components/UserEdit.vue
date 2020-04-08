<template>
  <div class="component">
    <h3>You may edit the User here</h3>
    <p>User age: {{ userAge }}</p>
    <button @click="changeAge">Change age</button>
  </div>
</template>

<script>
export default {
  props: ["userAge"],
  methods: {
    changeAge() {
      this.userAge = 33;
      this.$emit("ageWasChanged", this.userAge);
    }
  }
};
</script>

<style scoped>
div {
  background-color: lightgreen;
}
</style>
