<template>
    <a href="javascript:;" v-on:click="randomtool">Random tool</a>
</template>

<script>
export default {
    name: 'RandomTool',
    methods: {
        randomtool: function (event) {
            const t_tools = this.$store.getters['getTools'];
            const r = Math.floor(Math.random() * t_tools.length);
            const tool = this.tool = t_tools[r];
            this.$store.commit( 'resetSearchTerm' );
            this.$router.push( '/tool/'+tool.slug );
        },
    },
}
</script>
