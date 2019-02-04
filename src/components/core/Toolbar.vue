<template>
  <v-toolbar
    app
    fixed
    flat
    color="white"
  >
    <img width="170" :src="require('@/assets/logo.jpg')">
    <v-spacer/>
    <template v-if="!isMobile">
      <v-btn icon class="ma-2" color="secondary">
        <v-icon>mdi-home</v-icon>
      </v-btn>
      <v-btn class="ma-2" color="secondary">Coaches</v-btn>
      <v-btn class="ma-2" color="secondary">Book</v-btn>
      <v-btn class="ma-2" color="secondary">Events</v-btn>
      <v-btn class="ma-2" color="secondary">Win</v-btn>
      <v-btn class="ma-2" color="secondary">Contact</v-btn>
      <SocialMedia/>
    </template>
    <v-btn chip color="secondary" dark v-else>
      <v-icon>mdi-menu</v-icon>
    </v-btn>
  </v-toolbar>
</template>

<script>
export default {
  components: {
    SocialMedia: () => import('@/components/SocialMedia')
  },
  props: {
    isMobile: {
      type: Boolean,
      default: true
    }
  }
}
</script>
