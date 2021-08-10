<template>
  <div class="modal-overlay" v-if="modalOpen == true">
    <div class="modal-position">
      <div class="modal">
        <img :src="products[selected].image" alt="">
        <h4>
          {{ products[selected].title }} <br /> 
          {{ products[selected].rentalHost }}
        </h4>
        <p>
          {{ products[selected].content }}
        </p>
        <strong>
          For 
          <input v-model="day" type="text" placeholder="amount(1,2,3,...)"/> 
          day(s):&nbsp;€{{ products[selected].price * day }}
        </strong>
        <button @click="$emit('closedModal')">
          Close
        </button>
      </div>
  </div>  
    </div>
</template>

<script>
export default {
    name: 'Modal',
    data() {
      return{
        day: '',
      }
    },

    beforeUpdate() {
      if(this.day == 2){
        alert('Uh-oh, 3 nights are minimum :(')
      }
    },
    
    watch : {
      // day(a) {
      //   if(a > 32) {
      //     alert('Days should be less than 31 days')
      //   }
      // },
      day(a) {
        if(isNaN(a) == true){
          alert('Only numbers, please :)');
          this.day = '';
        }
      }
    },
    props: {
        products: Array,
        selected: Number,
        modalOpen: Boolean,
    },
}
</script>

<style>

.modal-overlay {
  position: fixed;
  width: 100%;
  height: 100%;
  padding: 20px;
  background-color: rgba(0,0,0,0.4);
}

.modal-position {
  display: flex;
  justify-content: center;
  align-items: center;
}

.modal {
  max-width: 560px;
  max-height: 100vh;
  border-radius: 4px;
  padding-bottom: 42px;
  background-color: #fff;
}

.modal img {
  width: 100%;
  height: auto;
  margin-bottom: 24px;
  border-radius: 4px 4px 0 0;
  background-size: cover;
  background-position: center center;
}

.modal h4 {
  margin-bottom: 24px;
}

.modal p {
  margin-bottom:24px;
}

.modal strong {
  display: block;
  margin-bottom: 42px;
}

.modal input {
  width: 108px;
  text-align: center;
}

.modal input:focus {
  outline: none;
}

.modal button {
    border: none;
    border-radius: 2px;
    padding: 11px 83px;
    font-weight: 700;
    color: #fff;
    background-color: #FF385D;
}
</style>