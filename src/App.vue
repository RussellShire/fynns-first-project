<script setup>
  import { ref } from 'vue';
  const buttonText = ref('click me')
  const clickCount = ref(0)
  const messageContent = ref('')

  const buttonClicked = () => {
    clickCount = clickCount + 1;

    
  }
</script>

<template>
  <button @click="buttonClicked">{{ buttonText }}</button> 
  <div v-if="messageContent" class="message">{{messageContent}}</div>
</template>

<style scoped>
.message {
  border: 1px black solid;
  padding: 10px;
  margin-top: 20px;
  border-radius: 10px;
  width: fit-content;
  background-color: gold;
}
</style>
