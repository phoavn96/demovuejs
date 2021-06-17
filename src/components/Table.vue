<template>


    <table>
        <thead>
        <tr>
            <th v-for="column in columns">{{column.label}}</th>
        </tr>
        </thead>
        <tbody>
        <tr v-for="item in data">
            <td v-for="column in columns">

                <template v-if="column.field !== 'action'">
                    {{ item[column.field] }}
                </template>
                <template v-else>
                    <a href="javascript:void(0)">Edit</a> | <a href="javascript:void(0)">Delete</a>
                </template>
            </td>

        </tr>
        </tbody>
    </table>
</template>

<script>
    export default {
        name: "Table",
        props: {
            data: {
                type: Array,
                default: () => []
            },
            columns: {
                type: Array,
                default: () => []
            }
        }
    }
</script>

<style scoped>

</style>