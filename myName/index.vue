<template>
    <div>
        <div @click="btn" v-show="isShow">显示这个盒子</div>
        <myGiarl msg="你好" />
    </div>
</template>
<script>
export default {
    name:'myName',
    data() {
        return {
            isShow:true 
        }
    },
    methods: {
        btn(){
            this.show=!this.show;
        }
    },
}
</script>
<style lang="less" scoped>

</style>


