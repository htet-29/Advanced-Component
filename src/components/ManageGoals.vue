<script>
  import ErrorDialog from "@/components/ErrorDialog.vue";
  export default {
    components: {
      ErrorDialog,
    },
    data() {
      return {
        errorIsInvalid: false,
      }
    },
    methods: {
      addGoal() {
        const enteredGoal = this.$refs.goal.value;
        if (enteredGoal === '') {
          this.errorIsInvalid = true;
        }
      },
      confirmError() {
        this.errorIsInvalid = false;
      }
    }
  }
</script>

<template>
  <div>
    <h2>Manage Goals</h2>
    <input type="text" ref="goal"/>
    <button @click="addGoal">Submit</button>
    <error-dialog v-if="errorIsInvalid">
      <h2>Input is invalid!</h2>
      <p>Please enter at least a few characters...</p>
      <button @click="confirmError">OK</button>
    </error-dialog>
  </div>
</template>

<style scoped>

</style>