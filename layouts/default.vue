<template>
  <v-app dark>
    <v-navigation-drawer v-model="drawer" app>
      <v-list-item class="mb-10">
        <v-list-item-avatar>
          <img src="~/assets/img/avatar.svg" />
        </v-list-item-avatar>
      </v-list-item>
      <v-list nav dense>
        <v-list-item
          v-for="(item, i) in items"
          :key="i"
          :to="item.to"
          router
          exact
          active-class="list_item_active"
          class="list_item"
        >
          <v-list-item-action>
            <v-icon>{{ item.icon }}</v-icon>
          </v-list-item-action>
          <v-list-item-content>
            <v-list-item-title v-text="item.title" />
          </v-list-item-content>
        </v-list-item>
      </v-list>
    </v-navigation-drawer>
    <v-app-bar dense fixed flat app>
      <v-app-bar-nav-icon @click.stop="drawer = !drawer" />
      <v-spacer />
      <v-btn icon @click.stop="rightDrawer = !rightDrawer">
        <v-icon>mdi-menu</v-icon>
      </v-btn>
    </v-app-bar>
    <v-main class="page">
      <v-container class="page-container">
        <nuxt />
      </v-container>
    </v-main>
    <v-navigation-drawer v-model="rightDrawer" :right="right" app>
      <div class="text-center right-drawer__container">
        <v-icon class="account-icon">mdi-account-circle</v-icon>

        <v-icon class="ml-8">mdi-dots-vertical</v-icon>

        <h3 class="mt-10">Transaction History</h3>
        <p class="transaction-status mt-16">You have no transactions yet</p>
      </div>
    </v-navigation-drawer>
  </v-app>
</template>

<script>
export default {
  data() {
    return {
      clipped: false,
      drawer: false,
      fixed: false,
      items: [
        {
          icon: 'mdi-view-dashboard',
          title: 'Dashboard',
          to: '/',
        },
        {
          icon: 'mdi-hand-coin',
          title: 'Get Loans',
          to: '/get-loans',
        },
        {
          icon: 'mdi-send',
          title: 'Transfer Money',
          to: '#',
        },
        {
          icon: 'mdi-piggy-bank',
          title: 'Save Money',
          to: 's',
        },
        {
          icon: 'mdi-wallet',
          title: 'Wallet',
          to: 't',
        },
        {
          icon: 'mdi-cart',
          title: 'Pay Later',
          to: '',
        },
      ],
      miniVariant: true,
      right: true,
      rightDrawer: false,
      title: 'Vuetify.js',
    }
  },
}
</script>
<style scoped>
.list_item {
  margin: 1rem 1rem;
}
.list_item_active {
  background: #6eb04d;
  border-radius: 0.6rem;
  overflow: hidden;
}
.list_item_active .v-list-item__action {
  margin: 0 2rem 0 0;
}

.page-container {
  padding-top: 2rem;
}
.right-drawer__container {
  padding: 3rem 2.5rem;
}

.account-icon {
  color: var(--color-heading);
}

.transaction-status {
  font-size: 1rem;
  font-weight: 500;
  opacity: 0.5;
}
</style>
