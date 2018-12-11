<template>
  <view class="container">
    <text-input
      :style="{height: 40, width: 200, borderColor: 'gray', borderWidth: 1}"
      v-model="messageText"
    />
    <button
      :on-press="saveMessage"
      title="Save"
    />
    <text v-for="(message, index) in messages" :key="index">{{ message }}</text>
  </view>
</template>
<script>
  import Store from '../store';
  export default {
    data: function() {
      return {
        messageText: ''
      }
    },
    computed: {
      messages: function() {
        return Store.getters.messages
      }
    },
    methods: {
      saveMessage: function() {
        Store.dispatch('addMessage', this.messageText)
        this.messageText = ''
      }
    }
  }
</script>
<style>
.container {
  background-color: white;
  align-items: center;
  justify-content: center;
  flex: 1;
}
.text-color-primary {
  color: blue;
}
</style>
