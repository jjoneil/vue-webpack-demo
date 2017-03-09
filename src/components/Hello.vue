<template>
  <div id="hello">
    <li>Year
      <input
        type="number"
        v-on:change="change_year"
        v-bind:value="yearly.toFixed(2)"
      ></input>
    </li>
    <li>Month
      <input
        type="number"
        v-on:change="change_month"
        v-bind:value="(yearly / 12).toFixed(2)"
      ></input>
    </li>
    <li>Week
      <input
        type="number"
        v-on:change="change_week"
        v-bind:value="(yearly / 52).toFixed(2)"
      ></input>
    </li>
    <li>Day
      <input
        type="number"
        v-on:change="change_day"
        v-bind:value="(yearly / 365).toFixed(2)"
      ></input>
    </li>
  </div>
</template>

<!-- Four boxes. Year, Month, Week, Day.
Whatever you enter in one of the boxes for spending amount, it updates the others.
 -->

<script>
export default {
  data () {
    return {
      yearly: 0
    }
  },
  methods: {
    change_year (evt) {
      this.yearly = evt.target.value * 1
    },
    change_month (evt) {
      this.yearly = evt.target.value * 12
    },
    change_week (evt) {
      this.yearly = evt.target.value * 52
    },
    change_day (evt) {
      this.yearly = evt.target.value * 365
    }
  }
}
</script>

<style scoped>
h1, h2 {
  font-weight: normal;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>

