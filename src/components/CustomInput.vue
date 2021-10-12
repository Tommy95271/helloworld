<template>
  <label for="">{{ label }}</label>
  <input
    :id="id"
    :type="type"
    v-model="inputValue"
  />
  {{ label }}
</template>

<script>
export default {
  name: "CustomInput",
  props: {
    id: Number,
    label: String,
    modelValue: String,
    type: String,
  },
  computed: {
    inputValue: {
      get() {
        return this.modelValue;
      },
      set(value) {
        //   console.log(value);
        this.$emit("update:modelValue", value);
      },
    },
  },
  //   data() {
  //     return {
  //       inputValue: "",
  //       isVisible: true,
  //     };
  //   },
};
</script>