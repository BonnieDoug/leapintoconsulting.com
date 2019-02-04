<template>
  <v-app>
    <core-toolbar :isMobile="isMobile" />
    <core-side-navigation :isMobile="!isMobile"/>
    <core-view />
    <core-footer />
  </v-app>
</template>

<script>
export default {
  components: {
    CoreFooter: () => import('@/components/core/Footer'),
    CoreSideNavigation: () => import('@/components/core/SideNavigation'),
    CoreToolbar: () => import('@/components/core/Toolbar'),
    CoreView: () => import('@/components/core/View')
  },
  mounted () {
    this.onResize()
    window.addEventListener('resize', this.onResize, { passive: true })
  },
  data: () => ({
    isMobile: false
  }),

  methods: {
    onResize () {
      this.isMobile = window.innerWidth < 925
    }
  }
}
</script>
