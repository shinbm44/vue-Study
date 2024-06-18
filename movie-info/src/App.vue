<template>

  <navbor/>
  <event :helloText="helloText"/>

  <h1>영화 정보</h1>
  
  <div v-for="(item, i) in data" :key="i">
    <figure>
      <img :src="`${this.data[i].imgUrl}`" :alt="item.title">
    </figure>
    <div class =:info>
    <h3 class="bg-yellow" >{{ item.title }} </h3>
    <p>개봉: {{ item.year }}</p>
    <p>장르: {{ item.category  }} </p>

    <button @:click="increaseLike(i)">좋아요</button> <span>{{ item.like }}</span>
    <p>
      <button @:click="isModal=true; selectedmovies=i">상세보기</button>
    </p>
    </div>
  </div>
 
  <Modal :data="data" :isModal="isModal" :selectedmovies="selectedmovies"
  @closeModal="isModal=false"/>


</template>

<script>
  import data from "./assets/movies.js";
  import Navbor from "./components/Navbar.vue";
  import Modal from "./components/Modal.vue";
  import Event from './components/Event.vue';
 


  console.log(data);
  console.log(Navbor);

  export default{
    name: "App",

    methods : {
      increaseLike(i) {
        this.data[i].like +=1;
      }
    },

    data() {
      return {
        isModal : false,
        data : data, // 이 부분의 data는 import한 data이다. 그리고 이 data는 assets/movies.js에 담긴 것
        selectedmovies : 0,
        helloText : "영화 소개 페이지"
      }
    },

    components: {
      Navbor: Navbor,
      Modal: Modal,
      Event // 템플릿에서 사용할 때는 대소문자 구분 x ?
    }

  }
</script>
  
<style>
 .bg-yellow {
    background: yellow;
    padding: 10px
  }
  .button {
    background: gray;
    padding-right: 15px;
    padding-left: 15px;
  }

* {
  box-sizing: border-box;
  margin: 0;
}

body {
  max-width: 768px;
  margin: 0 auto;
  padding: 20px;
}

h1,
h2,
h3 {
  margin-bottom: 1rem;
}

p {
  margin-bottom: 0.5rem;
}

button {
  margin-right: 10px;
  margin-top: 1rem;
  background: gainsboro;
}

.item {
  width: 100%;
  border: 1px solid #ccc;
  display: flex;
  margin-bottom: 20px;
  padding: 1rem;
}

.item figure {
  width: 30%;
  margin-right: 1rem;
}

.item img {
  width: 100%;
}

.item .info {
  width: 100%;
}

.modal {
  background: rgba(0, 0, 0, 0.7);
  position: fixed;
  left: 0;
  top: 0;
  width: 100%;
  height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
}

.modal .inner {
  background: #fff;
  width: 80%;
  padding: 20px;
  border-radius: 10px;
}
</style>

