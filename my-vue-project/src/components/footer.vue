<template>
    <div class="footer">
        <div class="content">
             <ul>
                <li>加入我们</li>
                <li>合作单位</li>
                <li>联系方式</li>
                <li>公司声明</li>
            </ul>
        <p> Blog company copyright</p>
        </div>
       
    </div>
</template>

<style scoped>
    *{
        margin: 0;
        padding: 0;
    }
    .footer{
        width: 100%;
        background-color: #C1D8C3;
        display: flex;
        /* 在水平方向排列 */
        justify-content: center; 
        padding-right: 2rem;
        height: 6rem;
    }
    .content{
        display: flex;
        flex-direction: column;
        align-items:center;
    }
    ul{
        list-style: none;
        display: flex; /* 将 ul 内的 li 变为横向排列 */
        justify-content: center; /* 确保 ul 内容居中 */
        padding: 0.8rem 0; /* 增加底部内边距，给 p 留下空间 */
    }
    ul li{
        padding: 0.5rem 1rem;
        cursor:pointer;
        
    }
    ul li:hover{
        background-color: #e0f7fa; /* 添加 hover 效果 */;
    }
    .footer p{
        font-style: 10px;
        color: black;
        text-align: center;
    }

</style>