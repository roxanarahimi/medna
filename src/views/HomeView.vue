<template>
  <div class="d-flex px-2 justify-content-between">
    <div class="d-flex">
      <i class="bi bi-grid-3x3-gap-fill mt-2 cursor-pointer chocolate-color" :class="{'maroon-color': type ==='tile'}" style="font-size: 42px;" @click="viewToggle('tile')"></i>
      <i class="bi bi-justify cursor-pointer chocolate-color" :class="{'maroon-color': type ==='table'}" style="font-size: 53px;" @click="viewToggle('table')"></i>
    </div>
  </div>
  <div v-if="type==='tile'" class="row px-2 pb-5">
    <div v-for="item in data" class="col-6 col-md-4  mb-4">
      <div class="card w-100 border-0 h-100 card-bg">
        <div v-if="item.off!==0" class="position-absolute d-grid text-center top-right-0">
          <p class="m-0 align-self-center fw-bold off-badge">{{ item.off }}%</p>
        </div>
        <div class="card-body" >
          <img :src="item.image" class="w-100 rounded rounded-circle p-2" alt="">
          <h5 class="pt-3" style="color: maroon">{{ item.name }}</h5>
          <div class="d-flex justify-content-between mb-3">
            <p v-if="item.off!==0" class="pb-3 text-decoration-line-through maroon-color" >{{item.price}}$</p>
            <p class="pb-3 maroon-color fw-bold">{{item.price - (item.price * item.off / 100)}}$</p>
          </div>
          <div class="position-absolute d-grid text-center bottom-left-0">
            <p class="m-0 align-self-center fw-bold add-badge">+</p>
          </div>
        </div>

      </div>

    </div>
  </div>
  <div v-if="type==='table'" class="row px-4 pb-5 ">
    <table class=" rounded" style="overflow: hidden; color: white !important">
      <thead>
      <tr style="background-color: #C34B25">
        <th scope="col" class=" py-4" style="width: 150px"></th>
        <th scope="col" class=" py-4">Name</th>
        <th scope="col" class=" py-4">Price</th>
        <th scope="col" class=" py-4">Off</th>
        <th scope="col" class=" py-4">Final Price</th>
      </tr>
      </thead>
      <tbody>
      <tr v-for="(item,index) in data" :key="index" :class="{'bg-chocolate':index%2===0, 'bg-main':index%2===1}">
        <td  style="width: 150px"><img :src="item.image" class="rounded rounded-circle p-2" width="50px" alt=""></td>
        <td>{{ item.name }}</td>
        <td>{{ item.price }}$</td>
        <td>{{ item.off }}%</td>
        <td>{{ item.price - (item.price * item.off / 100) }}$</td>
      </tr>
      </tbody>
    </table>

  </div>
</template>

<script>
import {ref} from "vue";

export default {
  name: 'HomeView',
  components: {},
  setup() {
    const data = [
      {id: 1, image: '/img/01.jpg', name: 'cherry cupcake', price: 5, off: 20},
      {id: 2, image: '/img/02.jpg', name: 'vanilla cupcake', price: 6, off: 0},
      {id: 3, image: '/img/03.jpg', name: 'chocolate cupcake', price: 2, off: 15},
      {id: 4, image: '/img/04.jpg', name: 'berry cupcake', price: 4, off: 0},
      {id: 5, image: '/img/01.jpg', name: 'cherry cupcake', price: 9, off: 9},
      {id: 6, image: '/img/02.jpg', name: 'vanilla cupcake', price: 7, off: 11},
      {id: 7, image: '/img/03.jpg', name: 'chocolate cupcake', price: 3, off: 20},
      {id: 8, image: '/img/04.jpg', name: 'berry cupcake', price: 6, off: 7},
      {id: 9, image: '/img/01.jpg', name: 'cherry cupcake', price: 5, off: 0},
      {id: 10, image: '/img/02.jpg', name: 'vanilla cupcake', price: 6, off: 32},
      {id: 11, image: '/img/03.jpg', name: 'chocolate cupcake', price: 2, off: 15},
      {id: 12, image: '/img/04.jpg', name: 'berry cupcake', price: 4, off: 0},

    ];
    const type =ref('tile');
    const pdf = () => {

    }
    const viewToggle = (x) => {
      type.value = x;
    }

    return {
      data, pdf, viewToggle, type
    }
  }
}
</script>
<style>
img:not(.parallax>img){
  border-radius: 500px !important;
}
</style>
