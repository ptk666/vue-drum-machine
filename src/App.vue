<template>
  <div id="app" class="container">
    <div id="display" class="display">
      <h1>Press a note!</h1> 
      <DrumMachine
        v-for="sound in sounds" :key="sound.id"
        :text="sound.key"
        :audio="sound.mp3" />
    </div>
  </div>
</template>

<script>
import DrumMachine from './components/DrumMachine.vue'

export default {
  name: 'App',
  components: {
    DrumMachine,
  },
  data() {
    return {
      sounds: [
        {
          key: 'Q',
          mp3: "https://s3.amazonaws.com/freecodecamp/drums/Heater-1.mp3"
        },
        {
          key: 'W',
          mp3: "https://s3.amazonaws.com/freecodecamp/drums/Heater-2.mp3"
        },
        {
          key: 'E',
          mp3: "https://s3.amazonaws.com/freecodecamp/drums/Heater-3.mp3"
        },
        {
          key: 'A',
          mp3: "https://s3.amazonaws.com/freecodecamp/drums/Heater-4_1.mp3"
        },
        {
          key: 'S',
          mp3: "https://s3.amazonaws.com/freecodecamp/drums/Heater-6.mp3"
        },
        {
          key: 'D',
          mp3: "https://s3.amazonaws.com/freecodecamp/drums/Dsc_Oh.mp3"
        },
        {
          key: 'Z',
          mp3: "https://s3.amazonaws.com/freecodecamp/drums/Kick_n_Hat.mp3"
        },
        {
          key: 'X',
          mp3: "https://s3.amazonaws.com/freecodecamp/drums/RP4_KICK_1.mp3"
        },
        {
          key: 'C',
          mp3: "https://s3.amazonaws.com/freecodecamp/drums/Cev_H2.mp3"
        }
      ],
      text: '',
      audio: ''
    }
  },
  methods: {
    
  }
}
</script>

<style>
@import url('https://fonts.googleapis.com/css2?family=Roboto+Mono:ital,wght@0,100;0,200;0,300;0,400;1,100;1,200;1,300&display=swap');

* {
  box-sizing: border-box;
    padding: 0;
    margin: 0;
}

#app {
  font-family: 'Roboto Mono', monospace;
  background-color: #b2bec3;
  min-width: 100vw;
  min-height: 100vh;
}

.container {
  min-height: 100vh;
  display: flex;
  align-items: center;
  justify-content: center;
  text-align: center;
}

.display {
  display: flex;
  flex-wrap: wrap;
  width: 360px;
  background-color: #fff;
  border-radius: 4px; 
}

.drum-pad {
  border: 1px solid #333;
  background-color: #ff6b81;
  color: #fff;
  border-radius: 4px;
  height: 100px;
  width: 100px;
  margin: 10px;
  display: flex;
  justify-content: center;
  align-items: center;
  cursor: pointer;
}

.drum-pad.active {
  opacity: 0.6;
  transform: scale(0.98);
}

.display h1 {
  display: block;
  width: 100%;
  text-align: center;
  justify-content: center;
}

#signature {
  color: #000;
  justify-content: center;
  text-align: center;
  font-size: 10px;
  margin-top: 5px;
}
</style>
