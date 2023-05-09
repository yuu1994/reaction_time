<template>
    <p>Result is {{ score }} ms</p>
    <div class="" v-if="score<300">
        <p>You are So fast !! Congrats...</p>
    </div>
    <div class="" v-else-if="score>300 && score<1500">
        <p>You are Normal ...</p>
    </div>
    <div class="" v-else>
        <p>You are so slow .Try Again!!</p>
    </div>
</template>
<script>
export default {
    props : [
        'score'
    ]
}
</script>

<style>

</style>