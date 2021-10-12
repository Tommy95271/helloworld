<template>
  <div class="">
    <h1>VueDirective</h1>
    <!-- <button @click.prevent="toggleInputValue">Click me to toggle inputValue</button> -->
    <form class="" v-if="isVisible" @submit.prevent="handleSubmit">
      <label for="inputValue">inputValue</label>
      <custom-input v-for="input in inputs" v-model="input.value" :key="input.id" :id="input.id" :type="input.type" :label="input.label"></custom-input>
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
      inputs: [{ id: 1, label: "Email", value: "", type: "email" },{ id: 2, label: "Password", value: "", type: "password" }],
    };
  },
  methods: {
    toggleInputValue() {
      this.isVisible = !this.isVisible;
    },
    handleSubmit() {
        this.inputs.forEach(e => {
            console.log(e);
        });
    },
  },
};
</script>