<template>
  <div class="component">
    <h3>You may edit the User here</h3>
    <p>User age: {{ userAge }}</p>
    <button @click="changeAge">Change age</button>
  </div>
</template>

<script>
import { eventBus } from "../main";

export default {
  props: ["userAge"],
  methods: {
    changeAge() {
      this.userAge = 33;
      // this.$emit("ageWasChanged", this.userAge);
      // eventBus.$emit("ageWasChanged", this.userAge);
      eventBus.changeAge(this.userAge);
    }
  }
};
</script>

<style scoped>
div {
  background-color: lightgreen;
}
</style>
