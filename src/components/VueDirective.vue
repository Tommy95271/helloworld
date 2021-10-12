<template>
  <div class="">
    <h1>VueDirective</h1>
    <!-- <button @click.prevent="toggleInputValue">Click me to toggle inputValue</button> -->
    <form class="" v-if="isVisible" @submit.prevent="handleSubmit">
      <label for="inputValue">inputValue</label>
      <custom-input v-model="inputValue" label="test"></custom-input>
      <!-- <span>{{ inputValue }}</span> -->
      <button type="submit">Submit</button>
    </form>
  </div>
</template>

<script>
import CustomInput from "./CustomInput.vue";

export default {
  components: { CustomInput },
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
    handleSubmit() {
      console.log(this.inputValue);
    },
  },
};
</script>