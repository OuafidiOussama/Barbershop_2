<template>
    <section>
        <img src="../assets/barber-shop-5212059_1920.jpg" alt="">
        <div>
            <h2>Welcome To MonSalonline</h2>
            <p>Make your shaving process easier with us. Easy, Quick, And Reliable</p>
            <Button @btn-click="$emit('toggle-signup')" text="Sign up" color="blueviolet"/>
        </div>
    </section>
</template>

<script>
import Button from './Button'
export default {
    components:{
        Button,
    },
}

</script>

<style scoped>
section img{
    position: absolute;
    top: 0;
    left: 0;
    z-index: -1;
    width: 100%;
    height: 100vh;
    object-fit: cover;
}
div{
    width: 45%;
    position: relative;
    top:100px;
    left: 40px;
    display: flex;
    flex-direction: column;
    align-items: center;
}
h2{
    font-size: 40px;
}
p{
    transform: translateY(-30px);
    font-size: 20px;
    text-align: center;
    width: 80%;
}
</style>