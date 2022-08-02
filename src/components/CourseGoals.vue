<template>
  <ul>
    <li v-for="goal in goals" :key="goal">
      <!--  
Scoped slots helps passing data from inside a component where a slot is
defined (in this case CourseGoals) towards the component where the markup is
passed (in this case App) by adding a prop that's linked to dynamic value for
example:       -->
      <slot :goal="goal" anotherProp="..."></slot>
      <!-- 
All of these props will be merged in a single props object that will be
accesible to the markup in the main component
       -->
    </li>
  </ul>
</template>
<script>
export default {
  data() {
    return {
      goals: ["Finish the course.", "Master Vue"],
    };
  },
};
</script>
