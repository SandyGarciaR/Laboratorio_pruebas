<template>
  <div>
    <q-layout view="hHh lpR fFf">

<q-header bordered class="bg-blue-10 text-white">
  <q-toolbar>
    <q-toolbar-title class="q-ml-sm">
      <!-- <q-avatar>
        <img src="">
      </q-avatar> -->
      Fábrica
    </q-toolbar-title>
  </q-toolbar>
</q-header>

<q-page-container>
  <router-view />
</q-page-container>

<q-footer bordered class="bg-black text-white">
  <q-toolbar>
    <q-toolbar-title>
      <div class="text-h6 text-center">© copyright</div>
    </q-toolbar-title>
  </q-toolbar>
</q-footer>

<div class="row">
  <div class="col-4"></div>
  <div class="col-4 text-center text-black text-h4 text-weight-bold">NÓMINA</div>
  <div class="col-4"></div>
  
</div>
<q-separator class="q-my-md  bg-blue-10" style="height: 2px; margin-left: 100px; margin-right: 100px;" />

<div class="row q-my-lg">
  <div class="col-2"></div>
  <div class="col-8">
    <q-btn class="bg-blue-10 text-white" @click="prompt, prompt = true" id="butonAdd">Crear <q-icon name="add"></q-icon> </q-btn>
  </div>
  <div class="col-2"></div>
</div>

<!-- TABLE INFO -->
<div class="row q-mt-md">
            <div class="col-2"></div>
            <div class="col-8 ">
                <q-table style="height: 400px" flat bordered  :rows="rows" :columns="columns" row-key="index"
                    virtual-scroll />
            </div>
            <div class="col-2"></div>
          </div> 

        <q-dialog v-model="prompt">
            <q-card >
              <q-card-section class="bg-blue-10">
                <h5 class="q-mt-sm q-mb-sm text-white text-center text-weight-bold">
                  DILIGENCIA LA INFORMACIÓN
                </h5>
              </q-card-section>
              <div>
                <q-card-section class="q-ma-xs">
                <div>
                  <q-input class="q-mb-md" filled type="text" v-model="name" label="Digite su nombre"></q-input>
                  <q-select filled class="q-mb-md"  v-model="category" :options="options"  label="Seleccione la categoria" />
                  <q-input filled type="number" v-model="hours" label="Digite las horas que trabajo a la semana"></q-input>
                  <div class="q-mb-sm">
                    <br />
                    <q-btn  label="guardar" class="text-white bg-blue-10" @click="postTypePackaing()" />
                    <q-btn class="q-ml-md" label="cerrar" v-close-popup />
                  </div>
                </div>
              </q-card-section>
              </div>
            </q-card>
          </q-dialog>

</q-layout>

  </div>
</template>



<script setup>
import {ref} from 'vue'

let prompt = ref(false)
let name = ref("")
let hours= ref()
let category = ref()
let options =ref([
    {label:"1", value:12000},
    {label:"2", value:17000},
    {label:"3", value:22000}

])
        
let columns = ref([
  {name: 'name',label: 'NOMBRE',field: 'name',align: 'center'},
  {name: 'category', label: 'CATEGORIA', field: 'category',align: 'center',},
  {name: 'hours', label: 'HORAS', field: 'hours',align: 'center',  },
  {name: 'extras', label: 'TOTAL DE EXTRAS', field: 'extras',align: 'center',},
  {name: 'total',  label: 'TOTAL', field: 'total',align: 'center'},

])


let rows = ref([])

function rol() {
  if (category.value=== "1") {
    let totalHours =hours.value-40
    
  }
}


</script>

<style >

</style>
