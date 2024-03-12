<script setup>
let props = defineProps({
    content: String,
    bgcolor: String,
    hoverbgcolor: String,
});
</script>
<template>
    <button role="button" type="button">{{ content }}</button>
</template>
<style lang="scss" scoped>
button {
    padding: 20px;
    font-size: 1.2rem;
    border: none;
    cursor: pointer;
    background-color: v-bind("props.bgcolor");
    color: white;
    font-weight: 700;
    &:hover {
        background-color: v-bind("props.hoverbgcolor");
    }
}
</style>
