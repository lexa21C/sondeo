<template>
  <div role="group">
    <label :for="inputId">{{ label }}</label>
    <b-form-input
      :id="inputId"
      :type="type" 
      v-model="inputValue"
      :state="inputState"
      :aria-describedby="inputId + '-help ' + inputId + '-feedback'"
      :placeholder="placeholder"
      trim
    ></b-form-input>

    <!-- This will only be shown if the input has an invalid state -->
    <b-form-invalid-feedback :id="inputId + '-feedback'">
      {{ invalidFeedbackMessage }}
    </b-form-invalid-feedback>

    <!-- This is a form text block (formerly known as help block) -->
    <b-form-text :id="inputId + '-help'">{{ helpText }}</b-form-text>
  </div>
</template>

<script>
export default {
  props: {
    label: {
      type: String,
      required: true
    },
    inputId: {
      type: String,
      required: true
    },
    inputValue: {
      type: String,
      default: ''
    },
    placeholder: {
      type: String,
      default: 'Enter your text'
    },
    type: { // Prop para el tipo de entrada (text, email, etc.)
      type: String,
      default: 'text' // Puedes establecer el valor predeterminado según tus necesidades
    },
    invalidFeedbackMessage: {
      type: String,
      default: 'Invalid input'
    },
    
  },
  computed: {
    inputState() {
      return this.inputValue.length > 2 ? true : false;
    }
  }
};
</script>
