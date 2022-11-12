<script setup>
const emits = defineEmits(["show", "block", "allow"]);

const props = defineProps(["block", "allow", "show"])


const clickHandler = () => {
  emits("show");
  emits("block");
  emits("allow");
};
</script>

<template>
  <button v-if="props.show" class="show" @click="clickHandler">Show</button>
  <button v-if="props.block" class="block" @click="clickHandler">Block</button>
  <button v-if="props.allow" class="allow" @click="clickHandler">Allow</button>
</template>

<style scoped>
.show {
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  width: 150px;
  padding: 20px;
  border: 1px solid blue;
  color: blue;
  font-size: 20px;
  cursor: pointer;
  border-radius: 10px;
}

.block{
    widows: 75px;
    padding: 10px;
    font-size: 10px;
    border: 1px solid red;
    font-weight: 600;
    color: red;
    border-radius: 10px;
    cursor: pointer;
}

.allow{
    widows: 75px;
    padding: 10px;
    font-size: 10px;
    border: 1px solid green;
    font-weight: 600;
    color: green;
    border-radius: 10px;
    cursor: pointer;
}
</style>
