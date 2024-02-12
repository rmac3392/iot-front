<template>
  <div>
    <h1>Arduino Control</h1>
    <button @click="turnOn">Turn On</button>
    <button @click="turnOff">Turn Off</button>
  </div>
</template>

<script setup>
import io from "socket.io-client";

const socket = io('https://iot-elyc.onrender.com/');
//const socket = io("http://localhost:5173");

const turnOn = () => {
  console.log("Connect to server on");
  socket.emit("on", 13);
};
const turnOff = () => {
  console.log("Connect to server off");
  socket.emit("off", 13);
};
</script>
