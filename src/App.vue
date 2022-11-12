<script setup>
import Button from "./components/Button.vue"
import Notification from "./components/Notification.vue"
import { ref } from "vue"


const showNotifications = ref(false)
const showButton = ref(true)

const showClick = () =>{
  showNotifications.value = true
  showButton.value = false
}

</script>

<template>
  <div class="floor">
    <Button v-if="showButton" @show="showClick" show="true"></Button>
    <Notification v-if="showNotifications"></Notification>
  </div>
</template>

<style scoped>
  .floor{
    position: absolute;
    width: 700px;
    height: 175px;

    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%);
    background-color: #CD8AFF;
    border-radius: 30px;
  }
</style>
