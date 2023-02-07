<template>
  <div style="text-align: center">
    <h2 style="text-align: ">Let's see products</h2>
    <v-btn variant="flat" color="#BFACE2" @click="LoadProduct()">
      Load products
    </v-btn>
  </div>
  <div style="text-align: center">
    <ul>
      <li v-for="product in productData" :key="product.id">
        {{ product.id }}
        <div
          class="d-flex align-center flex-column"
          style="margin-bottom: 1rem"
        >
          <v-card width="400"
            >{{ product.title }} <br />
            <img :src="product.image" alt="..." height="150" />
            <p style="margin-bottom: 1rem">{{ product.category }}</p>
            <p>price:{{ product.price }}$</p>
          </v-card>
        </div>
      </li>
    </ul>
  </div>
</template>

<script setup>
import axios from "axios";
import { ref } from "vue";
const productData = ref([]);
const url = ref("https://fakestoreapi.com/products");

function LoadProduct() {
  axios
    .get(url.value)
    .then((Response) => {
      productData.value = Response.data;
    })
    .catch((err) => {
      console.log(err);
    });
}
</script>
