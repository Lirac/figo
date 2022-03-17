<template>
  <div>
    <v-row>
      <h2 class="heading__2">Hello Frank.</h2>
      <welcome-banner></welcome-banner>
    </v-row>
    <v-row> </v-row>
  </div>
</template>

<script>
import welcomeBanner from '~/components/welcome-banner.vue'
export default {
  components: [welcomeBanner],
}
</script>
