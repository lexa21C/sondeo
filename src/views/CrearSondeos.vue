<template>
    <b-container class="">
        <b-row></b-row>
      <b-card class="m-2">
        <b-row class="justify-content-center">
          <h1>Crear sondeo</h1>
        </b-row>
        <b-row>
          <b-col>
            <b-form>
              <b-row class="justify-content-center">
                <b-col cols="12" sm="6">
                  <FormInput
                    label="Nombre"
                    inputId="nombre"
                    :inputValue="formData.nombre"
                    :type="'text'"
                    :placeholder="'Ingrese su nombre'"
                    :invalidFeedbackMessage="'Nombre inválido'"
                  />
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
              </b-row>
            </b-form>
          </b-col>
        </b-row>
      </b-card>
      <!-- Otros campos de entrada FormInput -->
      <!-- Puedes repetir el proceso para otros campos de entrada -->
    </b-container>
  </template>
  
  
  <script>
  import FormInput from '@/components/form-group/FormInput.vue'; // Asegúrate de que la ruta sea correcta
  
  export default {
    components: {
      FormInput // Registra el componente FormInput para poder usarlo en tu vista
    },
    data() {
      return {
        formData: {
          nombre: '', // Asegúrate de tener los campos de datos correspondientes
          // Otros campos de datos
        }
      };
    }
  };
  </script>
  