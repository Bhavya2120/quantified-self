<template>
    <div class="app">
  
    </div>
  </template>
  
  <script>
  import { useRouter } from 'vue-router'
  import axios from 'axios'
  export default {
  Name: 'LogOut',
  data() {
  },
  created(){
      const router = useRouter();
      const path = 'http://localhost:5000/logout'
      axios.delete(path)
      .then((resp)=>{
          console.log(resp.data)
          router.push({name: 'login'})
          alert('Logged out successfully!')
      })
      .catch((err) => {
            console.log(err)
            router.push({name:'login'}),
            alert('Token expired')

      } )
  }
  
  }
  </script>
  
  <style>
  
  </style>