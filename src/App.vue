<template>
  <div>
    <TheHeader />
    <button @click="setSelectComponent('ActiveGoal')">Active Goal</button>
    <button @click="setSelectComponent('ManageGoals')">Manage Goals</button>
    <keep-alive>
      <component :is="selectedComponent"></component>
    </keep-alive>
  </div>
</template>

<script>

import TheHeader from "@/components/TheHeader.vue";
import ManageGoals from "@/components/ManageGoals.vue";
import ActiveGoal from "@/components/ActiveGoal.vue";
// import UserInfo from "@/components/UserInfo.vue";
// import BadgeList from "@/components/BadgeList.vue";

export default {
  components: {
    TheHeader,
    ActiveGoal,
    ManageGoals,
  },
  data() {
    return {
      selectedComponent: 'ActiveGoal',
      activeUser: {
        name: 'Maximilian Schwarzmüller',
        description: 'Site owner and admin',
        role: 'admin',
      },
    };
  },
  methods: {
    setSelectComponent(component) {
      this.selectedComponent = component;
    },
  },
};
</script>

<style>
html {
  font-family: sans-serif;
}

body {
  margin: 0;
}
</style>