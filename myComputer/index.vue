<template>
    <div>
        <button @click="btn()">123</button>
        <p v-show="isBtn">Love</p>
         
       <span>{{dataWatch.name}}</span>
        <span>{{dataWatch.type}}</span>
         <span>{{dataWatch.boy}}</span>
          <br>
       <input type="text" v-model="ILoveYou">
     
    </div>
</template>
<script>
export default {
    data() {
        return {
            isBtn:true,
               
            dataWatch:{
                nameLove:"爱你李康康",
                name:"爱你香",
                type:'爱你金金',
                boy:'爱你'
            }
        }
    },
 //   watch: {
    //      nameLove(newVal,oldVal){
    //          console.log(newVal,oldVal)
    //          this.name=newVal+"香";
    //          this.type=newVal+"金金";
    //          this.boy=newVal+"李康康";
    //          console.log( this.boy+':'+this.name+ this.type)
    //      }
    // },
    computed:{
        ILoveYou: {
            get: function () {
                //获取的时候直接获取值
                return this.dataWatch.nameLove+this.dataWatch.name+this.dataWatch.type;
            },
            set: function (value) {
               this.dataWatch.nameLove= value; 
            }
        }
    },
    methods: {
        // btn(){
        //     this.isBtn=!this.isBtn;
        // },
        btn:function(){
            this.isBtn=!this.isBtn;
        }
        
    },
}
</script>
<style lang="less" scoped>

</style>