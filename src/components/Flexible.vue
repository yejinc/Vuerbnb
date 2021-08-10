<template>
  <div class="flexible">
    <h2 class="flexible-text">
      Not sure where to go? Perfect.
    </h2>
    <button class="flexible-button">
      I'm flexible
    </button>
  </div>
</template>

<script>
export default {
    name: 'Flexible',
    // data(){
    //     return {

    //     }
    // }
}
</script>

<style>
.flexible {
  padding: 42px;
  margin: 0 24px 80px;
  border-radius: 4px;
  background-image: url("https://a0.muscache.com/im/pictures/27a5b2c0-d954-4c8d-be6f-8db072cdfa45.jpg?im_q=medq&im_w=720");
  background-size: cover;
  background-repeat: no-repeat;
  background-position: center center;
}

.flexible-text {
  margin-bottom: 42px;
}

.flexible-button {
  border: none;
  border-radius: 8px;
  padding: 9px 16px;
  color: #fff;
  background-color: #222;
}
</style>