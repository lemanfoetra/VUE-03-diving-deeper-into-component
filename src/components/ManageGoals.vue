<template>
  <h2>Manage Goals</h2>
  <input type="text" ref="goal">
  <button type="button" @click="setGoal">Set Goal</button>
  <Teleport to="body">
    <ErrorAlert v-if="inputIsInvalid">
      <h2>Input is invalid!</h2>
      <p>Mohon masukan sebuah data</p>
      <button type="button" @click="confirmError">Oke</button>
    </ErrorAlert>
  </Teleport>
</template>

<script>
import ErrorAlert from './ErrorAlert.vue'

export default {
  components: {
    ErrorAlert
  },
  data() {
    return {
      inputIsInvalid: false,
    }
  },
  methods: {
    setGoal() {
      const eneterdValue = this.$refs.goal.value;
      if (eneterdValue === '') {
        this.inputIsInvalid = true
      }
    },
    confirmError() {
      this.inputIsInvalid = false
    }
  }
};
</script>