<template>
    <div class="body">
        <div class="title">
            {{data.title}}
        </div>
        <div class="data">
            Data: {{data.data}}
        </div>
    </div>
</template>

<script>
export default {
    props: ["data"],
}
</script>

<style scoped>
.title {
    background: mediumseagreen;
    display: block;
    font-weight: bold;
    font-size: 18px;
    padding: 10px 15px;
    border-radius: 5px 5px 0 0;
}
.data {
    display: block;
    padding: 10px 10px;
}
.body {
    background-color: peru;
    width: 250px;
    height: 260px;
    border-radius: 5px;
    float: left;
}
</style>