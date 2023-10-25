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
  </div>
</template>

<script>
import TheHeader from './components/TheHeader.vue';
import UserInfo from './components/UserInfo.vue'
import BadgeList from './components/BadgeList.vue';
import CourseGoal from './components/CourseGoals.vue'

export default {
  components: {
    TheHeader,
    UserInfo,
    BadgeList,
    CourseGoal
  },
  data() {
    return {
      activeUser: {
        name: 'Maximilian Schwarzmüller',
        description: 'Site owner and admin',
        role: 'admin',
      },
    };
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