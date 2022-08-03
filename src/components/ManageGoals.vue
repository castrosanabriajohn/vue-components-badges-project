<template>
  <!-- In vue3 you can have multiple top level elements -->
  <h2>Manage Goals</h2>
  <input type="text" ref="goal" />
  <button @click="addGoal">Add Goal</button>
  <teleport to="body">
    <error-alert v-if="invalidInput">
      <h2>Input is invalid!</h2>
      <p>Please enter at least one character...</p>
      <button @click="dismissError">Ok</button>
    </error-alert>
  </teleport>
</template>

<script>
import ErrorAlert from "./ErrorAlert.vue";
export default {
  components: { ErrorAlert },
  data() {
    return {
      invalidInput: false,
    };
  },
  methods: {
    addGoal() {
      const inputValue = this.$refs.goal.value;
      if (inputValue == "") {
        this.invalidInput = true;
      }
    },
    dismissError() {
      this.invalidInput = false;
    },
  },
};
</script>
