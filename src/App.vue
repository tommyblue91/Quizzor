<template>
  <div>
    <v-app> 
    <v-content>
<Header />
<Questionbox
v-if="question.length"
:currentQuestion="question[index]"
:next="next"
 />
    </v-content>
    </v-app>
  </div>
</template>


<script>
import Header from './components/Header.vue'
import Questionbox from './components/Questionbox.vue'

export default {
  name: 'App',
  components: {
    Header,
    Questionbox
  },
  data() {
    return {
question: [],
index: 0
    }
  },
  methods: {
    next() {
      this.index++
    }
  },
  mounted: function () {
    fetch('https://opentdb.com/api.php?amount=20&type=multiple', { 
    method: 'get'
    })
    .then ((response) => {
      return response.json()
    })
    .then ((jsonData) => {
      this.question = jsonData.results
    })
  }
} 

</script>