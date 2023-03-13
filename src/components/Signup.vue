<template>
    <form @submit.prevent="onSubmit" class="add-form">
      <div class="form-control">
        <label>First Name</label>
        <input type="text" v-model="Fname" name="firstName" placeholder="First Name" />
      </div>
      <div class="form-control">
        <label>Last Name</label>
        <input type="text" v-model="Lname" name="lastName" placeholder="Last Name" />
      </div>
      <div class="form-control">
        <label>Phone Number</label>
        <input
          type="text"
          name="day"
          v-model="Phone"
          placeholder="Phone Number"
        />
      </div>
  
      <input type="submit" value="Sign Up" class="btn btn-block" />
    </form>
</template>


<script>
import axios from 'axios'
export default{
    name:'SignUp',
    data() {
        return{
            Fname:'',
            Lname:'',
            Phone:'',
        }
    },
    methods:{
        async onSubmit(){
          const res = await axios.post('http://localhost/barbershop/api/costumer/create.php', {
              first_name : this.Fname,
              last_name: this.Lname,
              phone: this.Phone
          })
            if(!this.Fname){
                alert('Insert Your First Name')
                return
            }
            if(!this.Lname){
                alert('Insert Your Last Name')
                return
            }
            if(!this.Phone){
                alert('Insert Your Phone Number')
                return
            }
        }
    }
}

</script>

<style scoped>
.add-form {
  position: absolute;
  top: 27%;
  left: 58%;
  background-color: white;
  width: 300px;
  padding: 10px 30px;
  border-radius: 10px;
}
.form-control:first-child {
  margin: 10px 0;
}
.form-control {
  margin: 20px 0;
}
.form-control label {
  display: block;
  margin-left: 5px;  
  color: black;
}
.form-control input {
  width: 280px;
  height: 30px;
  margin: 5px;
  padding: 3px 7px;
  font-size: 17px;
  border-radius: 10px;
  border-color: rgba(0, 0, 0, 0.231) ;
}
</style>
