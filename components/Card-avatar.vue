<template>
  <v-avatar :color="avatarColor" :size="size" class="card-avatar">
    <v-icon :color="iconColor">{{ icon }}</v-icon>
  </v-avatar>
</template>

<script>
export default {
  name: 'CardAvatar',
  props: {
    icon: {
      type: String,
    },
    size: {
      type: String,
      default: '40',
    },
    iconColor: {
      type: String,
      default: '#86b052',
    },
    avatarColor: {
      type: String,
      default: '#40476d',
    },
  },
}
</script>

<style scoped>
.card-avatar {
  margin: 1rem;
}
</style>
