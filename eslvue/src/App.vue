
<template>
  <header>

    
    <div class="wrapper">
      <!-- the page index -->
      <nav class="nav active">
        <RouterLink to="/" @click="redirect">Home</RouterLink>
        <RouterLink to="/About" @click="about">About</RouterLink>
        <RouterLink to="/index"  @click="index">index</RouterLink>
        <RouterLink to="/form" @click="Form">Form</RouterLink>
        <RouterLink to="/jobs" @click="Jobs">Jobs</RouterLink>

      </nav>
    </div>
  </header>

  <!-- <HelloWorld v-if="showResults" :score="score" />
  <ModalView v-if="isPlaying" :delay="delay" @end="endGame" /> -->
  <RouterView />
</template>
<script  lang="ts">
import { RouterLink, RouterView } from 'vue-router'

// import the component
import HelloWorld from './components/HelloWorld.vue'
import ModalView from './components/ModalView.vue';
import Jobs from './views/jobs/Jobs.vue';

export default {

  setup() {
    let name = 'World'
    let age = 20
    return {
      name,
      age,

    }
  },
  // components are the components that are used in the template AND yOU HAVE TO IMPORT THEM
  // IN order to use them
  components: {
    HelloWorld,
    ModalView,
    Jobs,


},
  
  // data is a function that returns an object with the data that is used in the component
  data() {
    return {
      isPlaying: false,
      delay: 0,
      score: 0,
      showResults: false,
    }
  },
  // methods are functions that are called when an event is triggered
  methods: {
    startTimer() {
      this.isPlaying = true
      this.delay = 1000 + Math.random() * 5000
    },
    endGame(reactionTime: number) {
      this.isPlaying = false
      this.showResults = true
      this.score = reactionTime
      console.log(reactionTime)

    },
// $router is a property that is used to navigate between the pages   
// push is a method that is used to navigate to a specific page
    redirect() {
      this.$router.push({name: 'home' })
    },
    about() {
      this.$router.push({name: 'about' })
    },
    index() {
      this.$router.push({name: 'index' })
    },
    Form() {
      this.$router.push({name: 'form' })
    },
    Jobs() {
      this.$router.push({name: 'Jobs' })
    },

  },
}

</script>

<style scoped>
header {
  line-height: 1.5;
  max-height: 100vh;
  width: fit-content;


}

.wrapper{

  position: relative;

}
.logo {
  display: block;
  margin: 0 auto 2rem;
}

nav {
  width: 100%;
  text-align: center;
  font-size: 1.5rem;

}

nav a.router-link-exact-active {
  color: var(--color-text);
  font-size: 1rem;




}
nav a.router-link-exact-active:hover {
  filter: drop-shadow(0 0 0.75rem var(--color-text));
 
}

nav a.router-link-exact-active:hover {
  background-color: transparent;
}

nav a {

padding: 0 0.5rem;
border-left: 1px solid var(--color-border);



}

nav a:first-of-type {
  border: 0;
}

@media (min-width: 1024px) {
  header {
    display: flex;
    place-items: center;
    padding-right: calc(var(--section-gap) / 2);

  }

  .logo {
    margin: 0 2rem 0 0;
  }

  header .wrapper {
    display: flex;
    place-items: flex-start;
  
  }
  nav a {
    padding: 0 1rem;
    border: 0;

  }

  nav {
    text-align: left;
    margin-left: -3rem;
    font-size: 1rem;
    display: flex;
    align-items: flex-start;
    position: fixed;
    top: 0;
    left: 0;
    padding: 1rem 0;
    margin : 3rem 0;


  }
}
</style>
