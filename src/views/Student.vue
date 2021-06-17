<template>

    <div>
        <Table :columns="columns" :data="students"></Table>
    </div>
</template>

<script>
    import Table from "../components/Table";

    export default {
        name: "Student",
        components: {
            Table
        },

        data() {
            return {
                title: 'student management',
                students: [],
                columns: [
                    {
                        label: 'Roll Number',
                        field: 'rollNumber',
                    },
                    {
                        label: 'Full Name',
                        field: 'fullName',
                    },
                    {
                        label: 'Email',
                        field: 'email',
                    }, {
                        label: 'Status',
                        field: 'status',
                    },
                    {
                        label: 'Action',
                        field: 'action',
                    }]


            }
        },
        mounted() {
            this.loadStudent()
        },

        methods: {
            loadStudent() {
                fetch('http://localhost:8888/student/list')
                    .then(response => response.json())
                    .then(data => this.students = data)
            }
        }
    }


</script>

<style scoped>

</style>