<template>
  <ul>
    <li v-for="goal in goals" :key="goal">
      <slot :item="goal" :spacing="'...'"></slot>
    </li>
  </ul>
</template>

<script>
export default {
  name: "CourseGoal",
  data() {
    return {
      goals: [
        "Component",
        "vuex",
      ],
    }
  },
}
</script>