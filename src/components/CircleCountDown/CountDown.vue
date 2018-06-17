<template>
  <div class="timer-container">
    <CircleWithTextInside :percentage="daysPrecent">
      <div style="display:flex;flex-flow:column">
        <span class="timer-number">{{ days }}</span>
        <span class="timer-number-text">DAYS</span>
      </div>
    </CircleWithTextInside>
    <CircleWithTextInside :percentage="hoursPrecent">
      <div style="display:flex;flex-flow:column">
        <span class="timer-number">{{ hours }}</span>
        <span class="timer-number-text">HOURS</span>
      </div>
    </CircleWithTextInside>
    <CircleWithTextInside :percentage="minutesPrecent">
      <div style="display:flex;flex-flow:column">
        <span class="timer-number">{{ minutes }}</span>
        <span class="timer-number-text">MINS</span>
      </div>
    </CircleWithTextInside>
    <CircleWithTextInside :percentage="secondsPrecent">
      <div style="display:flex;flex-flow:column">
        <span class="timer-number">{{ seconds }}</span>
        <span class="timer-number-text">SECS</span>
      </div>
    </CircleWithTextInside>
    <!-- <span>:</span>
    <span>{{hours}}</span>
    <span>:</span>
    <span>{{minutes}}</span>
    <span>:</span>
    <span>{{seconds}}</span> -->
  </div>
</template>

<script>
import CircleWithTextInside from "./CircleWithTextInside";
export default {
  components: {
    CircleWithTextInside
  },
  props: {
    date: {}
  },
  data() {
    return {
      interval: 0,
      secs: 0,
      s: 0,
      mm: 0,
      hh: 0,
      dd: 0
    };
  },
  computed: {
    days() {
      return this.dd < 10 ? "0" + this.dd : this.dd;
    },
    hours() {
      return this.hh < 10 ? "0" + this.hh : this.hh;
    },
    minutes() {
      return this.mm < 10 ? "0" + this.mm : this.mm;
    },
    seconds() {
      return this.s < 10 ? "0" + this.s : this.s;
    },
    daysPrecent() {
      let val = Math.floor(this.dd / 365 * 100);
      return val > 100 ? 100 : val;
    },
    hoursPrecent() {
      let val = Math.floor(this.hh / 24 * 100);
      return val;
    },
    minutesPrecent() {
      let val = Math.floor(this.mm / 60 * 100);
      return val;
    },
    secondsPrecent() {
      let val = Math.floor(this.s / 60 * 100);
      return val;
    },
  },
  methods: {
    startTimer() {
      this.secs =
        Math.floor(this.date.getTime() / 1000) - Math.floor(Date.now() / 1000);

      clearInterval(this.interval);
      this.interval = setInterval(() => {
        if (this.secs <= 0) {
          this.secs = 0;
          this.generateCountDown();
          clearInterval(this.interval);
        } else {
          this.secs--;
          this.generateCountDown();
        }
      }, 1000);
    },
    generateCountDown() {
      var days = Math.floor(this.secs / (60 * 60 * 24));
      var hours = Math.floor((this.secs % (60 * 60 * 24)) / (60 * 60));
      var minutes = Math.floor((this.secs % (60 * 60)) / 60);
      var seconds = Math.floor(this.secs % 60);

      this.dd = days;
      this.hh = hours;
      this.mm = minutes;
      this.s = seconds;
    }
  },
  created() {
    this.startTimer();
  },
  watch: {
    date() {
      this.startTimer();
    }
  },
  beforeDestroy() {
    clearInterval(this.interval);
  }
};
</script>

<style>

</style>
