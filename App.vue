<template>
  <app-navigator></app-navigator>
</template>

<script>
import {
  createAppContainer,
  createMaterialTopTabNavigator,
  createStackNavigator
} from "vue-native-router";

import HomeScreen from "./screens/Home.vue";
import CameraScreen from "./screens/Camera.vue";


const Tabs = createMaterialTopTabNavigator({
  Home: HomeScreen
});

const StackNavigator = createStackNavigator(
  {
    Tabs,
    Camera: CameraScreen
  },
  {
    defaultNavigationOptions: {
      gestureEnabled: false,
      title: "Vue Native",
      headerTitleStyle: {
        textAlign: "center",
        alignSelf: "center",
        color: "white"
      },
      headerStyle: {
        backgroundColor: "#0288D1"
      }
    }
  }
);

const AppNavigator = createAppContainer(StackNavigator);

export default {
  components: { AppNavigator }
};
</script>
