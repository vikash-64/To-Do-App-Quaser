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

          <div class="col-12 q-pb-md">
            <q-input v-model="toDoTask" label="Input Task">
              <template v-slot:append>
                <q-btn round dense flat icon="add" @click="addItem"></q-btn>
              </template>
            </q-input>
          </div>
        </div>
      </q-card-section>

      <q-separator  />
      <q-card-section v-if="toDoList.length > 0" >
        <div class="row justify-center" v-for="(item, index) in toDoList" :key="index">
          <div class="col-8 q-py-md">
            {{ item.value }}
          </div>

          <div class="col-auto q-py-md">
               <q-btn round dense flat icon="done" @click="removeItem(index)"></q-btn>
          </div>

        </div>
      </q-card-section>

      <q-card-section v-else>
        <div class="row justify-center">
          <div class="col-12">
            <div class="text-h6">
              No item in the List
            </div>
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

  methods: {

    addItem() {

      this.toDoList.push({ value: this.toDoTask })

    },


    removeItem(index){

      this.toDoList.splice(index , 1)
       
    }

  }


})
</script>
