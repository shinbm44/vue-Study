<template>
  <h1>영화 정보</h1>
  
  <div v-for="(item, i) in data" :key="i">
    <h3 class="bg-yellow" >{{ item.title }} </h3>
    <p>개봉: {{ item.year }}</p>
    <p>장르: {{ item.category  }} </p>
  </div>

</template>

<script>
  export default{
    name: "App",
    data() {
      return {

        data : [
          {
            title: "노랑",
            year: 2023,
            category: "액션, 드라마",
          },
          {
            title: "아쿠아맨과 로스트 킹덤",
            year: 2023,
            category: "액션, 판타지, 어드벤처",
          },
          {
            title: "3월의 휴가",
            year: 2023,
            category: "판타지, 드라마 "
          }
        ]


      }
    },
  }
</script>
  
<style>
 .bg-yellow {
    background: yellow;
    padding: 10px

  }
</style>
