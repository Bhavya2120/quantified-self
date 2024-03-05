<template>
<body>
<div id="Home">
    <h2>Welcome to QuantifiedSelf, {{name}}!</h2> <br>
     <h3>Add trackers to your day-to-day activities and track your progress by adding logs </h3>
             <br>
             <h4>View your current trackers by clicking on the your trackers icon.<br>
            If you have no trackers running currently, get started by adding trackers</h4>
  </div>    </body>  
</template>

<script>
import axios from 'axios';
import { useRouter } from 'vue-router';


export default {
Name: 'HomeView',
mounted() {
    const router = useRouter();
    axios.get('http://localhost:5000/')
    .then((resp ) => console.log(resp.data))
    .catch((err) => {
            console.log(err)
            router.push({name:'login'})
            alert("Token Expired")
    })
},
data() {
    return {
        name: localStorage.name,
    }
},
};

</script>

<style>

.header{    
    top: 0;
    padding: 0;
    margin: 0;
}

body{
    background-color: red 39%, #317773 61%;
}
#Home{
    margin-bottom: 250px;
    color: white;
    
}
</style>