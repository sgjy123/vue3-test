<script setup>
    import {reactive, computed} from 'vue'
    const author = reactive({
        name: 'John Doe',
        books: [
            'Vue 2 - Advanced Guide',
            'Vue 3 - Basic Guide',
            'Vue 4 - The Mystery'
        ]
    })
    const computedBooks = computed(()=>{
       return author.books.length > 0 ? 'yes' : 'no'
    });
</script>
<template>
    <p>Has published books:</p>
    <span>{{computedBooks}}</span>
</template>
<style scoped>
</style>
