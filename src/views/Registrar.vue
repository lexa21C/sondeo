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
              <b-col cols="12" sm="6">
                <b-form-group label="Tipo documento" label-for="tipoDocumento">
                  <b-form-select v-model="formData.tipo_documento" id="tipoDocumento">
                    <option value="">Seleccionar...</option>
                    <option value="cedula">Cédula de Ciudadanía</option>
                    <option value="TI">Tarjeta de Identidad</option>
                    <option value="CE">Cédula de Extranjería</option>
                  </b-form-select>
                </b-form-group>
              </b-col>
              <b-col cols="12" sm="6">
                <b-form-group label="Número Documento" label-for="numeroDocumento">
                  <b-form-input v-model="formData.numero_documento" id="numeroDocumento" required></b-form-input>
                </b-form-group>
              </b-col>
              <b-col cols="12" sm="6">
                <b-form-group label="Nombres Completos" label-for="nombresCompletos">
                  <b-form-input v-model="formData.nombres_completos" id="nombresCompletos" required></b-form-input>
                </b-form-group>
              </b-col>
              <b-col cols="12" sm="6">
                <b-form-group label="Apellidos Completos" label-for="apellidosCompletos">
                  <b-form-input v-model="formData.apellidos_completos" id="apellidosCompletos" required></b-form-input>
                </b-form-group>
              </b-col>
              <b-col cols="12">
                <b-form-group label="Sexo" label-for="sexo">
                  <b-form-select v-model="formData.sexo" id="sexo">
                    <option value="">Seleccionar...</option>
                    <option value="Masculino">Masculino</option>
                    <option value="Femenino">Femenino</option>
                    <option value="Otro">Otro</option>
                  </b-form-select>
                </b-form-group>
              </b-col>
              <b-col cols="12">
                <b-form-group label="Email" label-for="email">
                  <b-form-input v-model="formData.correo_electronico" id="email" type="email" required></b-form-input>
                </b-form-group>
              </b-col>
              <b-col cols="12" sm="6">
                <b-form-group label="Teléfono" label-for="telefono">
                  <b-form-input v-model="formData.telefono_celular" id="telefono" type="number" required></b-form-input>
                </b-form-group>
              </b-col>
              <b-col cols="12" sm="6">
                <b-form-group label="Teléfono Fijo" label-for="telefonoFijo">
                  <b-form-input v-model="formData.telefono_fijo" id="telefonoFijo" type="number" required></b-form-input>
                </b-form-group>
              </b-col>
              <b-col cols="12">
                <b-form-group label="Municipio" label-for="municipio">
                  <b-form-input v-model="formData.municipio" id="municipio" required></b-form-input>
                </b-form-group>
              </b-col>
              <b-col cols="12" sm="6">
                <b-form-group label="Dirección" label-for="direccion">
                  <b-form-input v-model="formData.direccion" id="direccion" required></b-form-input>
                </b-form-group>
              </b-col>
              <b-col cols="12" sm="6">
                <b-form-group label="Barrio" label-for="barrio">
                  <b-form-input v-model="formData.barrio_vereda" id="barrio" required></b-form-input>
                </b-form-group>
              </b-col>
              <b-col cols="12" sm="6">
                <b-form-group label="Fecha de Nacimiento" label-for="fechaNacimiento">
                  <b-form-input v-model="formData.fecha_nacimiento" id="fechaNacimiento" type="date" required></b-form-input>
                </b-form-group>
              </b-col>
              <b-col cols="12">
                <b-form-group label="Etnia" label-for="etnia">
                  <b-form-input v-model="formData.etnia" id="etnia" required></b-form-input>
                </b-form-group>
              </b-col>
              <b-col cols="12">
                <b-form-group label="Condición de Discapacidad" label-for="condicionDiscapacidad">
                  <b-form-input v-model="formData.condicion_discapacidad" id="condicionDiscapacidad" required></b-form-input>
                </b-form-group>
              </b-col>
              <b-col cols="12" sm="6">
                <b-form-group label="Estrato de Residencia" label-for="estratoDeResidencia">
                  <b-form-input v-model="formData.estrato_residencial" id="estratoDeResidencia" type="number" required></b-form-input>
                </b-form-group>
              </b-col>
              <b-col cols="12" sm="6">
                <b-form-group label="Ultimo Nivel educativo" label-for="ultimoNivelEducativo">
                  <b-form-input v-model="formData.ultimo_nivel_educativo" id="estratoDeResidencia" type="text" required></b-form-input>
                </b-form-group>
              </b-col>
              <b-col cols="12">
                <b-form-group label="Tipo de Regimen de Afiliación" label-for="regimenAfiliacion">
                  <b-form-input v-model="formData.regimen_afiliacion" id="regimenAfiliacion" required></b-form-input>
                </b-form-group>
              </b-col>
              <b-col cols="12">
                <b-form-group label="Con cuales dispositivos tecnologicos cuentas" label-for="regimenAfiliacion">
                  <b-form-input v-model="formData.dispositivo_tecnologico" id="regimenAfiliacion" required></b-form-input>
                </b-form-group>
              </b-col>
              <!-- <b-col cols="12">
                <b-form-group label="Cuenta con acceso a dispositivos Tecnológicos" label-for="accesoDispositivos">
                  <b-form-select v-model="formData.acceso_dispositivos" id="accesoDispositivos">
                    <option value="">Seleccionar...</option>
                    <option value="Si">Sí</option>
                    <option value="No">No</option>
                  </b-form-select>
                </b-form-group>
              </b-col> -->
              <b-col cols="12">
                <b-form-group label="Cuenta con conectividad a internet" label-for="conectividadInternet">
                  <b-form-select v-model="formData.conectividad_internet" id="conectividadInternet">
                    <option value="">Seleccionar...</option>
                    <option value="Si">Sí</option>
                    <option value="No">No</option>
                  </b-form-select>
                </b-form-group>
              </b-col>
              <b-col cols="12" sm="6" >
                <b-form-group label="Contraseña" label-for="password">
                  <b-form-input id="password" v-model="formData.password" type="password"></b-form-input>
                </b-form-group>
              </b-col>
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
import axios from 'axios'
export default {
  data() {
    return {
      fecha:'',
      formData: {
        tipo_documento: 'Cedula',
        numero_documento: '1002962658222',
        nombres_completos: 'admin',
        apellidos_completos: 'admin',
        sexo: 'Femenino',
        telefono_celular: '315236',
        telefono_fijo: '8302678',
        correo_electronico: 'admin1212@admin.com"',
        municipio: 'Popayan',
        direccion: 'Calle 15',
        barrio_vereda: 'Centro',
        fecha_nacimiento: '1999-07-07',
        etnia: 'Ninguna',
        condicion_discapacidad: 'Ninguna',
        estrato_residencial: '3',
        ultimo_nivel_educativo: 'Doctorado',
        dispositivo_tecnologico: 'Celular',
        conectividad_internet: 'Si',
        regimen_afiliacion: 'Subsidiada',
        password:'1111222',
        password_confirmation: '1111222',
        rol_id: 1,
      },
    };
  },
  methods: {
    async submitForm() {
      // Aquí puedes agregar la lógica para enviar los datos del formulario al servidor
      console.log('Datos del formulario:', this.formData);
      await axios.post('api/registro_usuario', this.formData)
      .then(response => {
        console.log(response)
      })
      .catch(error => {
        console.log(error)
      })
    },
  },
};
</script>

<style scoped>
/* Estilos personalizados para tu formulario */
</style>


