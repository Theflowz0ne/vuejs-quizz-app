<template>
    <div class="shadow-xl border-2 p-5 mx-2 rounded-xl">
        <div class="flex justify-between items-start"
            ><h2 class="text-2xl font-bold flex flex-col m-3"
                >Q: {{ question.question }}</h2
            >
            <button
                v-show="question.selected_answer !== null"
                class="text-gray-500 font-semibold px-4 py-2 rounded-lg shadow-md hover:shadow-lg"
                @click="emitButtonClick"
                >Next</button
            ></div
        >

        <p class="font-light italic">Pick the correct answer:</p>
        <Answers :question="question" />
    </div>
</template>

<script>
import Answers from './Answers.vue';

export default {
    name: 'QuestionComponent',
    components: {
        Answers,
    },
    props: {
        currQuestion: Number,
        question: Object,
    },
    methods: {
        emitButtonClick() {
            this.$emit('button-click');
        },
    },
};
</script>
