<template
    ><div class="shadow-xl max-w-sm border-2 p-5 mx-auto rounded-xl">
        <div class="flex justify-between">
            <h1 class="text-2xl mb-3 font-bold">Results</h1>
            <i
                @click="resetQuiz"
                class="fa-solid fa-arrow-rotate-right pt-2 pr-2"></i>
        </div>
        Correct answers:
        {{
            questions.filter((question) => {
                if (question.correct_answer === question.selected_answer)
                    return true;
                return false;
            }).length
        }}/{{ questions.length }}</div
    >
</template>
<script>
export default {
    name: 'Result',
    props: {
        questions: Array,
    },
    methods: {
        resetQuiz() {
            // Emit an event to inform the parent component to reset the quiz
            this.$emit('reset-quiz');
        },
    },
};
</script>
