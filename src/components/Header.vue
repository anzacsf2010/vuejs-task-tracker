<template>
  <header class="header">
    <h1>{{ title }}</h1>
    <Button v-show="homePage"
            @btn-click="$emit('toggle-add-task')"
            :text="showAddTask ? 'Close' : 'Add new task'"
            :color="showAddTask ? 'blue' : 'green'" />
  </header>
</template>

<script>
import Button from "@/components/Button";

export default {
  name: "Header",
  props: {
    title: String,
    showAddTask: Boolean,
  },
  components: {
    Button,
  },
  emits: ['toggle-add-task'],
  computed: {
    homePage() {
      return this.$route.path === '/';
    },
  },
}
</script>