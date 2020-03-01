<template>
    <div class="table">
        <table>
            <thead>
            <tr>
                <th v-for="(cfg, index) in config" :key="index">{{cfg.value}}</th>
            </tr>
            </thead>
            <tbody>
            <tr v-for="(row, index) in data" :key="index">
                <td v-for="(obj, index) in config" :key="index">{{row[obj.key]}}</td>
                <td><button>edit</button></td>
            </tr>
            </tbody>
        </table>
    </div>
</template>

<script>
    export default {
        name: "Table",
        props: {
            data: {
                type: Array
            },
            config: {
                type: Array
            }
        }
    }
</script>

<style lang="scss">
    .table {
        border: 1px solid #999;
        color: #333;
        overflow: auto;

        table {
            border-collapse: collapse;
            width: 100%;

            th {
                position: sticky;
                top: 0;
                background: #ccc;
                padding: 6px 5px;
                border-bottom: 1px solid #999;
                text-align: left;
            }
            td {
                padding: 6px 5px;
                text-align: left;
            }
        }
    }
</style>