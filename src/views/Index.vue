<template>
    <div id="Index">
        <LoveContent class="love_content"></LoveContent>
        <RollingLove class="rolling_love"></RollingLove>
    </div>
</template>

<script>
    import RollingLove from "../components/RollingLove";
    import LoveContent from "../components/LoveContent";
    export default {
        name: "Index",
        components: {LoveContent, RollingLove}
    }
</script>

<style scoped>

    #Index{
        width: 100%;
        height: 100%;
    }

    .rolling_love{
        position: fixed;
        bottom: 10px;
        left: 10px;
    }

    .love_content{
        position: fixed;
        top: 50%;
        transform: translateY(-50%) translateX(-50%);
        left: 50%;
    }
</style>