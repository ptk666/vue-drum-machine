<template>
  <div class="drum-pad"
    @click="playSound(sound); changeNote()" >
    {{ sound.key }}
  </div>
</template>

<script>
export default {
  name: 'DrumMachine',
  props: ['sound'],
  data() {
    return {
      
    }
  },
  methods: {
    playSound({key, mp3}) {
      let s = new Audio(mp3);
      s.play();

      this.note = key;

      document.addEventListener('keydown', (e) => {
        const id = e.key.toUpperCase();
        const audio = document.getElementById(id);

        console.log(id, audio);
      })
    },
    changeNote() {
      this.$emit('change-note', this.note);
    }
  },
  mounted() {
    document.addEventListener('keydown', (e) => {
      const id = e.key.toUpperCase();
      const audio = document.getElementById(`${this.sound}.${id}`);

      console.log(id, audio);
    })
  }
}
</script>

<style>
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
</style>