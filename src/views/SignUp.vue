<template>
  <div> 
    <h1>Sign Up</h1>
    <CustomInput v-on:change-in-input="getName"/>
    <CustomInput v-on:change-in-input="getSurname"/>
    <button class="my-button" @click="submit">
      One button
    </button>
  </div>
</template>

<script>
import CustomInput from '../components/controllers/input';
// import axios from 'axios';
import apiService from '../helpers/api';


export default {
  name: 'SignUp',
  components: {
    CustomInput,
  },
  data() {
    return {
      dataForSubmit: {
        fname: '',
        lname: '',
        active: true,
      }
    }
  },
  methods: {
    async submit () {
     // await axios.get('http://localhost:3001/user/1').then((res) => console.log(res, 'res')).cath((err) => console.log(err, 'err'));
      //console.log(this.dataForSubmit);
      apiService.post('/user', this.dataForSubmit)
        .then(() => {
          this.$router.push('users');//after add users - redirect to users
        })
        .catch((err) => {
          alert(err.response.data)
        });
    },
    getName(data) {
      this.dataForSubmit.fname = data
    },
    getSurname(data) {
      this.dataForSubmit.lname = data
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