<template>
  <div> 
    <h1>Sign Up</h1>
    <CustomInput />
    <CustomInput />
    <button class="my-button" @click="submit">
      One button
    </button>
  </div>
</template>

<script>
import CustomInput from '../components/controllers/input';
export default {
  name: 'SignUp',
  components: {
    CustomInput,
  },
  methods: {
    async submit () {
      console.log('tik');
    }  
  }
}
</script>

<style lang="scss" scoped>
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

</style>