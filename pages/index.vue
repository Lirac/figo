<template>
  <div>
    <v-row>
      <v-col cols="12">
        <h2>Hello Frank.</h2>
        <welcome-banner></welcome-banner>
      </v-col>
    </v-row>

    <section class="block">
      <h3>Your wallet</h3>
      <v-row>
        <v-col cols="12" md="6" sm="6">
          <v-card flat>
            <v-card-title>
              <h4 class="bal__heading">Account balance</h4>
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
        <v-col md="3">
          <v-card flat class="wallet-card">
            <card-avatar
              class="wallet-avatar"
              :icon="'mdi-hand-coin'"
            ></card-avatar>
            <h5 class="wallet-text">Apply for Loan</h5>
          </v-card>
        </v-col>
        <v-col md="3" sm="6">
          <v-card flat class="wallet-card">
            <card-avatar :icon="'mdi-swap-horizontal'"></card-avatar>

            <h5 class="wallet-text">Send Money</h5>
          </v-card>
        </v-col>
      </v-row>
    </section>
    <section class="block">
      <h3>Coming features</h3>
      <v-row justify="space-between">
        <v-col cols="6" sm="6" md="2">
          <v-card flat class="features__card">
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
        <v-col cols="6" sm="6" md="2">
          <v-card flat class="features__card">
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
        <v-col cols="6" sm="6" md="2" class="coming-soon">
          <v-card class="features__card" flat>
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
        <v-col cols="6" sm="6" md="2">
          <v-card class="features__card" flat>
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
        <v-col cols="6" sm="6" md="2">
          <v-card class="features__card" flat>
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
import welcomeBanner from '~/components/Welcome-banner.vue'
import cardAvatar from '~/components/Card-avatar.vue'
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
  flex-direction: column;
}

.wallet-text {
  align-self: center;
  justify-self: center;
  font-size: 1rem;
  font-weight: 500;
}

.acc__bal {
  font-size: 3rem;
}

.bal__heading {
  color: #000;
  opacity: 0.5;
  padding: 0;
  margin: 0.5rem 0;
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
  color: var(--color-heading);
  justify-self: flex-end;
}
.features__text {
  opacity: 0.6;
  font-weight: 500;
  justify-content: center;
}

.features__card {
  display: flex;
  flex-direction: column;
  height: 100%;
  overflow: hidden;
  justify-content: space-between;
}
</style>
