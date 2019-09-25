<template>
    <div class="watchVal">
        <input type="text" v-model="dataVal">
    </div>
</template>
<script>
export default {
    data() {
        return {
            // typeVal:{
            //     count:""
            // },
            count:""
        }
    },
    // watch: {
    //     'typeVal.count':{
    //         handler(newVal,oldVal){
    //             console.log("变动之前的值"+':'+oldVal);
    //               console.log("变动之后的值"+':'+newVal);
    //         }
    //     },
    //     deep:true
    // },
    computed: {
        dataVal(){
            let count =0;
            this.count=count
            console.log(this.count)
            return count;
        }
    },
}
</script>
<style lang="less" scoped>
.watchVal{
    width: 100%;
    overflow: hidden;
}
</style>