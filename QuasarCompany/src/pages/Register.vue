<template>
  <q-layout>
    <q-page-container>
      <q-page class="container_bg">
        <div class="q-pa-xs">
          <div class="row justify-center">
            <div class="col-7 col-auto">
              <h5 class="text-center my-font text-light-blue-10">Company Details</h5>
              <q-linear-progress rounded size="15px" :value="progress1" color="light-blue-10"></q-linear-progress>
              <div class="row justify-center q-mt-lg q-pt-sm q-col-gutter-y-lg q-col-gutter-x-md">
                <div class="col-8 col-auto">
                  <q-input
                    bg-color="white"
                    v-model="name"
                    outlined
                    dense
                    type="tel"
                    color="light-blue-10"
                    placeholder="Company Name"
                  />
                </div>
                <div class="col-8 col-auto">
                  <q-input
                    bg-color="white"
                    v-model="name"
                    outlined
                    dense
                    type="tel"
                    color="light-blue-10"
                    placeholder="Business Address"
                  />
                </div>
              </div>
              <div class="row justify-center q-mt-xs q-pb-xl q-col-gutter-y-lg q-col-gutter-x-md">
                <div class="col-4 col-auto">
                  <q-input
                    bg-color="white"
                    v-model="name"
                    outlined
                    dense
                    type="tel"
                    color="light-blue-10"
                    placeholder="Email Address"
                  />
                </div>
                <div class="col-4 col-auto">
                  <q-input
                    bg-color="white"
                    v-model="name"
                    outlined
                    dense
                    type="tel"
                    color="light-blue-10"
                    placeholder="Contact Number"
                  />
                </div>
              </div>
              <div class="row justify-center q-mt-xl q-pt-lg q-col-gutter-y-lg q-col-gutter-x-md">
                <div class="col-3 col-auto">
                  <q-btn
                    :loading="loading3"
                    color="blue-grey-3"
                    @click="simulateProgress(4)"
                    style="width: 100%"
                  >
                    Back
                    <template v-slot:loading>
                      <q-spinner-hourglass class="on-left" />Loading...
                    </template>
                  </q-btn>
                </div>
                <div class="col-3 col-auto">
                  <q-btn
                    :loading="loading4"
                    color="light-blue-10"
                    @click="simulateProgress(4)"
                    style="width: 100%"
                  >
                    Next
                    <template v-slot:loading>
                      <q-spinner-hourglass class="on-left" />Loading...
                    </template>
                  </q-btn>
                </div>
              </div>
            </div>
          </div>
        </div>
      </q-page>
    </q-page-container>
  </q-layout>
</template>

<script>
export default {
  data() {
    return {
      progress1: 0.3,
      progress2: 0.9,
      name: "",
      loading3: false,
      loading4: false
    };
  },

  computed: {
    progressLabel1() {
      return (this.progress1 * 100).toFixed(2) + "%";
    },

    progressLabel2() {
      return (this.progress2 * 100).toFixed(2) + "%";
    }
  },
  methods: {
    simulateProgress(number) {
      // we set loading state
      this[`loading${number}`] = true;
      // simulate a delay
      setTimeout(() => {
        // we're done, we reset loading state
        this[`loading${number}`] = false;
      }, 3000);
    }
  }
};
</script>
<style>
.container_bg {
  background: url("~assets/images/background.jpg");
  /* -webkit-background-size: cover; */
  /* -moz-background-size: cover; */
  /* -o-background-size: cover; */
  background-size: cover;
}
</style>