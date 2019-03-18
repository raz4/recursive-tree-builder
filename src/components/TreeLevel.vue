<template>
    <div>
        <div class="container">
            <div class="item" v-for="node in root" :key="node.id" @click="updateSelectedChild(node)">
                <TreeCard v-bind:class="{ unselected: !(selectedNode == node) }" :data="node"/>
            </div>
        </div>
        <TreeLevel v-if="selectedNodeChildren" :root="selectedNodeChildren"/>
    </div>
</template>

<script>
import TreeCard from "./TreeCard.vue";
import TreeLevel from "./TreeLevel.vue";

export default {
    beforeCreate () {
        this.$options.components.TreeLevel = require('./TreeLevel.vue').default
    },
    components: {
        TreeCard,
        TreeLevel
    },
    props: ["root"],
    data() {
        return {
            selectedNode: null,
            selectedNodeChildren: null
        }
    },
    methods: {
        updateSelectedChild (node) {
            console.log("selected node: ", node.children)
            if (this.selectedNode == node){
                this.selectedNode = null
                this.selectedNodeChildren = null
            }
            else {
                this.selectedNodeChildren = node.children
                this.selectedNode = node
            }
        }
    },
    mounted() {
        // console.log("level")
        // console.log(this.root)
        console.log("root: ", this.root)
    }
}
</script>

<style scoped>
.container {
    display: flex;
    justify-content: center;
}
.item {
    order: 0;
    margin: 5px;
}
.unselected {
    opacity: 0.5;
}
</style>