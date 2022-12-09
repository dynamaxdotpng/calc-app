<template>
  <v-row justify="center" align="center">
    <v-col cols="12" sm="8" md="6">
      <v-card class="logo py-4 d-flex justify-center">
        Awesome calculator app (test project)
      </v-card>
      <v-card>
        <v-card-title class="headline">
          Let's do some calculations
        </v-card-title>
        <v-card-text>
          <v-text-field
            v-model="value1"
            label="Value 1"
            filled
            type="number"
          />

          <v-select
            v-model="operation"
            :items="operations"
            filled
            label="Operations"
          />

          <v-text-field
            v-model="value2"
            label="Value 2"
            filled
            type="number"
          />

          <v-text-field
            v-model="result"
            label="Result"
            filled
            background-color="green"
            type="number"
            disabled
          />
        </v-card-text>
      </v-card>
    </v-col>
  </v-row>
</template>

<script>
export default {
  name: 'IndexPage',
  data () {
    return {
      value1: null,
      value2: null,
      operation: '+',
      operations: ['+', '-', '×', '÷']
    }
  },
  computed: {
    result () {
      if (isNaN(this.value1) || isNaN(this.value2)) {
        return null
      }

      if (this.operation === '+') {
        return Number(this.value1) + Number(this.value2)
      }

      if (this.operation === '-') {
        return Number(this.value1) - Number(this.value2)
      }

      if (this.operation === '×') {
        return Number(this.value1) * Number(this.value2)
      }

      if (this.operation === '÷') {
        return Number(this.value1) / Number(this.value2)
      }

      return null
    }
  }
}
</script>
