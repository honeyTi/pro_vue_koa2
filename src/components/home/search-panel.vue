<template>
    <div class="search-pannel">

    </div>
</template>
<script>
export default {
    name: 'search-pannel',
    data(){
        return {msg:123}
    }
}
</script>
<style>
.search-pannel{
    position: fixed;
    top: 4.5rem;
    left: 0;
    right: 0;
    height: 0;
    background-color: #fff;
    margin-right: 1.2rem;
    margin-left: 1.2rem;
    /*animation: begin .6s forwards;*/
}

@keyframes begin{
    from {height: 0}
    to {height: 100%}
}
@keyframes end{
    from {height: 100%}
    to {height: 0}
}
</style>