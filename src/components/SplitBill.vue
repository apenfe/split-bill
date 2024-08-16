<template>

    <div class="container">

        <InputForm/>
        <PeopleView/>
        
    </div>

</template>

<script setup>

import InputForm from './InputForm.vue';
import PeopleView from './PeopleView.vue';

</script>

<style lang="scss">

.container{
    display: flex;
}

</style>