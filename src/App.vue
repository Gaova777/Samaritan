<template>
  <div class="container">
    <input type="file" @change="file = $event.target.files[0]" />
    <img :src="fileSrc" alt="" />
  </div>
</template>

<script>
export default {
  name: 'App',
  data () {
    return {
      file: null,
      fileSrc: null
    }
  },
  watch: {
    file (value) {
      console.log('------------------- FILE -------------------')
      console.log(value)

      if (value) {
        const reader = new FileReader()
        reader.onload = e => {
          this.fileSrc = e.target.result
        }
        reader.readAsDataURL(value)
      } else {
        this.fileSrc = null
      }
    }
  }
}
</script>

<style lang="scss">
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

body {
  margin: 0;
  max-width: initial;
}

.container {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  gap: 16px;
  min-height: 100vh;

  img {
    width: 50vw;
    border-radius: 8px;
  }
}
</style>
