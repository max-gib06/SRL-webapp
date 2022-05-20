<template>
  <div>
    <h2 class="text-center mb-3">Timer</h2>
    <ul class="list-group">
      <li class="list-group-item" v-show="timestamp">
        <strong>Timestamp:</strong> {{ timestamp }}
      </li>
      <li class="list-group-item" v-show="date">
        <strong>Date:</strong> {{ date }}
      </li>
      <li class="list-group-item" v-show="time">
        <strong>Time:</strong> {{ time }}
      </li>
      <li class="list-group-item" v-show="year">
        <strong>Current Year:</strong> {{ year }}
      </li>
      <li class="list-group-item" v-show="fulldatetime">
        <strong>Full Date:</strong> {{ fulldatetime }}
      </li>
    </ul>
       <button @click="start">Start</button>
    <button @click="stop">Stop </button>
    <button @click="reset">Reset</button>
     <li class="list-group-item" v-show="formattedElapsedTime">
       <strong>Full Date:</strong> {{ formattedElapsedTime }}
     </li>
  </div>
</template>
<script>

export default {
  name: 'DateComponent',
  data: () => ({
    date: '',
    time: '',
    year: '',
    timestamp: '',
    fulldatetime: '',
    formattedElapsedTime: '',
    timer: undefined
  }),
  methods: {
    printDate: function () {
      return new Date().toLocaleDateString()
    },
    printTime: function () {
      return new Date().toLocaleTimeString()
    },
    printYear: function () {
      return new Date().getFullYear()
    },
    printTimestamp: function () {
      return Date.now()
    },
    printFullDate: function () {
      return new Date()
    }
  },
  mounted: function () {
    this.date = this.printDate()
    this.time = this.printTime()
    this.timestamp = this.printTimestamp()
    this.year = this.printYear()
    this.fulldatetime = this.printFullDate()
    window.setTimeout(function () {
      location.reload()
    }, 60000)
  }
}
</script>
