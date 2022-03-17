<template>
  <div>
    <v-row>
      <v-col>
        <h2 v-if="e1 === 1">Basic information</h2>
        <h2 v-if="e1 === 2">Work information</h2>
        <h2 v-if="e1 === 3">BVN Authentication</h2>
      </v-col>
    </v-row>
    <v-row>
      <v-col cols="12">
        <v-stepper v-model="e1" class="stepper" flat>
          <v-stepper-header>
            <v-stepper-step color="#86b052" :complete="e1 > 1" step="1">
            </v-stepper-step>

            <v-divider></v-divider>

            <v-stepper-step color="#86b052" :complete="e1 > 2" step="2">
            </v-stepper-step>

            <v-divider></v-divider>

            <v-stepper-step color="#86b052" :complete="e1 > 3" step="3">
            </v-stepper-step>

            <v-divider></v-divider>

            <v-stepper-step color="#86b052" :complete="e1 > 4" step="4">
            </v-stepper-step>

            <v-divider></v-divider>

            <v-stepper-step step="5"></v-stepper-step>
          </v-stepper-header>

          <v-stepper-items>
            <v-stepper-content step="1">
              <v-card flat class="mb-12 stepper__content">
                <v-form>
                  <v-row class="mt-4">
                    <v-col cols="12" md="6">
                      <v-col cols="12">
                        <label class="input__label">Full name *</label>
                        <v-text-field
                          required
                          outlined
                          placeholder="Enter your full name"
                        >
                        </v-text-field>
                      </v-col>

                      <v-col cols="12">
                        <label class="input__label" for="">Gender *</label>
                        <v-btn-toggle
                          mandatory
                          class="toggle__gender"
                          active-class="toggle__active"
                        >
                          <v-btn class="toggle__btn mr-4">Male</v-btn>
                          <v-btn class="toggle__btn">Female</v-btn>
                        </v-btn-toggle>
                      </v-col>

                      <v-col cols="12">
                        <label class="input__label" for=""
                          >Date of Birth *</label
                        >
                        <v-menu
                          v-model="menu"
                          :close-on-content-click="false"
                          :nudge-right="40"
                          transition="scale-transition"
                          offset-y
                          min-width="290px"
                        >
                          <template #activator="{ on }">
                            <v-text-field
                              v-model="date"
                              outlined
                              readonly
                              placeholder="Enter your birth date"
                              v-on="on"
                            />
                          </template>
                          <v-date-picker
                            v-model="date"
                            :max="new Date().toISOString().substr(0, 10)"
                            min="1950-01-01"
                            @input="menu = false"
                          />
                        </v-menu>
                      </v-col>
                    </v-col>
                    <v-col cols="12" md="6">
                      <v-col cols="12">
                        <label class="input__label" for=""
                          >Email Address *</label
                        >
                        <v-text-field
                          required
                          outlined
                          placeholder="Enter your email"
                        >
                        </v-text-field>
                      </v-col>
                      <v-col cols="12">
                        <label class="input__label" for=""
                          >Home Address *</label
                        >
                        <v-textarea
                          outlined
                          required
                          placeholder="Enter your home address"
                        ></v-textarea>
                      </v-col>
                      <v-col col="12">
                        <v-btn
                          color="#86b052"
                          class="text-capitalize white--text"
                          depressed
                          @click="e1 = 2"
                        >
                          next</v-btn
                        >
                      </v-col>
                    </v-col>
                  </v-row>
                </v-form>
              </v-card>
            </v-stepper-content>

            <v-stepper-content step="2">
              <v-card flat class="mb-12 stepper__content">
                <v-form>
                  <v-row dense class="mt-4">
                    <v-col cols="12" md="6">
                      <v-row>
                        <v-col cols="12">
                          <label class="input__label"
                            >Employment Status *</label
                          >
                          <v-select
                            outlined
                            :items="employmentStatus"
                            placeholder="Enter employment status"
                          ></v-select>
                        </v-col>
                        <v-col cols="12">
                          <label class="input__label"
                            >Where do you work? *</label
                          >
                          <v-text-field
                            outlined
                            placeholder="Enter where you work"
                          ></v-text-field>
                        </v-col>
                        <v-col cols="12">
                          <label class="input__label"
                            >Enter your job title *</label
                          >
                          <v-text-field
                            outlined
                            placeholder="Enter job title"
                          ></v-text-field>
                        </v-col>
                        <v-col cols="12" class="text-right d-none d-md-block">
                          <v-btn
                            depressed
                            outlined
                            class="text-capitalize"
                            @click="e1 = 1"
                            >Back</v-btn
                          >
                        </v-col>
                      </v-row>
                    </v-col>
                    <v-col md="5" offset-md="1">
                      <v-row>
                        <v-col cols="12">
                          <label class="input__label" for=""
                            >Monthly Income *</label
                          >
                          <v-text-field
                            required
                            outlined
                            placeholder="Enter amount"
                          >
                          </v-text-field>
                        </v-col>
                        <v-col cols="12">
                          <label class="input__label" for=""
                            >Salary Date *</label
                          >
                          <v-menu
                            v-model="menu2"
                            :close-on-content-click="false"
                            :nudge-right="40"
                            transition="scale-transition"
                            offset-y
                            min-width="290px"
                          >
                            <template #activator="{ on }">
                              <v-text-field
                                v-model="salaryDate"
                                placeholder="Enter salary date"
                                outlined
                                readonly
                                v-on="on"
                              />
                            </template>
                            <v-date-picker
                              v-model="salaryDate"
                              :max="new Date().toISOString().substr(0, 10)"
                              min="1950-01-01"
                              @input="menu2 = false"
                            />
                          </v-menu>
                        </v-col>
                        <v-col cols="12">
                          <label class="input__label">Company Address *</label>
                          <v-text-field
                            outlined
                            placeholder="Enter your office address"
                          ></v-text-field>
                        </v-col>
                        <v-col col="12">
                          <v-btn
                            depressed
                            outlined
                            class="text-capitalize d-sm-none"
                            @click="e1 = 1"
                            >Back</v-btn
                          >
                          <v-btn
                            color="#86b052"
                            class="text-capitalize white--text"
                            depressed
                            @click="e1 = 3"
                          >
                            next</v-btn
                          >
                        </v-col>
                      </v-row>
                    </v-col>
                  </v-row>
                </v-form>
              </v-card>
            </v-stepper-content>

            <v-stepper-content step="3">
              <v-card flat class="mb-12 stepper__content">
                <v-form>
                  <v-row dense class="mt-4">
                    <v-col md="5" sm="12">
                      <v-row>
                        <v-col cols="12">
                          <label class="input__label"
                            >Enter your bank verification number *</label
                          >
                          <v-text-field
                            outlined
                            placeholder="123456789098"
                          ></v-text-field>
                        </v-col>
                        <v-col cols="12" class="text-right">
                          <v-btn
                            depressed
                            outlined
                            class="text-capitalize"
                            @click="e1 = 2"
                            >Back</v-btn
                          >
                        </v-col>
                      </v-row>
                    </v-col>
                    <v-col md="5" offset-md="1" class="d-flex align-end">
                      <v-btn
                        color="success"
                        class="text-capitalize"
                        depressed
                        @click="e1 = 1"
                      >
                        next</v-btn
                      >
                    </v-col>
                  </v-row>
                </v-form>
              </v-card>
            </v-stepper-content>
          </v-stepper-items>
        </v-stepper>
      </v-col>
    </v-row>
  </div>
</template>

<script>
export default {
  data() {
    return {
      e1: 1,
      menu: false,
      menu2: false,
      date: '',
      salaryDate: '',
      employmentStatus: ['Employed', 'Unemployed', 'Self-employed'],
    }
  },
}
</script>

<style scoped>
.stepper {
  background: var(--app-background) !important;
}
.stepper__content {
  background: var(--app-background) !important;
}

.toggle__gender {
  display: flex;
  background: var(--app-background) !important;
}

.toggle__btn {
  flex-basis: 48%;
  text-transform: capitalize;
}
.toggle__active {
  background: var(--app-green) !important;
  color: #fff !important;
}

.input__label {
  color: var(--color-heading);
  opacity: 0.6;
}
</style>
