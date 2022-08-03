<template>
  <div>
    <!-- <the-header></the-header> -->
    <TheHeader />
    <button @click="setSelectedComponent('active-goals')">Active Goals</button>
    <button @click="setSelectedComponent('manage-goals')">Manage Goals</button>
    <!--     <active-goals v-if="selectedComponent === 'active-goals'"></active-goals>
    <manage-goals v-if="selectedComponent === 'manage-goals'"></manage-goals> -->
    <keep-alive>
      <component :is="selectedComponent"></component>
    </keep-alive>
    <!-- <badge-list></badge-list>
    <BadgeList />
        <user-info
      :full-name="activeUser.name"
      :info-text="activeUser.description"
      :role="activeUser.role"
    ></user-info>
    <UserInfo
      :full-name="activeUser.name"
      :info-text="activeUser.description"
      :role="activeUser.role"
    />
    <CourseGoals>
      <template #default="props">
        <h2>{{ props.goal }}</h2>
        <p>{{ props["anotherProp"] }}</p>
      </template>
    </CourseGoals>
    If you're only targetting only the default slot 
You can remove the unnecesary template wrapper
    <CourseGoals #default="props">
      <h2>{{ props.goal }}</h2>
      <p>{{ props["anotherProp"] }}</p>
    </CourseGoals> -->
  </div>
</template>

<script>
import TheHeader from "./components/TheHeader.vue";
import ManageGoals from "./components/ManageGoals.vue";
import ActiveGoals from "./components/ActiveGoals.vue";
/* import UserInfo from "./components/UserInfo.vue";
import BadgeList from "./components/BadgeList.vue";
import CourseGoals from "./components/CourseGoals.vue"; */
export default {
  components: {
    /* "the-header": TheHeader,
    TheHeader: TheHeader,
    UserInfo,
    BadgeList,
    CourseGoals, */
    TheHeader,
    ManageGoals,
    ActiveGoals,
  },
  data() {
    return {
      selectedComponent: "active-goals",
      activeUser: {
        name: "Maximilian Schwarzmüller",
        description: "Site owner and admin",
        role: "admin",
      },
    };
  },
  methods: {
    setSelectedComponent(cmp) {
      this.selectedComponent = cmp;
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
