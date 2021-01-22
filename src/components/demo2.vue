<template>
    <h1>{{ state.count }} * 2={{ double }}</h1>
    <h2>{{ num }}</h2>
    <button @click="add">累加</button>
</template>
<script>
import { reactive, computed, ref, onMounted } from "vue";

export default {
    setup() {
        const state = reactive({
            count: 1,
        });
        const num = ref(2);

        function add() {
            state.count += 1;
            num.value += 10;
        }
        const double = computed(() => state.count * 2);

        onMounted(() => {
            console.log("mouted");
        });

        return { state, add, double, num };
    },
};
</script>
