<template>
  <Header title="MonSalonline" @toggle-login="toggleLogin"/>
  <Home  @toggle-signup="toggleSignup"/>
  <div v-show="showSignup">
     <SignUp/>
  </div>
  <div v-show="showLogin">
     <Login/>
  </div>



</template>

<script>
import Header from './components/Header'
import Home from './components/Home'
import SignUp from './components/Signup'
import Login from './components/Login'
export default {
  name: 'App',
  components: {
    Header,
    Home,
    SignUp,
    Login
  },
  methods:{
    toggleSignup(){
      this.showSignup = !this.showSignup
    },
    toggleLogin(){
      this.showLogin = !this.showLogin
    },
    
  },
  data(){
    return{
      showSignup:false,
      showLogin:false,
      Fname: '',
      Lname: '',
      Phone: ''
    }
  }
}
</script>

<style>
body {
  font-family: 'Poppins', sans-serif;
  color: white;
}
.btn{
display: inline-block;
background: #000;
color: #fff;
border: none;
padding: 10px 20px;
margin: 5px;
border-radius: 5px;
cursor: pointer;
text-decoration:none;
font-size:15px;
font-family: inherit;
}
.btn:focus{
  outline: none;
}
.btn:active{
  transform: scale(.98);
}
.btn-block{
  display:block;
  width: 100%;
}

</style>
