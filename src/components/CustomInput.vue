<template>
  <div class="custom-input">
    <label :for="name">{{ label }}</label>
    <input
      type="text"
      :disabled="disabled"
      :id="name"
      :name="name"
      v-model="myinput"
    />
    <p>{{ myinput || "error" }}</p>
  </div>
</template>

<script>
export default {
  name: "CustomInput",
  data() {
    return {
      myinput: this.value,
    };
  },
  props: {
    disabled: Boolean,
    name: String,
    label: String,
    value: String,
  },
};
</script>
