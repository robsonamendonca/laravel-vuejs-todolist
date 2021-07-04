<template>
  <div>
      <h1 class="title">Todo List</h1>
      <div class="todoListContainer">
          <add-itemform/>
          <list-view/>
      </div>
  </div>
</template>

<script>

import addItemform from './addItemform.vue'
import listView from './listView.vue'

export default {
    components: {
        addItemform,
        listView
    }
}
</script>

<style scoped>
.title{
    margin-top: 200px;
    text-align: center;
}

.todoListContainer{
    width: 400px;
    margin: auto;
    margin-top: 50px;
}
</style>