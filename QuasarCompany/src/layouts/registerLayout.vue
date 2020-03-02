<template>
  <q-layout view="lHh Lpr lFf">
    <div class="backgound_img">
      <q-page-container>
        <router-view />
      </q-page-container>
    </div>
  </q-layout>
</template>

<script>
import EssentialLink from "components/EssentialLink";

export default {
  name: "registerLayout",

  components: {
    EssentialLink
  },

  data() {
    return {};
  }
};
</script>