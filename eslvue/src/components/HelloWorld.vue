<template>
  <div class="greetings">

    <h1>Your score is: {{ score }} ms</h1>
    <h3>You are {{ rank }} </h3>
  </div>
</template>
<script  lang="ts">
export default {
  props: ['score'],
  data() {
    return {
      rank: '',
    }
  },

  mounted() {
    if (this.score < 250) {
      console.log('fast')
      this.rank = 'speed'
    }
    else if (this.score < 1500) {
      console.log('fast')
      this.rank = 'fast';
    }
    else {
      console.log('slower')
      this.rank = 'slow poke';
    }
  },

}

</script>


<style scoped>
h1 {
  font-weight: 500;
  font-size: 2.6rem;
  top: -10px;
}

h3 {
  font-size: 1.2rem;
}

.greetings h1,
.greetings h3 {
  text-align: center;
}

@media (min-width: 1024px) {

  .greetings h1,
  .greetings h3 {
    text-align: left;
  }
}
</style>
