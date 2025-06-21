<script>
export default {
  data() {
    return {
      goals: ['Finish the Course', 'Master Vue']
    }
  }
}
</script>

<template>
  <ul>
    <li v-for="goal in goals">
      <slot :item="goal"></slot>
    </li>
  </ul>
</template>

<style scoped>

</style>