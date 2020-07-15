<template>
  <v-app>
    <Navbar />
    <Content />
  </v-app>
</template>

<script>
import Navbar from '@/components/core/Navbar'
import Content from '@/components/core/Content'
export default {
  name: "App",
  components: {
    Navbar,
    Content
  },

};
</script>
