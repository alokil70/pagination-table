<template>
    <div id="app">
        <Table
                v-if="tableData"
                :data='tableData'
                :config="tableConfig"
                :style="{height: '200px'}"
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
                {key: "imageName", value: "Image"},
                {key: "productName", value: "Name"},
                {key: "description", value: "Description"},
                {key: "Category", value: "Category"},
                {key: "createdAt", value: "Created"},
                {key: "price", value: "Price"}
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
