<template>
  <div>
    <!-- <img src="assets/1.jpg" class="tu"> -->
    <input type="text" v-model="text" placeholder="请输入内容" id="ddd">
    <button @click="handleClick" id="btn">提交</button>
    <ul class="yjxy">
      <li v-for="(item, index) in list" :key="index" @click="removeItem(index)">
        {{item}}
      </li>
    </ul>
    <a class="aa">点击内容文本即可删除</a>
  </div>
</template>

<script>
export default {
  data(){
    return({
      list:[
        '第一条内容',
        '第二条内容',
        '第三条内容'
      ],
      text:''
    })
  },
  methods:{
    handleClick(){
      //console.log(this.text)
      this.list.push(this.text)
      this.text= ''
      // console.log(this.list)
    },
    removeItem(index){
      this.list.splice(index, 1)
    }
  }
}
</script>

<style>
  /* .tu{
    width: 100%;
    height: 100px;
  } */
  div{
    background: url(assets/1.jpg) no-repeat;
    height: 500px;
  }
  #ddd{
  -web-kit-appearance:none;
  -moz-appearance: none;
  font-size:14px;
  height:26px;
  margin-left: 40%;
  margin-top: 50px;
  border-radius:6px;
  border:1px solid #33a7ff;
  color:#6a6f77;
  }
  #btn{
    width: 60px;
    height:30px;
    margin-left: 20px;
    display: inline-block;
    background-color: rgb(50, 252, 255);
    border:rgb(0, 224, 228);
    border-radius: 10px;
  }
  .yjxy{
    margin-left: 40%;
    color: rgb(255, 83, 30);
  }
  .aa{
    font-size: 14px;
    color: #949494;
    margin-left: 41%;
  }
</style>