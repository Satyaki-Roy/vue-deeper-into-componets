<template>
  <h2>Manage Goals</h2>
  <input type="text" ref="goal">
  <button @click="setGoal">Set Goal</button>
  <teleport to="body">
    <error-alert v-if="isGoalEmpty">
      <h2>Input is invalid</h2>
      <p>Please enter few characters</p>
      <button @click="hideError">Ok</button>
    </error-alert>
  </teleport>
</template>

<script>
import ErrorAlert from "@/components/ErrorAlert";

export default {
  name: "ManageGoals",
  components: {
    ErrorAlert,
  },
  data() {
    return {
      isGoalEmpty: false,
    }
  },
  methods: {
    setGoal() {
      const enteredValue = this.$refs.goal.value;
      if (enteredValue === "") {
        this.isGoalEmpty = true;
      }
    },
    hideError() {
      this.isGoalEmpty = false;
    }
  }
}
</script>