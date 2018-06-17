<template>
    <div class="years-slider-container">
        <div class="years" :style="styleYears">
            <span @click="changeYear(year)" :class="['text-year',isSelected(year) &&'selected-text-year']" v-for="year in years" :key="year">{{year}}</span>
        </div>
    </div>
</template>

<script>
export default {
  props: {
    years: {
      type: Array
    },
    selectedYear: {}
  },
  computed: {
    styleYears() {
      let index = this.years.indexOf(this.selectedYear);
      let translateY;

      switch (index) {
        case 0:
          translateY = 23;
          break;
        case 1:
          translateY = 0;

          break;
        case 2:
          translateY = -22;
          break;
      }
      return {
        transform: `translateY(${translateY}%)`
      };
    }
  },
  methods: {
    isSelected(year) {
      return this.selectedYear === year;
    },
    changeYear(year) {
      this.selectedYear = year;
      this.$emit("yearChanged", this.selectedYear);
    }
  }
};
</script>

<style>
.years-slider-container {
  width: 300px;
  height: 300px;
  display: flex;
  flex-flow: column;
  justify-content: center;
  align-items: center;
  overflow: hidden;
  padding: 10px;
}
.years {
  display: flex;
  flex-flow: column;
  justify-content: center;
  align-items: center;
}
.text-year {
  user-select: none;
  cursor: pointer;
  /* Style for "2017" */
  opacity: 0.43;
  color: #1f2e71;
  font-size: 44px;
  font-weight: 700;
}
.selected-text-year {
  cursor: pointer;
  user-select: none;

  color: #1f2e71;
  opacity: 1;
  font-weight: bold;
  font-size: 131px;
}
</style>
