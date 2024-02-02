<script>
export default {
    mounted() {
        console.log(this.$slots);
    }
}
</script>

<template>
    <header class="header">
        <h1 class="title" v-if="$slots.title">
            <slot name="title"/>
        </h1>

        <div class="description">
            <slot name="description"/>
        </div>

        <div class="content">
            <slot/>
        </div>
    </header>
</template>

<style>
.header{
    background: #000000;
    color: #fff;
}


</style>
 