<template>
    <div :class="containerClass">
      <b-form-group
        :label="labelText"
        label-for="lastName"
        invalid-feedback="Valid last name is required."
      >
        <b-form-input
          id="lastName"
          :aria-placeholder="placeholder"
          v-model="lastName"
          required
        ></b-form-input>
      </b-form-group>
    </div>
  </template>
  
  <script>
  export default {
    props: {
      containerClass: String,
      labelText: String,
      placeholder: String,
    },
    data() {
      return {
        lastName: "",
      };
    },
  };
  </script>
  