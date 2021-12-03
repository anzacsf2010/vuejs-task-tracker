<template>
  <h3>Version {{ version }}</h3>
  <router-link to="/">Go Back</router-link>
</template>

<script>
export default {
  name: 'About',
  data() {
    return {
      version: '1.0.0'
    }
  },
  inheritAttrs: false, // disable 'non-props' warning
};
</script>