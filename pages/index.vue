<template>
  <v-container>
    <v-row>
      <v-col align="center" justify="center">
        <v-progress-circular
          indeterminate
          color="secondary"
        />
      </v-col>
    </v-row>
    <v-row>
      <v-col align="center" justify="center">
        <h2 class="txt"></h2>
      </v-col>
    </v-row>
  </v-container>
</template>

<script>
export default {
  name: 'IndexPage',
  data: () => ({
    text: 'Loading',
    interval: 200,
    pause: 5,
    intervalId: null
  }),
  mounted () {
    const txt = document.querySelector('.txt')
    let n = 0
    this.intervalId = setInterval(() => {
      if (n < this.text.length) {
        txt.innerHTML += this.text[n++]
      } else if (n < this.text.length + this.pause) {
        n += 1
      } else {
        txt.innerHTML = ''
        n = 0
      }
    }, this.interval);
  },
  beforeDestroy () {
    clearInterval(this.intervalId)
  }
}
</script>

<style>
@keyframes cursor {
    to {
        border-color: transparent;
    }
}
.txt {
    display: table-cell;
    color: #333333;
    vertical-align: middle;
    border-right: 0.05em solid black; 
    animation: cursor 0.5s ease infinite;
}
</style>