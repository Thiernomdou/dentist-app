<template>
  <v-app>
    <sidebar-top></sidebar-top>
    <v-main>
      <router-view/>
    </v-main>
  </v-app>
</template>

<script>
import SideBar from '@/components/SideBar'
export default {
  name: 'App',

  data: () => ({
    //
  }),
  components: {
    'sidebar-top': SideBar
  }
};
</script>
