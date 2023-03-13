<template>
    <header>
        <h1>{{ title }}</h1>
        <Button @btn-click="$emit('toggle-login')" text="Appointements" color="green"/>
    </header>
</template>

<script>
import Button from "./Button"
export default{
    name:'Header',
    props:{
        title: String,
    },
    components:{
        Button,
    },
}
</script>

<style scoped>
header{
    display: flex;
    justify-content: space-between;
    align-items: center;
    padding: 0 20px;
    margin-bottom: 20px;
    border-bottom: 3px solid rgba(0, 0, 0, 0.288);
}
</style>