<template>
  <div class="about">
    <b-table :items="items"></b-table>
  </div>
  
</template>

<script>
export default {
  data(){
    return{
      items:[
        {
          id:1,
          name:'Carlos',
          telefone: 36868374,
          ações:''
        },
        {
          id:2,
          name:'Mara',
          telefone: 36828874,
          ações:''
        },
        {
          id:3,
          name:'Ana Paula',
          telefone: 36848974,
          ações:''
        }
      ]
    }
  }
}
</script>
<style>
  .about {
    border-bottom:1px solid red
  }
</style>