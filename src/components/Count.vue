<script setup>
    import { reactive, ref } from 'vue'

    const state = reactive({ count: 0 });
    const count1 = ref(0);
    const object = {
        foo: ref(1)
    }

    const { foo } = object;

    function increment() {
        state.count++
    }

    function Count2() {
        count1.value++
    }
    function updateFoo() {
        foo.value++;
    }
</script>

<template>
    <button @click="increment">
        {{ state.count }}
    </button>
    <button @click="Count2">
        {{ count1 }}
    </button>
    <button @click="updateFoo">
        {{ foo }}
    </button>
    {{ object.foo }}
</template>
