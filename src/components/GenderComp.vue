<template>
    <div class="gender-content">
        <div>
            <strong>Name: </strong>{{ name }}
        </div>
        <div>
            <strong>Description: </strong>{{ description }}
        </div>
    </div>
</template>

<style>
    .gender-content {
        padding: 20px;
        display: flex;
        flex-direction: column;
        background-color: aquamarine;
        border-radius: 10px;
        align-items: flex-start;
        
    }

</style>

<script setup lang="ts">

export interface Gender {
    name: string,
    familyName: string,
    description: string,
    occurrence: string,
    image: string,
}

defineProps<Gender>()

</script>