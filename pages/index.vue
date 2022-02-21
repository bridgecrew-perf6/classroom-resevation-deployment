<template>
  <v-container class="idx">
    <v-row class="welcome">
      <v-col cols="3" align-self="center">
        <home-calendar />
      </v-col>
      <v-col align-self="center">
        <home-kinesis />
      </v-col>
    </v-row>
    <v-row class="meethip">
      <v-col class = "mt-8" cols="3" align-self="center" >
        <meethip-kinesis />
      </v-col>
    </v-row>
    <v-row class="contact">
      <v-col>
        <home-contact />
      </v-col>
    </v-row>
  </v-container>
</template>

<script>
import meethipKinesis from '~/components/kinesis/meethip-kinesis.vue'
export default {
  components: { meethipKinesis },
}
</script>

<style lang="scss" scoped>
.meethip {
  height: 35%;
}
.idx {
  height: 100%;
}
.contact {
  height: 10%;
}
.welcome {
  height: 48%;
}
</style>
