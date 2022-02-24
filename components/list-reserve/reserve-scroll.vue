<template>
  <v-row>
    <v-col>
      <v-row>
        <v-col align-self="center" class="d-flex align-content-center">
            Name:
            <span class="data d-inline-block font-weight-bold text-truncate">
              {{ item.name }}
            </span>
        </v-col>
        <v-col align-self="center">
          Room: <strong>{{ item.roomNumber }}</strong>
        </v-col>
        <v-col align-self="center">
          Date:
          <strong>{{ dayjs(item.date).format('DD/MM/YYYY') }}</strong>
        </v-col>
        <v-col align-self="center" class="d-flex align-content-center">
          Description:
          <span class="data d-inline-block font-weight-bold text-truncate">
            {{ item.description }}
          </span>
        </v-col>
      </v-row>
      <v-row>
        <v-col align-self="center">
          Time:
          <v-chip
            v-for="(i, index) in item.periods"
            :key="index"
            label
            outlined
            class="ml-1"
            color="primary"
            >{{ i.start }} - {{ i.end }}
          </v-chip>
        </v-col>
        <v-col cols="3" align-self="center">
          <ReserveStatus
            :date="item.date"
            :status="item.cancelled"
            @finish="finish"
          />
        </v-col>
      </v-row>
    </v-col>
    <v-col cols="1" class="text-end" align-self="center">
      <v-btn
        text
        @click="$emit('cancel', item._id)"
        outlined
        large
        color="error"
        :disabled="item.cancelled || finished"
      >
        Cancel
      </v-btn>
    </v-col>
  </v-row>
</template>

<script>
import dayjs from 'dayjs'
import ReserveStatus from './reserve-status.vue'
export default {
  components: { ReserveStatus },
  props: {
    item: Object,
  },
  data: () => ({
    finished: false,
  }),

  methods: {
    finish(value) {
      this.finished = value
    },
    dayjs,
  },
}
</script>

<style lang="scss" scoped>
.data {
  width: 200px;
  min-width: 100px;
  margin-left: 4px;
}
</style>
