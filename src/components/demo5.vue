<template>
    <h1>Supense</h1>
    <Suspense>
        <template #default>
            <AsyncComponent :timeout="3000" />
        </template>
        <template #fallback>
            <h1>加载中</h1>
        </template>
    </Suspense>
</template>

<script>
import AsyncComponent from "./demo5-async.vue";
export default {
    components: {
        AsyncComponent,
    },
};
</script>