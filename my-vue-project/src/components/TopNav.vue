<template>
    <div class="header">
        <ul>
            <li @click="logout">退出</li>
            <li>使用指南</li>
        </ul>

    </div>
</template>

<style scoped>
    *{
        margin: 0;
        padding: 0;
    }
    .header{
        width: 100%;
        background-color: #C1D8C3;
        display: flex;
        /* 在水平方向排列 */
        justify-content: flex-end; 
        padding-right: 2rem;
        height: 3rem;
    }
    ul{
        list-style: none;
        display: flex; /* 将 ul 内的 li 变为横向排列 */
        justify-content: center; /* 确保 ul 内容居中 */
        align-items:center;
    }
    ul li{
        padding: 0.5rem 1rem;
        cursor:pointer
    }
    ul li:hover{
        background-color: rgb(255, 255, 255,0.5); /* 添加 hover 效果 */;
    }


</style>
<script>
export default {
    methods:{
        logout(){
            this.$router.push('/')
        }
    }
}
</script>