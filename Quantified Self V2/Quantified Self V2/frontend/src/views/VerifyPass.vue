<template>
    <h1 class="header"> Welcome to QuantifiedSelf</h1>
    <form class="form-signin" @submit.prevent="submit">
 
   <h1 class="h3 mb-3 font-weight-normal reg">Enter your One-Time Password</h1>
 
   
   <input v-model="data.otp" type="name"  class="form-control" placeholder="One Time Password" required autofocus>
   
   <button class="btn btn-lg btn-outline-dark" style="margin-left: 75px;margin-top: 10px;" type="submit">Submit</button>
    </form>
 </template>
 
 <script>
 import { reactive } from "vue"
 import axios from "axios"
 import { useRouter } from "vue-router"
 
 export default {
 Name:'VerifyPass',
 setup() {
    const data = reactive({
      otp: '',
    })
    const router = useRouter();
    const submit = async() => {
    axios.post('http://localhost:5000/verifypass',{
      otp : data.otp
    })
    .then((res) => {
      if(res.data[1]['status']=='666'){
         alert('Wrong OTP!')
         router.push({name:'forgotpass1'})
      }
      else{
         alert('OTP Verified!')
         router.push({name:'changepass'})
      }
    })
   }
    return {
       data,
       submit,
    }
 }
 }
 </script>
 
 <style>
 .header{
    display: flex;
    text-align: center;
    margin-top: 100px;
    margin-bottom: -50px;
    flex: 50%;
    justify-content: center;
 }
 .reg{
    margin-top: 50px;
 }
 </style>