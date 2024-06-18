<template>
    <div class ="modal" v-if="isModal">
     <div class ="inner">
          <h3>{{ data[selectedmovies].title }}</h3>
         <p>영화 상세정보</p>
          <button @:click="isModal=false" selec>닫기</button>

     </div>
    </div>

</template>

<script>
export default {
    name: "ModalComponent"
}
</script>

<style>
    
</style>