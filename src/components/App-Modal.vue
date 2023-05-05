<template>
    <!-- click.self => not effect in child div only in self div -->
    <div class="backdrop" @click.self="closeDrop">
        <!-- success => class name : theme data -->
        <div class="modal" :class="{success:theme === 'success', danger:theme === 'danger'}">
            <!-- slot get data from model child-->
            <slot>
                <!-- defalut work when there is no slot -->
                default
            </slot>
            <!-- slot with name -->
            <slot name="links"/>
        </div>
    </div>
</template>

<script>
    export default {
        props : ['theme'],
        
        methods :{
            closeDrop(){
                this.$emit("close");
            }
        }
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