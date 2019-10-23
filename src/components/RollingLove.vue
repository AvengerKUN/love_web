<template>
    <div id="RollingLove">
        <template v-for="(item,i) in loves">
            <a :href="item.http" :id="'loveId'+item.loveId" :class="{'lastAnimation':i === loves.length-1}" :style="{'background-color':item.color}">
                {{ item.text }}
            </a>
            <br>
        </template>
    </div>
</template>

<script>
    export default {
        name: "RollingLove",
        data(){
            return{
                loves:[
                    {
                        loveId: 0,
                        http:"http://baidu.com",
                        text:"这是一段表白的话1",
                        color:"rgb(237, 188, 204)"
                    },
                    {
                        loveId: 0,
                        http:"http://baidu.com",
                        text:"这是一段表白的话2",
                        color:"rgb(237, 188, 204)"
                    },
                    {
                        loveId: 0,
                        http:"http://baidu.com",
                        text:"这是一段表白的话3",
                        color:"rgb(146, 217, 228)"
                    },
                    {
                        loveId: 0,
                        http:"http://baidu.com",
                        text:"这是一段表白的话4",
                        color:"rgb(146, 217, 228)"
                    },
                    {
                        loveId: 0,
                        http:"http://baidu.com",
                        text:"这是一段表白的话5",
                        color:"rgb(146, 217, 228)"
                    }
                ]
            }
        },
        methods:{
            rolling(){
                this.loves.push(this.loves[0]);
                this.loves.splice(0,1)
            }
        }
        ,
        beforeMount() {

            setInterval(this.rolling,5000)

        }
    }
</script>

<style scoped>
    #RollingLove a{
        font-size: 16px;
        margin-bottom: 20px;
        display: inline-block;
        padding: 5px 15px 5px 15px;
        text-decoration: none;
        color: #ffffff;
        border-radius: 15px;
    }

    .lastAnimation{
        animation: rolling infinite 5s;
        opacity: 0;
    }

    @keyframes rolling {
        0%{
            opacity: 0;
            margin-bottom: 0;
        }
        100%{
            opacity: 1;
            margin-bottom: 20px;
        }
    }
</style>