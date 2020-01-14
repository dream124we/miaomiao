<template>
    <div class="messageBox">
        <h2>{{title}}</h2>
        <p>{{content}}</p>
        <div>
            <div @touchstart="handleCancel">{{cancel}}</div>
            <div @touchstart="handleOk">{{ok}}</div>
        </div>
    </div>
</template>

<script>
export default {
    name : 'MessgaeBox'
}
</script>

<style scoped>
.messageBox{ font-size: 14px; text-align: center; background: #ffffff; width: 200px; min-height: 120px; border: 1px solid #ddd; border-radius: 10px; box-shadow: 0px 0px 3px #0000005c; position: absolute; left: 50%; top: 50%; margin: -60px 0 0 -100px ; display: flex; flex-flow: column;}
.messageBox h2{ border-bottom: 1px solid #ddd; font-size: 16px; font-weight: 500; padding: 5px;}
.messageBox p{ flex: 1; padding: 10px;}
.messageBox>div{ display: flex; background-color: #f2f2f2; border-top: 1px solid #ddd;}
.messageBox>div>div{ flex: 1; border-right: 1px solid #ddd; color: #999; padding: 5px; font-size: 12px;}
.messageBox>div>div:last-of-type{ border-right: none; color: #f03d37;}
</style>