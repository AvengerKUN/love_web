<template>
    <div id="LoveContent">
<!--        这是覆盖上的div-->
        <div class="loveCover" :class="coverClass" @click="openLove">
            <div class="coverText">
                <h2> Love 表白墙</h2>
                <p>
                    单击打开<br>
                    即可打开表白墙
                </p>
                <p>
                    我们将<br>
                    存储你的心声
                </p>
            </div>
        </div>

<!--        创建表单-->
        <el-form class="loveFrom">
            <el-form-item label="昵称:">
                <el-input placeholder="昵称..."></el-input>
            </el-form-item>
            <el-form-item label="送给:">
                <el-input placeholder="送给..."></el-input>
            </el-form-item>
            <el-form-item label="显示的颜色 :">
                <el-color-picker></el-color-picker>
            </el-form-item>
            <el-input
                type="textarea"
                :rows="8"
                placeholder="给他(她) 的祝福">
            </el-input>
        </el-form>
    </div>
</template>

<script>
    export default {
        name: "LoveContent",
        data(){
            return{
                coverClass:{'mobileCover':false}
            }
        },
        methods:{
            openLove(){
                this.coverClass.mobileCover = true
            }
        }
    }
</script>

<style scoped>

    #LoveContent{
        width: 360px;
        height: 600px;
        background-color: white;
        position: relative;
        box-shadow: 0 4px 10px 4px rgba(19, 35, 47, 0.3);
    }
    .loveCover{
        width: 80%;
        height: 100%;
        background-color: rgb(195,36,76);
        position: absolute;
        right: 0;
        z-index: 1;
    }

    .coverText{
        color: white;
        position: absolute;
        top: 50%;
        transform: translateY(-50%);
        left: 20%;
    }

    .coverText p{
        font-size: 13px;
        margin-top: 10%;
    }

    /*上下箭头*/
    .coverText:before{
        content: ">";
        font-size: 50px;
        position: absolute;
        top:-100px;
        left: -30px;
        animation: coverArrow infinite 2s;
    }

    .coverText:after{
        content: ">";
        font-size: 50px;
        position: absolute;
        bottom:-100px;
        left: -30px;
        animation: coverArrow infinite 2s;
    }

    .loveFrom{
        position: absolute;
        width: 200px;
        margin: 10% 0 0 10%;
    }

    .mobileCover{
        animation:mobileCover 1s normal;
        transform: translateX(80%);
    }

    /*卡片移动动画*/
    @keyframes mobileCover {
        0%{
            transform: translateX(0);
        }
        100%{
            transform: translateX(80%);
        }
    }

    /*箭头动画*/

    @keyframes coverArrow {
        0%{
            opacity: 1;
            left: -30px;
        }
        100%{
            opacity: 0;
            left: 0;
        }
    }
</style>