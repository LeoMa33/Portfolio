<template>
    <div :class="{long:props.long}">
        <input v-if="!long" :id="props.id" :name="props.id" :type="props.type" :placeholder="props.title">
        <textarea v-else :id="props.id" :name="props.id" :type="props.type" :placeholder="props.title"></textarea>
        <label :for="props.id">{{  props.title }}</label>
    </div>
</template>

<script setup lang="ts">
const props = defineProps(["title", "type", "id", "long"]);
</script>

<style scoped>
div {
    display: flex;
    flex-direction: column-reverse;
    width: 100%;
    height: fit-content;
}

.long {
    flex-grow: 1;
}

label {
    color: var(--medium);
    font-weight: 600;
}

input {
    background: none;
    border: none;
    padding-top: 5px;
    padding-bottom: 5px;
    font-size: 20px;
    color: black;
    border-bottom-style: solid;
    border-bottom-width: 3px;
    border-bottom-color: var(--light);
}

input::placeholder {
    color: var(--light);
}

input:focus {
    border-color: #00B578;
    outline: none;
    border-bottom-style: solid;
    border-bottom-width: 3px;
}

input:focus + label {
    color: #00B578;
}

textarea {
    background: none;
    border: none;
    padding-top: 5px;
    padding-bottom: 5px;
    font-size: 20px;
    color: black;
    border-bottom-style: solid;
    border-bottom-width: 3px;
    border-bottom-color: var(--light);
    resize: none;
    flex-grow: 1;
}

textarea::placeholder {
    color: var(--light);
}

textarea:focus {
    border-color: #00B578;
    outline: none;
    border-bottom-style: solid;
    border-bottom-width: 3px;
}

textarea:focus + label {
    color: #00B578;
}
</style>