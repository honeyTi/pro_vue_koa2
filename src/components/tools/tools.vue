<template>
    <div class="tools-nav">
        <ul>
            <subway></subway>
            <draw></draw>
        </ul>
    </div>
</template>
<script>
import subway from './tool/subway.vue'
import draw from './tool/draw.vue'

export default {
    name:'tools',
    components:{
        'subway':subway,
        'draw':draw,
    }
  
}
</script>
<style>
@import '../../assets/css/tools/tools.scss'
</style>

