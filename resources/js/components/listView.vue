<template>
  <div>
      <div v-for="(item, index) in items" :key="index">
          <listitem
          :item="item"
          v-on:reloadTodos="getTodos()"
          class="item"
          />
      </div>
  </div>
</template>

<script>
import listitem from './listItem.vue'

export default {
    components: {
        listitem
    },
    data: function(){
        return{
            items: []
        }
    },
    methods: {
        getTodos() {
            axios.get('api/todos').then(response=> {
                if(response.status ===200){
                    this.items = response.data.todos
                }
            })
        }
    },
    created() {
        this.getTodos()
    }

}
</script>

<style>
.item {
    border-style: solid;
    border-color: blue;
    border-radius: 7px;
    border-width: 1px;
    outline: none;
    padding: 5px;
    height: 30px;
    width: 100%;
    margin-top: 5px;
}
</style>