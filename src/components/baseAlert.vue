<script>

export default {
    props: ['variant'],
    computed: {
        baseClass() {
            return [
                'alert', 
                this.variant ? `alert-${this.variant}` : ''
            ]
        },
    },
}
</script>


<template>
    <div :class="baseClass">
        Seu formulário foi enviado com sucesso
    </div>
</template>


<style scoped>
.alert {
    padding: 5px;
    border-radius: 6px;
    color: gray;
    background-color:blanchedalmond;
}

.alert-success {
    background: #45343f;
    color: white;
}

.alert-danger {
    background: red;
    color: white;
}
</style>