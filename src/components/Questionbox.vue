<template>
    <div><br>
       <div class="v-jumbotron theme--light" style="height: 500px;">
           <div class="v-jumbotron__wrapper">
               <div class="v-jumbotron__background"></div>
               <div class="v-jumbotron__content">
                   <div class="container fill-height">
                       <div class="layout align-center">
                           <div class="flex">
                               <h3 class="display-2 text-xs-center">Question Box</h3>
                               <hr class="my-3 v-divider theme--light">
                               <div class="title mb-3 text-xs-center">{{ currentQuestion.question}}</div>
                               <div class="container col-lg-2 col-md-3 col-sm-4 col-xs-6" style="text-align:center" >                         
                                <v-list v-for="(answer, index) in answers"
                                 :key="index"
                                 @click.prevent="selectAnswer(index)">
                                 <button type="button" class="v-btn">
                                    <div class="v-btn__content">{{  answer }}</div></button>
                                            
                                </v-list>
                                    <br>  
                                    <button type="button" class="v-btn theme--light info"><div class="v-btn__content">Submit</div></button> <br>
                                <button type="button" @click="next" class="v-btn theme--light info"><div class="v-btn__content">Next</div></button>
                                 
                               </div>

        </div></div></div></div></div></div></div> 
    
</template>
<script>
export default {
    props: {
        currentQuestion: Object,
        next: Function
    },
    data() {
        return {
            selectedIndex:null
        }
    },
    computed: {
        answers() {
           let answers = [...this.currentQuestion.incorrect_answers]
           answers.push(this.currentQuestion.correct_answer)
           return answers
        }
    },
    watch: {
        currentQuestion(){
            this.selectedIndex = null
            this.shuffelAnswers()
        }
    },
  methods: {
      selectAnswer(index) {
          this.selectedIndex = index
      },
//   shuffleAnswers () {
    //   let answers = [...this.currentQuestion.incorrect_answers, this.currentQuestion.correct_answer]
//   },
  mounted() {
      console.log(this.currentQuestion)
  }
}
}
</script>

<style>
.button:hover {
    cursor: pointer;
}

.selected {
    background-color: blue;
}
.correct {
    background-color: green;
}
.incorrect {
    background-color: red;
}
</style>