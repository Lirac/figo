<template>
  <v-avatar size="40" class="card-avatar">
    <v-icon color="#86b052">{{ icon }}</v-icon>
  </v-avatar>
</template>

<script>
export default {
  name: 'CardAvatar',
  props: {
    icon: {
      type: String,
    },
  },
}
</script>

<style scoped>
.card-avatar {
  margin: 1rem;
  background: #40476d;
}
</style>
