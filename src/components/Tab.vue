<template>
    <div class="tab-box">    
        <div class="button-group">
            <button v-for="(gender, index) in genders" :key="gender.name" 
            @click="onGenderSelected(index)">{{ gender.name }}</button>
        </div>

        <GenderComp
            v-if="selectedIndex >= 0"
            v-bind="genders[selectedIndex]"
        />
    </div>
</template>

<script setup lang="ts">
import GenderComp, { type Gender } from './GenderComp.vue'
import { ref, reactive, computed } from 'vue'

const genders: Gender[] = [
    {       
        name: 'Alocasia',
        familyName: 'Arasseae',
        description: 'Beautiful and Green.',
        occurrence: 'Cory',
        image: 'img'
    },    
    {       
        name: 'Monstera Deliciosa',
        familyName: 'Arasseae',
        description: 'Big, strong leaves.',
        occurrence: 'Boombys',
        image: 'img'
    },
    {
        name: 'Lirata',
        familyName: 'Arasseae',
        description: 'Tall clusters.',
        occurrence: 'Borneo',
        image: 'img'
    },
    
]

const selectedIndex = ref(-1)

function onGenderSelected(optionIndex: number) {
    selectedIndex.value = optionIndex
}

</script>

<style>
.button-group {
    padding: 20px;
    display: flex;
    flex-direction: row;
    border-radius: 10px;
    justify-content: space-between;
}

.tab-box {
    width: 400px;
    display: flex;
    flex-direction: column;
    margin-left: auto;
    margin-right: auto;
    padding: 15px;
    border-radius: 10px;
}

</style>