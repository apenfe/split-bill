<template>

    <div class="no-items" v-if="store.people.length === 0">
        No items  
    </div>
    
    <div class="people-view" v-if="store.people.length > 0">

        <header class="header">

            <div>

                <div>
                    <LabelData :title="'Total + Tip: '" :value="getGrandTotal()"/>
                </div>

                <div>
                    <LabelData :title="'Falta por pagar: '" :value="store.params.remaining"/>
                </div>

            </div>

        </header>

        <div class="people-container">

            <PersonData
                v-for="person in store.people" 
                :key="person.id"
                :id="person.id" 
                :number-of-person="person.numberOfPerson" 
                :total-per-person="person.totalPerPerson" 
                :paid="person.paid"
            />

        </div>

    </div>
    
</template>

<script setup>

//import {ref} from 'vue';
import {getGrandTotal, store} from '../store/store'
import LabelData from './LabelData.vue';
import PersonData from './PersonData.vue';



</script>

<style lang="scss">

.no-items{
    width: 100%;
    height: 100%;
    display: flex;
    align-items: center;
    justify-content: center;
    font-size: 28px;
}

.people-view{
    margin: 0px auto;
    display: flex;
    align-items: center;
    flex-direction: column;
}

.people-container{
    width: 800px;
    margin: 0 auto;
    display: grid;
    grid-template-columns: 1fr 1fr 1fr;
    grid-template-rows: auto;
    gap: 10px;
}

.header{
    color: black;
    font-weight: bolder;
    padding: 20px 0;
    font-size: 28px;
    display: flex;
    justify-content: space-between;
    gap: 10px;
    flex-direction: column;
}

</style>