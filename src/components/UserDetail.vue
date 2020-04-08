<template>
  <div class="component">
    <h3>You may view the User Details here</h3>
    <p>Many Details</p>
    <p>User name: {{ name }}</p>
    <p>User age: {{ userAge }}</p>
    <button @click="resetName">Reset name</button>
    <button @click="resetFn">Reset name</button>
  </div>
</template>

<script>
import { eventBus } from "../main";

export default {
  props: {
    name: {
      type: String,
      required: true
    },
    resetFn: Function,
    userAge: Number
  },
  methods: {
    resetName() {
      this.name = "Nico";
      this.$emit("nameWasChanged", this.name);
    }
  },
  created() {
    eventBus.$on("ageWasChanged", age => {
      this.userAge = age;
    });
  }
};
</script>

<style scoped>
div {
  background-color: lightcoral;
}
</style>
