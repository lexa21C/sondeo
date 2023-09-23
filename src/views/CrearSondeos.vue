<template>
  <b-container class="">
    <b-card class="m-2">
      <b-row class="justify-content-center text-center">
        <h1>Crear sondeo</h1>
      </b-row>
      <b-row>
        <b-col>
          <b-form>
            <b-row class="justify-content-center">
              <b-col cols="12" sm="6">
                <b-form-group>
                  <FormInput
                    label="Nombre"
                    inputId="nombre"
                    :inputValue="formData.nombre"
                    :type="'text'"
                    :placeholder="'Ingrese su nombre'"
                    :invalidFeedbackMessage="'Nombre inválido'"
                  />
                </b-form-group>
              </b-col>
              <b-col cols="12" sm="6">
                <FormInput
                  label="Fecha de inicio"
                  inputId="fechaInicio"
                  :inputValue="formData.fechaInicio"
                  :type="'date'"
                  :placeholder="'Selecciona una fecha y hora'"
                  :invalidFeedbackMessage="'Fecha de inicio inválida'"
                />
              </b-col>
              <b-col cols="12">
                <b-form-group label="Subir Imagen">
                  <b-form-file
                    v-model="formData.imagen"
                    accept="image/*"
                    placeholder="Seleccione una imagen"
                    :state="Boolean(formData.imagen)"
                    :size="formData.imagen ? (formData.imagen.size / 1024).toFixed(2) + ' KB' : ''"
                    @input="handleImageUpload"
                  ></b-form-file>
                </b-form-group>
              </b-col>
            </b-row>
          </b-form>
        </b-col>
      </b-row>
      <b-row class="m-3">
        <hr class="my-4">
        <b-button  variant="primary" class="w-100">Crear sondeo</b-button>
      </b-row>
    </b-card>

    <!-- Otros campos de entrada FormInput -->
    <!-- Puedes repetir el proceso para otros campos de entrada -->
  </b-container>
</template>

<script>
import FormInput from '@/components/form-group/FormInput.vue';

export default {
  components: {
    FormInput
  },
  data() {
    return {
      formData: {
        nombre: '',
        fechaInicio: '',
        imagen: null // Initialize the image field as null
        // Otros campos de datos
      }
    };
  },
  methods: {
    handleImageUpload(value) {
      // This method will be called when an image is selected
      // You can access the selected image as value
      // You can perform any additional processing or validation here
      console.log('Selected image:', value);
    },
    registrarSondeos() {
      // Handle the logic for registering sondeos here
      // You can access the form data as this.formData
      console.log('Form Data:', this.formData);
      // Perform the registration logic, e.g., send data to an API
    }
  }
};
</script>

