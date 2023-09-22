<template>
    <b-container>
      <main>
        <div class="py-5 text-center">
          <h2>¡Regístrate y Haz la Diferencia!</h2>
          <p class="lead">
            La participación ciudadana es esencial para construir una sociedad más inclusiva y democrática. Tu voz importa, y queremos asegurarnos de que se escuche.
          </p>
        </div>
  
        <b-row>
          <b-col cols="12" md="7" lg="8">
            <b-form @submit.prevent="submitForm" novalidate>
              <b-row>
                <template v-for="(field, label) in formFields">
                  <b-col :cols="field.cols" :sm="field.sm" :key="label">
                    <b-form-group :label="label" :label-for="label">
                      <template v-if="field.type === 'select'">
                        <b-form-select v-model="formData[label]" :id="label">
                          <option value="">{{ field.placeholder }}</option>
                          <option v-for="option in field.options" :value="option.value">{{ option.text }}</option>
                        </b-form-select>
                      </template>
                      <template v-else>
                        <b-form-input v-model="formData[label]" :id="label" :type="field.type" :required="field.required"></b-form-input>
                      </template>
                    </b-form-group>
                  </b-col>
                </template>
              </b-row>
              <hr class="my-4">
              <b-button type="submit" variant="primary" class="w-100">Registrar</b-button>
            </b-form>
          </b-col>
        </b-row>
      </main>
    </b-container>
  </template>
  
  <script>
  export default {
    data() {
      return {
        formData: {
          tipo_documento: "",
          numero_documento: "",
          nombres_completos: "",
          apellidos_completos: "",
          sexo: "",
          email: "",
          telefono: "",
          telefono_fijo: "",
          municipio: "",
          direccion: "",
          barrio: "",
          fecha_nacimiento: "",
          etnia: "",
          condicion_discapacidad: "",
          estrato_residencia: "",
          regimen_afiliacion: "",
          acceso_dispositivos: "",
          conectividad_internet: "",
        },
        formFields: {
          "Tipo documento": {
            type: "select",
            cols: "12",
            sm: "6",
            options: [
              { text: "Seleccionar...", value: "" },
              { text: "Cédula de Ciudadanía", value: "CC" },
              { text: "Tarjeta de Identidad", value: "TI" },
              { text: "Cédula de Extranjería", value: "CE" },
            ],
            placeholder: "Seleccionar...",
            required: true,
          },
          "Número Documento": {
            type: "text",
            cols: "12",
            sm: "6",
            required: true,
          },
          "Nombres Completos": {
            type: "text",
            cols: "12",
            required: true,
          },
          "Apellidos Completos": {
            type: "text",
            cols: "12",
            required: true,
          },
          "Sexo": {
            type: "select",
            cols: "12",
            options: [
              { text: "Seleccionar...", value: "" },
              { text: "Masculino", value: "Masculino" },
              { text: "Femenino", value: "Femenino" },
              { text: "Otro", value: "Otro" },
            ],
            placeholder: "Seleccionar...",
            required: true,
          },
          "Email": {
            type: "email",
            cols: "12",
            required: true,
          },
          "Teléfono": {
            type: "number",
            cols: "12",
            sm: "6",
            required: true,
          },
          "Teléfono Fijo": {
            type: "number",
            cols: "12",
            sm: "6",
            required: true,
          },
          "Municipio": {
            type: "text",
            cols: "12",
            required: true,
          },
          "Dirección": {
            type: "text",
            cols: "12",
            required: true,
          },
          "Barrio": {
            type: "text",
            cols: "12",
            required: true,
          },
          "Fecha de Nacimiento": {
            type: "date",
            cols: "12",
            required: true,
          },
          "Etnia": {
            type: "text",
            cols: "12",
            required: true,
          },
          "Condición de Discapacidad": {
            type: "text",
            cols: "12",
            required: true,
          },
          "Estrato de Residencia": {
            type: "number",
            cols: "12",
            sm: "6",
            required: true,
          },
          "Tipo de Regimen de Afiliación": {
            type: "text",
            cols: "12",
            required: true,
          },
          "Cuenta con acceso a dispositivos Tecnológicos": {
            type: "select",
            cols: "12",
            options: [
              { text: "Seleccionar...", value: "" },
              { text: "Sí", value: "Si" },
              { text: "No", value: "No" },
            ],
            placeholder: "Seleccionar...",
            required: true,
          },
          "Cuenta con conectividad a internet": {
            type: "select",
            cols: "12",
            options: [
              { text: "Seleccionar...", value: "" },
              { text: "Sí", value: "Si" },
              { text: "No", value: "No" },
            ],
            placeholder: "Seleccionar...",
            required: true,
          },
        },
      };
    },
    methods: {
      submitForm() {
        // Agregar la lógica para enviar los datos del formulario al servidor aquí
        console.log("Datos del formulario:", this.formData);
      },
    },
  };
  </script>
  
  <style>
    .bd-placeholder-img {
      font-size: 1.125rem;
      text-anchor: middle;
      -webkit-user-select: none;
      -moz-user-select: none;
      user-select: none;
    }
  
    @media (min-width: 768px) {
      .bd-placeholder-img-lg {
        font-size: 3.5rem;
      }
    }
  </style>
  