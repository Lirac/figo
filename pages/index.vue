<template>
  <div>
    <v-row>
      <h2>Hello Frank.</h2>
      <welcome-banner></welcome-banner>
    </v-row>

    <section class="block">
      <h3>Your wallet</h3>
      <v-row>
        <v-col md="6" class="sm-12">
          <v-card elevation="1">
            <v-card-title>
              <p>Account balance</p>
            </v-card-title>
            <v-card-text>
              <h1 class="acc__bal">0.00</h1>
              <p class="balance__label">Hide balance</p>
              <v-switch class="d-inline-flex balance-switch"></v-switch>
              <div class="d-flex align-center mt-10 mb-4">
                <span class="mr-4 acc-num">Account no: 04675932367</span>
                <v-icon color="#3f4f80">mdi-credit-card-chip</v-icon>
              </div>
            </v-card-text>
          </v-card>
        </v-col>
        <v-col md="3" sm="12">
          <v-card class="wallet-card">
            <card-avatar :icon="'mdi-hand-coin'"></card-avatar>
            <v-card-text class="wallet-text">
              <h5>Apply for Loan</h5>
            </v-card-text>
          </v-card>
        </v-col>
        <v-col md="3" sm="12">
          <v-card class="wallet-card">
            <card-avatar :icon="'mdi-swap-horizontal'"></card-avatar>
            <v-card-text class="wallet-text">
              <h5>Send money</h5>
            </v-card-text>
          </v-card>
        </v-col>
      </v-row>
    </section>
  </div>
</template>

<script>
import welcomeBanner from '~/components/welcome-banner.vue'
import cardAvatar from '~/components/card-avatar.vue'
export default {
  components: [welcomeBanner, cardAvatar],
}
</script>

<style scoped>
.wallet-card {
  min-height: 17.5rem;
  display: flex;
}

.wallet-text {
  align-self: center;
  font-size: 1rem;
  font-weight: 500;
}
.acc__bal {
  font-size: 3rem;
}
.balance__label {
  display: inline !important;
  margin-right: 1rem;
  font-weight: 500;
}
.balance-switch {
  margin-top: 0;
}
.acc-num {
  font-weight: 500;
  font-size: 1rem;
}
.block {
  margin: 5rem 0;
}
</style>
