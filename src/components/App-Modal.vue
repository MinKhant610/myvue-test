<template>
    <div class="backdrop">
        <!-- success => class name : theme data -->
        <div class="modal" :class="{success:theme === 'success', danger:theme === 'danger'}">
            <h1>{{ header }}</h1>
            <p>{{ content }}</p>
        </div>
    </div>
</template>

<script>
    export default {
        props : ['header', 'del', 'content', 'theme'],
    }
</script>
    
<style scoped>
    .backdrop{
        position: fixed;
        top: 0;
        background: rgba(0, 0, 0, 0.5);
        width: 100%;
        height: 100%;

    }
    .modal{
        width: 400px;
        padding: 20px;
        margin: 100px auto;
        background-color: white;
        border-radius: 10px;
    }
    p{
        font-style: normal;
    }
    .success{
        background: yellowgreen;
    }
    .danger{
        background: red;
        color: white;
    }
</style>