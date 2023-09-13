<template>
    <ul>
        <li
            v-for="(answer, index) in question.answers"
            @click="selectedAnswer(index)"
            :key="index"
            class="p-2 my-1 rounded-md"
            :class="{
                'bg-green-300':
                    question.selected_answer !== null &&
                    index === question.correct_answer,
                'bg-red-500':
                    question.selected_answer !== null &&
                    index === question.selected_answer &&
                    index !== question.correct_answer,
                'hover:bg-gray-600 hover:text-white':
                    question.selected_answer == null,
            }">
            {{ answer }}
        </li>
    </ul>
</template>

<script>
export default {
    name: 'Answers',
    props: {
        question: Object,
    },
    methods: {
        selectedAnswer(index) {
            if (this.question.selected_answer != null) return false;
            this.question.selected_answer = index;
            this.$emit('on-selected-answer', index);
            console.log(index, this.question);
        },
    },
};
</script>
