<template>
  <div class="product-card">
      <img :src="product.image" alt="product-card-1" class="product-card-image" />
      <h4>{{ product.title }}</h4>
      <p>€{{ product.price }}</p>
    <!-- <div class="like-count">
      <button @click="likes[0] ++">Likes</button>
      <span>{{likes[0]}}</span>
    </div> -->  
    </div>
</template>

<script>
export default {
    name: 'Card',
    props : {
        product: Object,
    },
}
</script>

<style>
.product-card {
    max-width: 640px;
    height: auto;
    margin-bottom: 120px;
}

.product-card h4{
    margin-bottom: 20px;
}

.product-card-image {
    width: 100%;
    margin-bottom: 42px;
    border-radius: 4px;
}

@media screen and (max-width: 640px) {
   .product-card-image {
        border-radius: 0;
}
}
</style>