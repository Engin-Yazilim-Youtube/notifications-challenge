<script setup>
import Button from "./Button.vue"
import { ref } from "vue"
 
const showContainer = ref(true)

const clickHandler = () => {
    showContainer.value = false
}
</script>

<template>
    <div v-if="showContainer" class="container">
        <div class="close">
            <img src="../assets/close.svg">
        </div>
        <div class="content">
            <h3>Show notifications for</h3>
            <div class="sub">
                <img src="../assets/notification.svg">
                <p>www.website.com</p>
            </div>
        </div>
        <div class="buttons">
            <Button block="true" @block="clickHandler"></Button>
            <Button allow="true" @allow="clickHandler"></Button>
        </div>
    </div>
</template>

<style scoped>
.container{
    width: 400px;
    height: 200px;

    background-color: #fff;
    position: fixed;
    top: 50%;
    left:50%;
    transform: translate(-50%, -50%);
    padding: 20px;
    border-radius: 10px;
}

.close{
    float: right;
}

.content{
    display: grid;
    grid-template-columns: repeat(1 1fr);
    padding: 20px;
}

.sub{
    display: flex;
    flex-direction: row;
    align-items: flex-end;
}

.buttons{
    display: flex;
    flex-direction: row;
    justify-content: flex-end;
    gap: 10px;
}
</style>