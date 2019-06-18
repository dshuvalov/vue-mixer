<template>
  <div>
    R:
    <input type="number" v-model="RValue" min="0" max="255" @change="handleChangeValue">
    <input type="range" v-model="RValue" min="0" max="255" step="1" @change="handleChangeValue">
    <br>G:
    <input type="number" v-model="GValue" min="0" max="255" @change="handleChangeValue">
    <input type="range" v-model="GValue" min="0" max="255" step="1" @change="handleChangeValue">
    <br>B:
    <input type="number" v-model="BValue" min="0" max="255" @change="handleChangeValue">
    <input type="range" v-model="BValue" min="0" max="255" step="1" @change="handleChangeValue">
  </div>
</template>

<script>
export default {
  data() {
    return {
      RValue: 234,
      GValue: 59,
      BValue: 113
    };
  },
  mounted: function() {
    this.$nextTick(() => this.handleChangeValue());
  },
  methods: {
    handleChangeValue() {
      document.body.style.backgroundColor =
        "rgb(" +
        [this.RValue || 0, this.GValue || 0, this.BValue || 0].join(",") +
        ")";
    }
  }
};
</script>