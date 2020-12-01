<template>
  <div id="app">
    <b-table striped hover :fields="fields" :items="items">
        <template v-slot:cell(actions)="data">
            <b-button v-b-modal.meu-modal size="sm" class="mr-2" variant="info" @click="editar(data.id)">Editar</b-button>
            <b-button size="sm" variant="danger" @click="excluir(data.id)">Excluir</b-button>

            <b-modal id="meu-modal" title="BootstrapVue">Olá Mundo, eu sou um Modal</b-modal>
        </template>
        </b-table>
  </div>
</template>

<script>
export default {
  data() {
      return {
        items: [
          { id: 1, name: 'Carlos', phone: '3682-5291', address:'New York', email:'carlos@gmail.com', isActive: true },
          /*{ id: 2, name: 'Maria', phone: '3686-8374', address:'San Diego', email:'ana@gmail.com', isActive: true },
          { id: 3, name: 'José', phone: '3682-9745', address:'San Francisco', email:'mara@gmail.com', isActive: true },
          { id: 4, name: 'Carlos', phone: '3682-5291', address:'New York', email:'carlos@gmail.com', isActive: true },
          { id: 5, name: 'Maria', phone: '3686-8374', address:'San Diego', email:'ana@gmail.com', isActive: true },
          { id: 6, name: 'José', phone: '3682-9745', address:'San Francisco', email:'mara@gmail.com', isActive: true }
          */
        ],
        fields: [
          {
            key: 'id',
            label: 'Id',
            sortable: true
          },
          {
            key: 'name',
            sortable: true
          },
          {
            key: 'phone',
            sortable: false
          },
          {
            key: 'address',
            label: 'Address',
          },
          {
            key: 'email',
            label: 'Email',
          },
          {
            key: 'actions',
            label: 'Ações',
          }
        ],
      }
    }
}
</script>