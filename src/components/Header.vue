<template>
    <div class="headerview">
        <h1>{{msg}}</h1>
    </div>
</template>

<script>
export default {
    data(){
        return {
            title: "我是標題"
        }
    },
        props: {
            msg: {
                type: String,
                default: "我是誰？"
            }
        }
    }

</script>

<style>

</style>
