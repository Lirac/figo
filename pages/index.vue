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
          <v-card flat>
            <v-card-title>
              <p>Account balance</p>
            </v-card-title>
            <v-card-text>
              <h1 v-if="!hide" class="acc__bal">0.00</h1>
              <h1 v-if="hide" class="acc__bal">X.XX</h1>
              <p class="balance__label">Hide balance</p>
              <v-switch
                v-model="hide"
                class="d-inline-flex balance-switch"
              ></v-switch>
              <div class="d-flex align-center mt-10 mb-4">
                <span class="mr-4 acc-num">Account no: 04675932367</span>
                <v-icon color="#3f4f80">mdi-credit-card-chip</v-icon>
              </div>
            </v-card-text>
          </v-card>
        </v-col>
        <v-col md="3" sm="12">
          <v-card flat class="wallet-card">
            <card-avatar :icon="'mdi-hand-coin'"></card-avatar>
            <v-card-text class="wallet-text">
              <h5>Apply for Loan</h5>
            </v-card-text>
          </v-card>
        </v-col>
        <v-col md="3" sm="12">
          <v-card flat class="wallet-card">
            <card-avatar :icon="'mdi-swap-horizontal'"></card-avatar>
            <v-card-text class="wallet-text">
              <h5>Send Money</h5>
            </v-card-text>
          </v-card>
        </v-col>
      </v-row>
    </section>
    <section class="block">
      <h3>Coming features</h3>
      <v-row class="d-flex" justify="space-between">
        <v-col md="2">
          <v-card flat>
            <card-avatar
              avatar-color="#dfdfdf"
              size="30"
              icon-color="#b5b6b3"
              :icon="'mdi-swap-horizontal'"
            ></card-avatar>
            <v-card-text>
              <p class="text-center features__text">Investment</p>
            </v-card-text>
            <div class="feature-action text-center">
              <p class="pa-0 ma-0 caption">Coming Soon</p>
            </div>
          </v-card>
        </v-col>
        <v-col md="2">
          <v-card flat>
            <card-avatar
              avatar-color="#dfdfdf"
              size="30"
              icon-color="#b5b6b3"
              :icon="'mdi-piggy-bank'"
            ></card-avatar>
            <v-card-text>
              <p class="text-center features__text">Savings</p>
            </v-card-text>
            <div class="feature-action text-center">
              <p class="pa-0 ma-0 caption">Coming Soon</p>
            </div>
          </v-card>
        </v-col>
        <v-col md="2">
          <v-card flat>
            <card-avatar
              avatar-color="#dfdfdf"
              size="30"
              icon-color="#b5b6b3"
              :icon="'mdi-cart'"
            ></card-avatar>
            <v-card-text>
              <p class="text-center features__text">Buy Now pay later</p>
            </v-card-text>
            <div class="feature-action text-center">
              <p class="pa-0 ma-0 caption">Coming Soon</p>
            </div>
          </v-card>
        </v-col>
        <v-col md="2">
          <v-card flat>
            <card-avatar
              avatar-color="#dfdfdf"
              size="30"
              icon-color="#b5b6b3"
              :icon="'mdi-credit-card'"
            ></card-avatar>
            <v-card-text>
              <p class="text-center features__text">Pay Bills</p>
            </v-card-text>
            <div class="feature-action text-center">
              <p class="pa-0 ma-0 caption">Coming Soon</p>
            </div>
          </v-card>
        </v-col>
        <v-col md="2">
          <v-card flat>
            <card-avatar
              avatar-color="#dfdfdf"
              size="30"
              icon-color="#b5b6b3"
              :icon="'mdi-cellphone'"
            ></card-avatar>
            <v-card-text>
              <p class="text-center features__text">Airtime</p>
            </v-card-text>
            <div class="feature-action text-center">
              <p class="pa-0 ma-0 caption">Coming Soon</p>
            </div>
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
  data: () => {
    return {
      hide: false,
    }
  },
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
.feature-action {
  background: #dfdfdf;
  padding: 0.1rem;
  color: var(--color-heading);
}
.features__text {
  opacity: 0.6;
  font-weight: 500;
}
</style>
