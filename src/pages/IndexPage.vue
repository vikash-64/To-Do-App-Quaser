<template>
  <q-page class="flex flex-center">
    <q-card class="my-card" style="width: 600px;">
      <q-card-section>
        <div class="text-h4">
          To-Do List
        </div>
      </q-card-section>

      <q-card-section>
        <div class="row justify-center">

          <div class="col-12">
            <q-input v-model="toDoTask" label="Input Task">
              <template v-slot:append>
                <q-btn round dense flat icon="add" @click="addItem" ></q-btn>
              </template>
            </q-input>
          </div>
        </div>
      </q-card-section>

      <q-card-section>
        <div class="row justify-center" v-for="(item, index) in toDoList" :key="index">
          <div class="col-8 q-py-md">
            {{ item.value }}
          </div>
        </div>
      </q-card-section>
    </q-card>
  </q-page>
</template>

<script>
import { defineComponent } from 'vue'

export default defineComponent({
  name: 'IndexPage',

  data() {
    return {

      toDoTask: '',

      toDoList: [
        { value: "create an app" },
        { value: "Build an app" }
      ]

    }
  },

  methods:{ 

    addItem(){

      this.toDoList.push({value:this.toDoTask})
       
    }

  }


})
</script>
