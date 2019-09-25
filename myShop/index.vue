<template>
    <div>
        <table>
            <thead>
                <tr>
                <th>商品总数:{{getTotal}}</th>
                <th>商品总价:{{AllData.totalPrice}}</th>
                <th>
                    <input type="checkbox" v-model="AllData.AllChecked" @click="checkAll">
                    全选
                </th>
            </tr>
            </thead>
            <tbody>
                <tr v-for="(item,index) in list" :key="index">
                    <td>{{item.name}}</td>
                    <td>{{item.price}}</td>
                    <td>
                        <input type="checkbox" v-model="item.isChecked">
                    </td>
                </tr>
            </tbody>
        </table>
    </div>
</template>
<script>
export default {
    data() {
        return {
            list:[{
                name:"桃子",
                price:12,
                isChecked:false
            },
            {
                 name:"梨子",
                 price:8,
                 isChecked:false
            },
             {
                 name:"苹果",
                 price:20,
                 isChecked:false
            },
             {
                 name:"香蕉",
                 price:10,
                 isChecked:false
            }
               
            ],
          AllData:{
                // 选中的商品数量
            total:0,
            //商品的总价格
            totalPrice:0,
            //是否已经全选
            AllChecked:false
            
          }
        }
    },
    methods: {
        //全选和反选
      checkAll(){
            this.list.forEach(index=>{
             if(!this.AllData.AllChecked){
                index.isChecked=true;
            }else{
                 index.isChecked=false;
             }  
        })
      }  
    },
    computed:{
        //计算商品中的商品数量，总价格，以及判断是否全选
        getTotal(){
            let count=0;
            let totalPrice=0;
           this.list.forEach(index=>{
               if(index.isChecked){
                  count++;
                  this.AllData.total=count;
                  totalPrice+=index.price;
               }
           })
            this.AllData.totalPrice=totalPrice;
            this.AllData.AllChecked=this.AllData.total===this.list.length;
            return count;
        }
    },
    activated() {
        

    },
}
</script>
<style lang="less" scoped>
 table{
     text-align: center;
     border-collapse: collapse;
     border-spacing: 0;
 }
 td,th{
     width:200px;
     height: 20px;
     border: 1px solid #000;
 }
 input{
     width:20px;
     height:20px;
 }
</style>
