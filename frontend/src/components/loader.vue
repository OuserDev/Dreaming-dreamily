<template>
    <div class="spinner-container" style="z-index: 2">
        <div class="spinner" />
    </div>
</template>

<script>
export default {};
</script>

<style scoped>
.spinner-container {
    position: absolute;
    top: 43vh;
}
.spinner {
    width: 100px;
    height: 100px;
    border-radius: 50%;
    border: 10px solid #e0e0e0;
    border-bottom: 10px solid #bb00ff;
    animation: spin 1s linear infinite;
    position: relative;
}
@keyframes spin {
    from {
        transform: rotate(0deg);
    }
    to {
        transform: rotate(360deg);
    }
}
</style>
