<template>
    <b-container>
      <b-card>
        <b-form @submit.prevent="submitForm">
          <b-form-group label="Nombre del Sondeo" label-for="nombre">
            <b-form-input
              id="nombre"
              v-model="formData.nombre"
              :state="!$v.formData.nombre.$error"
              @input="clearValidation('nombre')"
              required
            ></b-form-input>
            <b-form-invalid-feedback v-if="$v.formData.nombre.$error">
              El nombre del sondeo es requerido.
            </b-form-invalid-feedback>
          </b-form-group>
  
          <b-form-group label="Fecha de Publicación" label-for="fechaPublicacion">
            <b-form-datepicker
              id="fechaPublicacion"
              v-model="formData.fechaPublicacion"
              :state="!$v.formData.fechaPublicacion.$error"
              @input="clearValidation('fechaPublicacion')"
              required
            ></b-form-datepicker>
            <b-form-invalid-feedback v-if="$v.formData.fechaPublicacion.$error">
              La fecha de publicación es requerida.
            </b-form-invalid-feedback>
          </b-form-group>
  
          <b-form-group label="Fecha de Finalización" label-for="fechaFinalizacion">
            <b-form-datepicker
              id="fechaFinalizacion"
              v-model="formData.fechaFinalizacion"
              :state="!$v.formData.fechaFinalizacion.$error"
              @input="clearValidation('fechaFinalizacion')"
              required
            ></b-form-datepicker>
            <b-form-invalid-feedback v-if="$v.formData.fechaFinalizacion.$error">
              La fecha de finalización es requerida.
            </b-form-invalid-feedback>
          </b-form-group>
  
          <b-form-group label="Imagen" label-for="imagen">
            <b-form-file
              id="imagen"
              v-model="formData.imagen"
              @input="clearValidation('imagen')"
              placeholder="Seleccionar imagen"
              accept="image/*"
              required
            ></b-form-file>
            <b-form-invalid-feedback v-if="$v.formData.imagen.$error">
              Debes seleccionar una imagen.
            </b-form-invalid-feedback>
          </b-form-group>
  
          <!-- Otros campos del formulario -->
  
          <b-button type="submit" variant="primary">Guardar</b-button>
        </b-form>
      </b-card>
    </b-container>
  </template>
  
  <script>
  export default {
    data() {
      return {
        formData: {
          nombre: "",
          fechaPublicacion: null,
          fechaFinalizacion: null,
          imagen: null,
          // Otros campos aquí...
        },
      };
    },
    methods: {
      async submitForm() {
        // Lógica para enviar el formulario al servidor aquí
        console.log('Datos del formulario:', this.formData);
        await axios.post('registro_usuario', this.formData)
        .then(response => {
            console.log(response)
        })
        .catch(error => {
            console.log(error)
        })
      },
      clearValidation(field) {
        // Limpia los mensajes de validación del campo especificado
        this.$v.formData[field].$reset();
      },
    },
  };
  </script>
  