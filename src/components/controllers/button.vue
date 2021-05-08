<template>
  <button class="my-button" :class="{ isBlue: isRed}" @click="incriment">
      {{ title }}
      {{ count }}
  </button>
</template>

<script>
export default {
    name: 'CustomButton',
    props: {
        title: String,
        isRed: Boolean,
    },
    data() {
        return {
            count: 1,
        }
    }, 
    methods: {
        incriment() {
            // console.log('tick');
            this.count +=1;
        }
    }
}
</script>

<style lang="scss">
    .my-button {
        height: 30px;
        width: 150px;
        background-color: green;
        border-radius: 5px;
        opacity: 0.8;
        outline: none;
        margin: 10px;
        color: whitesmoke;
        font-weight: 500;
        &:hover {
            opacity: 1;
            cursor: pointer;
        }
    }
    .isBlue {
        background-color: blue;
    }
</style>