<template>
    <div id="app">
        <Table
                v-if="tableData"
                :data='tableData'
                :config="tableConfig"
        />
    </div>
</template>

<script>
    import Table from './components/Table'

    export default {
        name: 'App',
        components: {
            Table
        },
        data: () => ({
            tableData: undefined,
            tableConfig: [
                {key: "img", value: "Image"},
                {key: "name", value: "Name"},
                {key: "description", value: "Desc"},
                {key: "category", value: "Category"},
                {key: "price", value: "Price"},
            ]
        }),
        mounted() {
            this.$axios.get('http://localhost:9090/api/products')
                .then(data => this.tableData = data.data)
        }
    }
</script>

<style>
</style>
