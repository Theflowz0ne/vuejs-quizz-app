<template>
    <div class="max-w-3xl m-5 mx-auto h-screen max-h-fit">
        <QuestionComponent
            v-if="curr_question <= questions.length - 1"
            :currQuestion="curr_question"
            :question="questions[curr_question]"
            @button-click="handleButtonClick" />
        <Result
            v-else
            :questions="questions"
            @reset-quiz="resetQuiz"
            v-cloak
    /></div>
</template>

<script>
import QuestionComponent from './components/QuestionComponent.vue';
import Result from './components/Result.vue';
export default {
    name: 'App',
    components: {
        QuestionComponent,
        Result,
    },
    data() {
        return {
            curr_question: 0,
            questions: [],
        };
    },
    methods: {
        handleButtonClick() {
            this.curr_question += 1;
        },
        async fetchQuestions() {
            const res = await fetch('api/questions');
            const data = await res.json();

            return data;
        },
        resetQuiz() {
            this.curr_question = 0;
            for (const question of this.questions) {
                question.selected_answer = null;
            }
        },
    },
    async created() {
        this.questions = await this.fetchQuestions();
        console.log(this.questions);
    },
};
</script>
<style scoped>
[v-cloak] {
    display: none;
}
</style>
