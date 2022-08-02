<template>
  <div>
    <!-- <the-header></the-header> -->
    <TheHeader />
    <!--     <badge-list></badge-list> -->
    <BadgeList />
    <!--     <user-info
      :full-name="activeUser.name"
      :info-text="activeUser.description"
      :role="activeUser.role"
    ></user-info> -->
    <UserInfo
      :full-name="activeUser.name"
      :info-text="activeUser.description"
      :role="activeUser.role"
    />
    <!-- <CourseGoals>
      <template #default="props">
        <h2>{{ props.goal }}</h2>
        <p>{{ props["anotherProp"] }}</p>
      </template>
    </CourseGoals> -->
    <!-- If you're only targetting only the default slot 
You can remove the unnecesary template wrapper -->
    <CourseGoals #default="props">
      <h2>{{ props.goal }}</h2>
      <p>{{ props["anotherProp"] }}</p>
    </CourseGoals>
  </div>
</template>

<script>
import TheHeader from "./components/TheHeader.vue";
import UserInfo from "./components/UserInfo.vue";
import BadgeList from "./components/BadgeList.vue";
import CourseGoals from "./components/CourseGoals.vue";
export default {
  components: {
    /* "the-header": TheHeader, */
    /* TheHeader: TheHeader, */
    TheHeader,
    UserInfo,
    BadgeList,
    CourseGoals,
  },
  data() {
    return {
      activeUser: {
        name: "Maximilian Schwarzmüller",
        description: "Site owner and admin",
        role: "admin",
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
