<template>
  <div>
    <the-header></the-header>
    <button @click="setSelectedComponent('active-goals')">Active Goal</button>
    <button @click="setSelectedComponent('manage-goals')">Manage Goal</button>
    <keep-alive>
      <component :is="activeComponent"></component>
    </keep-alive>
  </div>
</template>

<script>
import TheHeader from '@/components/layout/TheHeader.vue';
import ActiveGoals from "@/components/ActiveGoals";
import ManageGoals from "@/components/ManageGoals";

export default {
  components: {
    TheHeader,
    ActiveGoals,
    ManageGoals
  },
  data() {
    return {
      activeUser: {
        name: 'Maximilian Schwarzmüller',
        description: 'Site owner and admin',
        role: 'admin',
      },
      activeComponent: ""
    };
  },
  methods: {
    setSelectedComponent(cmp) {
      this.activeComponent = cmp;
    }
  }
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