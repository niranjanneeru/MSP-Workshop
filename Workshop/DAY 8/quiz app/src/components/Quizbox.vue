<template>
    <div class="question-box">
        <b-jumbotron>
            <template v-slot:lead>
                {{question.question}}
            </template>

            <hr class="my-4">
            <b-list-group>
                <b-list-group-item id="list"
                                   v-for="(answer,index) in randomList" :key="index"
                                   @click.prevent="selectedAnswer(index)"
                                   v-bind:class="answerClass(index)">
                    {{answer}}
                </b-list-group-item>
            </b-list-group>
            <b-button variant="primary"
                      @click="submitAnswer"
                      :disabled="selectedIndex === null || answered"
            >Submit
            </b-button>
            <b-button @click="next" variant="success" >Next</b-button>
        </b-jumbotron>
    </div>
</template>

<script>

    export default {
        import  _  from "lodash";
        props: {
            'question': Object,
            next: Function,
            increment: Function
        },computed: {
            randomList(){
                // eslint-disable-next-line vue/no-side-effects-in-computed-properties
                return this.shuffledAnswers.sort(function(){return 0.5 - Math.random()});
            }
        },
        data() {
            return {
                selectedIndex: null,
                shuffledAnswers: [],
                answered: false,
                correctIndex: null
            }
        },
        watch: {
            question: {
                immediate: true,
                handler() {
                    this.answered = false
                    this.selectedIndex = null
                    this.shuffleAnswers()
                }
            }
        }, methods: {
            selectedAnswer(index) {
                this.selectedIndex = index
            },
            answerClass(index) {
                let answeredClass = ''
                if (!this.answered && this.selectedIndex === index) {
                    answeredClass = 'selected'
                } else if (this.answered && this.correctIndex === index) {
                    answeredClass = 'correct'
                } else if (this.answered && this.selectedIndex === index && this.correctIndex !== index) {
                    answeredClass = 'incorrect'
                }
                return answeredClass
            },
            submitAnswer() {
                let isCorrect = false
                if (this.selectedIndex === this.correctIndex) {
                    isCorrect = true
                }
                this.answered = true
                this.increment(isCorrect)
            },
            shuffleAnswers() {
                let answers = [...this.question.incorrect_answers, this.question.correct_answer]
                this.shuffledAnswers = _.shuffle(answers)
                this.correctIndex = this.shuffledAnswers.indexOf(this.question.correct_answer)
            }
        }
    }
</script>

<style scoped>
    .list-group {
        margin-bottom: 15px;
    }

    #list:hover {
        background: #eeeeee;
        cursor: pointer;
    }

    .selected {
        background-color: lightblue;
    }

    .correct {
        background-color: green;
    }

    .incorrect {
        background-color: red;
    }

    .btn {
        margin: 0px 5px;
    }
</style>