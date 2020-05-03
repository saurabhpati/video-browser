<template>
    <div class="details">
        <h4>{{video.snippet.title}}</h4>
        <p>{{video.snippet.description}}</p>
    </div>
</template>

<script>
export default {
    name: "VideoDetail",
    props: ["video"]
}
</script>

<style scoped>
.details {
    margin-top: 10px;
    border: 1px solid #ddd;
    padding: 10px;
    border-radius: 4px;
}
</style>