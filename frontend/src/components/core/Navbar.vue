<template>
  <div id="navbar">
    <v-app-bar app color="light" light>
        <v-img
          alt="logo"
          class="ml-4"
          src="https://secureservercdn.net/198.71.233.179/wzy.63e.myftpupload.com/wp-content/uploads/2019/08/SCM-S_black.png"
          transition="scale-transition"
          width="100"
        />
        <v-tabs
          right
          slider-color="#1D2553"
          class="mr-1"
          color="#f3713a"
        >
          <v-tab @click.prevent="$router.push('/')">
            HOME
          </v-tab>
          <v-tab @click.prevent="$router.push('/about')">
            About
          </v-tab>
        </v-tabs>
    </v-app-bar>
  </div>
</template>

<style scoped>
</style>
