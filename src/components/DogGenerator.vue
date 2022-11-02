<template>
  <h3>Random Dog Generator</h3>
  <div>
    <img v-bind:src="image" alt="">
  </div>
  <button v-on:click="generateDog()">Generate</button>
</template>

<script>
import axios from "axios";
export default {
  name: "DogGenerator",
  data () {
    return {
      info: null,
      image: ""
    }
  },
  mounted () {
    document.title = "Random Dog Generator";
    this.generateDog()
  },
  methods: {
    generateDog() {
      axios
      .get('https://dog.ceo/api/breeds/image/random')
      .then(response => (this.image = response.data.message))
    }
  },
}
</script>

