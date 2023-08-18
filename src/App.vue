<template>
  <div class="container">
    <input type="file" @change="file = $event.target.files[0]" />
    <h2 v-if="file">There is a file</h2>
  </div>
</template>

<script>
export default {
  name: 'App',
  data () {
    return {
      file: null
    }
  },
  watch: {
    file (value) {
      console.log('------------------- FILE -------------------')
      console.log(value)
      console.log()
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
  min-height: 100vh;
}
</style>
