<template>
  <div class="container">
    <h1>Listado de sondeos</h1>

    <b-row>
      <b-col>
        <div class="table-responsive">
          <table class="table table-striped table-hover">
            <thead>
              <tr>
                <th scope="col">Nombre sondeo</th>
                <th scope="col">Preguntas</th>
                <th scope="col">Respuestas</th>
                <th scope="col">Acciones</th>
                <!-- <th scope="col">Ficha</th> -->
              </tr>
            </thead>
            <tbody>
              <tr v-for="item in paginatedItems" :key="item.id">
                <td>{{ item.first_name }}</td>
                <td>
                  <b-button  @click="postProyecto()" variant="success" class="enviar">Agregar</b-button>
                </td>
                <td>
                  <b-button @click="fichaProyectos(item.id)" variant="primary" class="m-1">Ver</b-button>
                </td>
                <td>
                  <b-button @click="editarEntrega(item)" variant="warning" class="m-1 mr-2">
                    <b-icon icon="pencil"></b-icon>
                  </b-button>
                  <b-button @click="eliminarEntrega(item.id)" variant="danger">
                    <b-icon icon="trash"></b-icon>
                  </b-button>
                </td>
              </tr>
            </tbody>
          </table>
          <b-pagination
            v-model="currentPage"
            :total-rows="rows"
            :per-page="perPage"
            aria-controls="my-table"
            class="center"
          ></b-pagination>
        </div>
      </b-col>
    </b-row>
  </div>
</template>

<script>
export default {
  data() {
    return {
      perPage: 5, // Adjust the number of items per page as needed
      currentPage: 1,
      items: [
        { id: 1, first_name: 'Fred', last_name: 'Flintstone' },
        { id: 2, first_name: 'Wilma', last_name: 'Flintstone' },
        { id: 3, first_name: 'Barney', last_name: 'Rubble' },
        { id: 4, first_name: 'Betty', last_name: 'Rubble' },
        { id: 5, first_name: 'Pebbles', last_name: 'Flintstone' },
        { id: 6, first_name: 'Bamm Bamm', last_name: 'Rubble' },
        { id: 7, first_name: 'The Great', last_name: 'Gazzoo' },
        { id: 8, first_name: 'Rockhead', last_name: 'Slate' },
        { id: 9, first_name: 'Pearl', last_name: 'Slaghoople' },
        
        { id: 1, first_name: 'Fred', last_name: 'Flintstone' },
        { id: 2, first_name: 'Wilma', last_name: 'Flintstone' },
        { id: 3, first_name: 'Barney', last_name: 'Rubble' },
        { id: 4, first_name: 'Betty', last_name: 'Rubble' },
        { id: 5, first_name: 'Pebbles', last_name: 'Flintstone' },
        { id: 6, first_name: 'Bamm Bamm', last_name: 'Rubble' },
        { id: 7, first_name: 'The Great', last_name: 'Gazzoo' },
        { id: 8, first_name: 'Rockhead', last_name: 'Slate' },
        { id: 9, first_name: 'Pearl', last_name: 'Slaghoople' }
      ]
    };
  },
  computed: {
    rows() {
      return this.items.length;
    },
    paginatedItems() {
      const startIndex = (this.currentPage - 1) * this.perPage;
      const endIndex = startIndex + this.perPage;
      return this.items.slice(startIndex, endIndex);
    }
  },
  methods: {
    postProyecto() {
      // Add your logic for "Agregar" action here
    },
    fichaProyectos(id) {
      // Add your logic for "Ver" action here using the given "id"
    },
    editarEntrega(item) {
      // Add your logic for "Editar" action here using the given "item"
    },
    eliminarEntrega(id) {
      // Add your logic for "Eliminar" action here using the given "id"
    }
  }
};
</script>
