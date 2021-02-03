<template>
    <header class="header">
        <img  src='../../../src/assets/UPLogo2.png' alt="UnderPinned Logo"  style="width: 200px">
        <h1>Current Posts </h1>
    </header>
</template>

<script> 
    export default {
        name: "Header" 
    }
</script>

<style scoped>
    .header {
        background: navy;
        color: white;
        text-align: center;
        padding: 10px;
    }
    .header a {
        color: white;
        padding-right: 5px;
    }
</style>