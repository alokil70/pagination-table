<template>
    <table>
        <thead>
        <tr>
            <th v-for="head in config" :key="head.key">{{head.value}}</th>
        </tr>
        </thead>
        <tbody>
        <tr>
            <td></td>
        </tr>
        </tbody>
    </table>
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