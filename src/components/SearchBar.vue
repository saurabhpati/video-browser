<template>
    <div>
        <input @input="onInput"/>
    </div>
</template>

<script>
export default {
    name: 'SearchBar',
    methods: {
        onInput(event) {
            this.$emit('termChange', event.target.value);
        }
    }
}
</script>

<style scoped>
    input {
        width: 75%;
    }

    div {
        margin-top: 20px;
        margin-bottom: 20px;
        text-align: center;
    }
</style>