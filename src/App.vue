<script setup>
  import { ref } from 'vue';
  const buttonText = ref('press me')
  const clickCount = ref(0)
  const messageContent = ref('')
  const showButton = ref(true)

  const buttonClicked = () => {
    clickCount.value = clickCount.value + 1;

    if (clickCount.value > 0 && clickCount.value < 2) {
      buttonText.value = 'press me again'
    } else if (clickCount.value < 5) {
      messageContent.value = "Ouch! Hey don't press me!-I might say press but still it REALLY HURTS"
    } else if (clickCount.value < 15 ) {
      messageContent.value = "You really don't quit!"
    } else if (clickCount.value < 30 ) {
      messageContent.value = "For the millionth time, STOP IT!!!!"
    } else if (clickCount.value < 100 ) {
      messageContent.value = "I'm in hospital now!" 
    } else if (clickCount.value < 101 )  {
      messageContent.value = "WILL YOU STOP DESTROYING ME!!!"
      
    } else if (clickCount.value < 105 ) {
      messageContent.value = "That's it, I'm off!"
      showButton.value = false
    }
  }
</script>

<template>
  <div class="button-container">
    <button v-if="showButton" @click="buttonClicked">{{ buttonText }}</button> 
    <span class="counter">{{ clickCount }}</span>
  </div>

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

.counter {
  margin-left: 5px;
}

.button-container {
  display: flex;
  align-items: center;
}
</style>
