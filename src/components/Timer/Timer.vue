<template>
  <div>
    <p class="result__counter"><span class="result__timer"> {{ minutes }}:{{ seconds }}</span> минут</p>

  </div>
</template>

<script>
export default {
  data() {
    return {
      time: 600, // 10 минут в секундах
      minutes: 0,
      seconds: 0
    };
  },
  mounted() {
    this.timer = setInterval(() => {
      this.time--;
      if (this.time <= 0) {
        clearInterval(this.timer);
      } else {
        const minutes = Math.floor(this.time / 60);
        const seconds = this.time % 60;
        this.minutes = minutes;
        this.seconds = seconds;
      }
    }, 1000);
  }
};
</script>

<style>
.result__counter {
  font-family: PT Serif;
  font-size: 11px;
  font-weight: 400;
  line-height: 30px;
  letter-spacing: 0.1em;
  text-align: center;
  color: rgba(59, 222, 124, 1);
  padding-bottom: 6px;
}

.result__timer {
  font-size: 20px;
  font-weight: 400;
  line-height: 30px;
  letter-spacing: 0.1em;
  text-align: center;

}
</style>