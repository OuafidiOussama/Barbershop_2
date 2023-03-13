<template>
    <form @submit="onSubmit" class="add-form">
      <div class="form-control">
        <label>Identifier</label>
        <input type="text" v-model="ident" name="identifier" placeholder="Identifier" />
      </div>
      
  
      <input type="submit" value="login" class="btn btn-block" />
    </form>
</template>


<script>
export default{
    name:'Login',
    data() {
        return{
            ident:'',

        }
    },
    methods:{
        onSubmit(e){
            e.preventDefault()
            if(!this.ident){
                alert('Insert Your Identifier')
                return
            }


            const Login= {
                id : '',
                ident: this.ident
            }

            this.$emit('login', Login)

            this.ident= ''
        }
    }
}

</script>

<style scoped>
.add-form {
  position: absolute;
  top: 40%;
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
