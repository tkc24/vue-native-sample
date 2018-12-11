<template>
  <app-navigation></app-navigation>
</template>
<script>
import { StackNavigator } from "vue-native-router";
import HomeScreen from "./screens/HomeScreen.vue";
import MessagesScreen from "./screens/MessagesScreen.vue";
const AppNavigation = StackNavigator(
  {
    Home: HomeScreen,
    Messages: MessagesScreen,
  },
  {
    initialRouteName: 'Home',
  }
);
export default {
    components: { AppNavigation }
}
</script>