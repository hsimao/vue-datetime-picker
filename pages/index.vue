<template>
  <v-row justify="center" align="center">
    <v-col cols="12" sm="8" md="6">
      <div>
        <client-only>
          <datetime-picker
            v-model="date"
            format="YYYY-MM-DD HH:mm:ss"
            type="datetime"
            value-type="format"
            placeholder="Select date"
            :disabled-date="notAfterToday"
            :disabled-time="notAfterTodayTime"
          />
        </client-only>
        <hr />
        <pre>{{ date }}</pre>
      </div>
    </v-col>
  </v-row>
</template>

<script>
import Logo from '~/components/Logo.vue'
import VuetifyLogo from '~/components/VuetifyLogo.vue'
import DatetimePicker from '~/components/datetime-picker.vue'

export default {
  name: 'IndexPage',
  components: {
    Logo,
    VuetifyLogo,
    DatetimePicker
  },
  data() {
    return {
      date: this.$moment().format('YYYY-MM-DD HH:mm:ss'),
      disabledDate: new Date(),
      disabledTime: new Date()
    }
  },
  methods: {
    notAfterToday(date) {
      return date > new Date(new Date().setHours(0, 0, 0, 0))
    },
    notAfterTodayTime(date) {
      return date > new Date(new Date())
    }
  }
}
</script>
