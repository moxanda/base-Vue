<template>
  <div>
    <nav>
      <ul>
        <li><a href="#">Crear Tablero</a></li>
      </ul>
    </nav>
    <div class="boards-container">
      <div class="boards">
        <div class="board" v-for="board in boards" :key="board.id">
          <div>{{board.name}}</div>
          <InputNew @on-new-item="handleNewItem"></InputNew>
          <div class="items">
            <div class="item drag-el" v-for="item in board.items" :key="item.id">
              {{ item.title }}
            </div>
          </div>
        </div>
      </div>
    </div>
    
  </div>
  PPP  RRR UUU EEE BBB AAA
</template>
<script setup>
  import { reactive } from 'vue'
  import InputNew from "./InputNew.vue";
  let boards = reactive(
  [
    { 
      id: crypto.randomUUID(),
      name: 'Tablero 1',
      items: [
        {
          id:  crypto.randomUUID(),
          title: 'Feacture 1 - A'
        },
                {
          id:  crypto.randomUUID(),
          title: 'Feacture 1 - B'
        },
      ]
    },
        { 
      id: crypto.randomUUID(),
      name: 'Tablero 2',
      items: [
        {
          id:  crypto.randomUUID(),
          title: 'Feacture 2 - A'
        },
                {
          id:  crypto.randomUUID(),
          title: 'Feacture 2 - B'
        },
      ]
    },
  ])  
  function handleNewItem(text) {
    console.log(text.value)
  }
</script>

<style scoped>

.boards{
  display: flex;
  gap: 10px;
}

  .board{
    background: #efefef;
    padding: 10px;
}

.items{
  display: flex;
  flex-direction: column;
  gap: 5px;
}
  
.item{
  background-color: white;
  padding: 10px;
  box-sizing: border-box;
}
</style>