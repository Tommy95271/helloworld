<template>
  <div class="">
    <h1>VueDirective</h1>
    <!-- <button @click.prevent="toggleInputValue">Click me to toggle inputValue</button> -->
    <form class="" v-if="isVisible" @submit="handleSubmit">
      <label for="inputValue">inputValue</label>
      <input
        type="text"
        id="inputValue"
        v-model="inputValue"
        @keyup.enter="consoleLog(inputValue)"
      />
      <span>{{ inputValue }}</span>
      <button type="submit">Submit</button>
    </form>
  </div>
</template>

<script>
export default {
  name: "VueDirective",
  props: {
    msg: String,
  },
  data() {
    return {
      msg1: "test",
      inputValue: "",
      isVisible: true,
    };
  },
  methods: {
    toggleInputValue() {
      this.isVisible = !this.isVisible;
    },
    consoleLog(inputValue) {
      console.log(inputValue);
    },
    handleSubmit() {
      console.log(this.inputValue);
    },
  },
};
</script>