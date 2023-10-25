<template>
  <div>
    <TheHeader></TheHeader>
    <badge-list></badge-list>
    <user-info :full-name="activeUser.name" :info-text="activeUser.description" :role="activeUser.role"></user-info>
    <course-goal>
      <template v-slot:default="slotProps">
        <h2>{{ slotProps['item'] }}</h2>
      </template>
    </course-goal>

    <button type="button" @click="setSelectedComponent('active-goals')">Active Button</button>
    <button type="button" @click="setSelectedComponent('manage-goals')">Manage Button</button>
    <!-- <active-goals></active-goals>
    <manage-goals></manage-goals> -->
    <KeepAlive>
      <component :is="selectedCompoenent == 'active-goals' ? 'active-goals' : 'manage-goals'"></component>
    </KeepAlive>
  </div>
</template>

<script>
import TheHeader from './components/TheHeader.vue';
import UserInfo from './components/UserInfo.vue'
import BadgeList from './components/BadgeList.vue';
import CourseGoal from './components/CourseGoals.vue'
import ActiveGoals from './components/ActiveGoals.vue'
import ManageGoals from './components/ManageGoals.vue'

export default {
  components: {
    TheHeader,
    UserInfo,
    BadgeList,
    CourseGoal,
    ActiveGoals,
    ManageGoals,
  },
  data() {
    return {
      selectedCompoenent: 'active-goals',
      activeUser: {
        name: 'Maximilian Schwarzmüller',
        description: 'Site owner and admin',
        role: 'admin',
      },
    };
  },
  methods: {
    setSelectedComponent(comp) {
      this.selectedCompoenent = comp;
    }
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