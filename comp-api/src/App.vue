<script setup lang="ts">
import { RouterLink, RouterView } from 'vue-router'
// import * as Form from './views/HomeView.vue'
import { computed, reactive, ref, toRefs } from 'vue'

const name = ref('')
const email = ref('')
const age = ref('')
// the difference between ref and reactive is that ref is a single value and reactive is an object
const state = reactive({
  name: '',
  email: '',
  age: ''
})
const search = ref('')
const names = reactive(
  [
    'John',
    'Jane',
    'Jill',
    'Jack',
    'Jenny',
    'Jen',


  ]
)


// computed is a function that returns a value based on the value of another value
const filteredNames = computed(() => {
  return names.filter((name) => 
     name.toLowerCase().includes(search.value.toLowerCase())
  )
})

// save the state to a json file
const saveState = () => {
  const data = JSON.stringify(state)
  localStorage.setItem('state', data)
  return data
  // save the data to a file

}


const handleClick = () => {
  name.value = state.name
  email.value = state.email
  age.value = state.age
  saveState()


}
</script>

<template>
  <header>


    <div class="wrapper">

      <div>
        <input type="text" v-model="search" placeholder="Search" />
        <button  @click="filteredNames.keys" type="button" class="bg-blue-500 text-white p-2 rounded">
          Submit
     
        </button>
        <ul>
          <li v-for="name in filteredNames" :key="name">
            <p class="bg-yellow" v-if="name">
              {{ name }}

            </p>
            <span v-else class="text-2xl">
              No results
            </span>
          </li>
        </ul>

      </div>
      <p class="text-2xl">
        My Name is {{ name }} and I am {{ age }} years old
        and my email is {{ email }}

      </p>
      <form class="form flex flex-col gap-4 mt-4 w-1/2 mx-auto">
        <input type="text" v-model="state.name" placeholder="Name" />
        <input type="text" v-model="state.email" placeholder="Email" />
        <input type="text" v-model="state.age" placeholder="Age" />
        <button @click="handleClick" type="button" class="bg-blue-500 text-white p-2 rounded">
          Submit
        </button>
      </form>
    </div>

  </header>

  <RouterView />
</template>

<style scoped></style>
