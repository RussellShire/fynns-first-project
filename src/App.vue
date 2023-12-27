<script setup>
  import { ref } from 'vue';
  const buttonText = ref('dont press me')
  const buttonTextTwo = ref('please press me')
  const clickCount = ref(0)
  const clickCountTwo = ref(0)
  const messageContent = ref('')
  const messageContentTwo = ref('')
  const showButton = ref(true)

  const buttonClicked = () => {
    clickCount.value = clickCount.value + 1;

    if (clickCount.value > 0 && clickCount.value < 2) {
      buttonText.value = "dont press me again"
    } else if (clickCount.value < 5) {
      messageContent.value = "Ouch! Hey don't press me!-I might say press but still it REALLY HURTS"
    } else if (clickCount.value < 15 ) {
      messageContent.value = "You really don't quit!"
    } else if (clickCount.value < 30 ) {
      messageContent.value = "For the millionth time, STOP IT!!!!"
      buttonText.value ="dont press me now"
    } else if (clickCount.value < 100 ) {
      messageContent.value = "I'm in hospital now!" 
    } else if (clickCount.value < 101 )  {
      messageContent.value = "WILL YOU STOP DESTROYING ME!!!"
      
    } else if (clickCount.value < 105 ) {
      messageContent.value = "That's it, I'm off!"
      showButton.value = false
    }
  }

  const buttonTwoClicked = () => {
    clickCountTwo.value = clickCountTwo.value + 1;
    
    buttonTextTwo.value = "please press me again"
    
    if (clickCountTwo.value > 0 && clickCountTwo.value < 5) {
      messageContentTwo.value = "Thanks for pressing me!"
    } else if (clickCountTwo.value < 15) {
      messageContentTwo.value = "oooo I love this!"
    } else if (clickCountTwo.value < 30) {
      messageContentTwo.value = "please-just 10 more presses."
    } else if (clickCountTwo.value < 40) {
      messageContentTwo.value = "ok actually 20 more as this is so much like amassage"
    }
  }
</script>

<template>
  <h1>Fynn's Project</h1>
  <p>A button that doesn't like their job and one that dose</p>
  <div class="button-container">
    <button v-if="showButton" @click="buttonClicked">{{ buttonText }}</button> 
    <span class="counter">{{ clickCount }}</span>
  </div>

  <div v-if="messageContent" class="message">{{messageContent}}</div>

  <div class="button-container">
    <button @click="buttonTwoClicked">{{ buttonTextTwo }}</button> 
    <span class="counter">{{ clickCountTwo }}</span>
  </div>

  <div v-if="messageContentTwo" class="message">{{messageContentTwo}}</div>


</template>

<style scoped>
.message {
  border: 1px black solid;
  padding: 10px;
  margin-top: 20px;
  margin-bottom: 20px;
  border-radius: 100px;
  width: fit-content;
  background-color: gold;
}

.counter {
  margin-left: 5px;
}

.button-container {
  display: flex;
  align-items: center;
  margin: 20px;
}
</style>
