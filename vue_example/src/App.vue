<template>
  <div>
    <div class="black-bg" v-if="modal == 1">
      <div class="white-bg">
        <h4>상세페이지</h4>
        <p> 내용</p>
        <button @click="modal = 0">닫기</button>
      </div>
    </div>



    <img alt="Vue logo" src="./assets/logo.png">
    {{p1}}
    <ul>
      <li v-for="(a,i) in product" :key="i">{{a}}-{{i}}</li>
    </ul>
    <ul>
      <li v-for="a in product" :key="a">{{i}}</li>
    </ul>
    <button @click="count += 1">버튼</button><span>카운트:{{count}}</span>
    <br>
    <button @click="count_plus">버튼</button><span>카운트:{{count}}</span>
    <br>
    <button @mouseover="count += 1">버튼</button><span>카운트:{{count}}</span>
    {{tmp_list[0].title}}
    <img id="img2" :src="tmp_list[0].image"/>
  </div>
</template>

<script>
//import {a1} from './assets/data';
import list_data from './assets/data';
list_data;

export default {
  name: 'App',
  data(){
    return {
      modal : 0,
      p1 : 60,
      p2 : 70,
      product : ['가','나','다'],
      count : 0,
      tmp_list : list_data,
    }
  },
  methods:{
    count_plus(){
      this.count = this.count + 1
      this.modal = this.count%2
    }
  },
  components: {
  }
}
</script>

<style>
body{
  margin : 0
}
div{
  box-sizing : border-box;
}
.black-bg{
  width:100%; height: 100%;
  background: rgba(0,0,0,0.5);
  position: fixed; padding:20px;
}
.white-bg{
  width: 100%; background: white;
  border-radius: 8px;
  padding: 20px;
}

#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
