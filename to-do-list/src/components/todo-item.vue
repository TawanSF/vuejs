<template>
<div>
    <span>{{ title }}</span>
    <button @click="$emit('remove')">Remove</button>
</div>
</template>

<script>
export default {
    props: ['title']
}
</script>

