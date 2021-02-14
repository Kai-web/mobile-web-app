<template>
    <div>
        <h1>教师列表</h1>
        <el-table :data="items">
            <el-table-column prop="_id" label="ID" width="330"> </el-table-column>
            <el-table-column prop="name" label="教师姓名"> </el-table-column>
            <el-table-column prop="icon" label="缩略图"> 
                <template slot-scope="scope">
                    <img :src="scope.row.icon" alt="" style="height:5rem; border-radius:50%">
                </template>
            </el-table-column>
            <el-table-column fixed="right" label="操作" width="180">
                <template slot-scope="scope">
                    <el-button type="primary" icon="el-icon-edit" size="small" @click="$router.push(`/items/edit/${scope.row._id}`)">编辑
                    </el-button>
                    <el-button type="danger" icon="el-icon-delete" size="small" @click="remove(scope.row)">删除</el-button>
                </template>
            </el-table-column>
        </el-table>
    </div>
</template>

<script>
    export default {
        data() {
            return {
                items: []
            };
        },
        methods: {
            async fetch() {
                const res = await this.$http.get("rest/items")
                this.items = res.data;
            },
            async remove(row) {
                this.$confirm(`是否确定要删除当前教师 【 ${row.name} 】 `, '提示', {
                    confirmButtonText: '确定',
                    cancelButtonText: '取消',
                    type: 'warning'
                }).then(async () => {
                    const res = this.$http.delete(`rest/items/${row._id}`)      // eslint-disable-line no-unused-vars
                    this.$message({
                        type: 'success',
                        message: '删除成功!'
                    });
                    this.fetch()
                }).catch(() => {
                    this.$message({
                        type: 'info',
                        message: '已取消删除'
                    });
                });
            }
        },
        created() {
            this.fetch()
        }
    }
</script>