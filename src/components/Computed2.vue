<script setup>
    import {ref, computed} from 'vue'
    const firstName = ref('John')
    const lastName = ref('Doe')
    const fullName = computed({
        get() {
            return firstName.value + ' ' + lastName.value;
        },
        set(newValue) {
            console.log(newValue);
            [firstName.value, lastName.value] = newValue.split(' ');
        }
    })
</script>
<template>
    <input type="text" v-model="firstName">
    <input type="text" v-model="lastName">
    <input type="text" v-model="fullName">
    <p>{{fullName}}</p>
</template>
<style scoped>
</style>
