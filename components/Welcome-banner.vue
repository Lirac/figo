<template>
  <v-banner class="banner" elevation="5" single-line
    >Welcome to your dashboard, please complete your profile.
    <template #actions>
      <v-btn
        color="#8fbd51"
        class="text-capitalize white--text font-weight-light"
      >
        Complete Profile
      </v-btn>
    </template></v-banner
  >
</template>

<script>
export default {
  name: 'WelcomeBanner',
}
</script>

<style scoped></style>
