<template>
    <div>
        <input class="customInput" v-model="text" v-on:input="$emit('change-in-input', text)"/>
        <!-- <p>{{ text }}</p> -->
    </div>
</template>

<script>

export default {
    name: 'CustomInput',
    data() {
        return {
            text: ''
        }
    }    
}

</script>

<style lang="scss">
    .customInput {
        margin: 10px;
        border: 2px solid green;
    }
</style>