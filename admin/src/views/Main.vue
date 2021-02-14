<template>
    <el-container style="height: 100vh">
        <el-header style="text-align: right; font-size: 12px">
            <div class="logo-title">
                <img src="../assets/logo1.png" alt="" />
                <h2 style="font-size: 21px">蜜丝卡伦后台管理系统</h2>
                <el-dropdown style="float: right">
                    <i class="el-icon-setting" style="margin-right: 15px"></i>
                    <el-dropdown-menu slot="dropdown">
                        <el-dropdown-item>查看</el-dropdown-item>
                        <el-dropdown-item>新增</el-dropdown-item>
                        <el-dropdown-item>删除</el-dropdown-item>
                    </el-dropdown-menu>
                    <span>王小虎</span>
                </el-dropdown>
            </div>
        </el-header>
        <el-container>
            <el-aside width="201px" style="background-color: #250246">
                <el-menu router :default-openeds="['1', '3']">
                    <el-submenu index="1">
                        <template slot="title"><i class="el-icon-message"></i>内容管理</template>
                        <el-menu-item-group>
                            <template slot="title">分类</template>
                            <el-menu-item index="/categories/create">新建分类</el-menu-item>
                            <el-menu-item index="/categories/list">分类列表</el-menu-item>
                        </el-menu-item-group>
                        <el-menu-item-group title="分组2">
                            <el-menu-item index="1-3">选项3</el-menu-item>
                        </el-menu-item-group>
                        <el-submenu index="1-4">
                            <template slot="title">选项4</template>
                            <el-menu-item index="1-4-1">选项4-1</el-menu-item>
                        </el-submenu>
                    </el-submenu>
                    <el-submenu index="2">
                        <template slot="title"><i class="el-icon-menu"></i>导航二</template>
                        <el-menu-item-group>
                            <template slot="title">分组一</template>
                            <el-menu-item index="2-1">选项1</el-menu-item>
                            <el-menu-item index="2-2">选项2</el-menu-item>
                        </el-menu-item-group>
                        <el-menu-item-group title="分组2">
                            <el-menu-item index="2-3">选项3</el-menu-item>
                        </el-menu-item-group>
                        <el-submenu index="2-4">
                            <template slot="title">选项4</template>
                            <el-menu-item index="2-4-1">选项4-1</el-menu-item>
                        </el-submenu>
                    </el-submenu>
                    <el-submenu index="3">
                        <template slot="title"><i class="el-icon-setting"></i>导航三</template>
                        <el-menu-item-group>
                            <template slot="title">分组一</template>
                            <el-menu-item index="3-1">选项1</el-menu-item>
                            <el-menu-item index="3-2">选项2</el-menu-item>
                        </el-menu-item-group>
                        <el-menu-item-group title="分组2">
                            <el-menu-item index="3-3">选项3</el-menu-item>
                        </el-menu-item-group>
                        <el-submenu index="3-4">
                            <template slot="title">选项4</template>
                            <el-menu-item index="3-4-1">选项4-1</el-menu-item>
                        </el-submenu>
                    </el-submenu>
                </el-menu>
            </el-aside>
            <el-main>
                <router-view></router-view>
            </el-main>
        </el-container>
    </el-container>
</template>
<style>
    .el-header {
        background-color: #250246;
        color: #fff;
        line-height: 60px;
    }

    .el-aside {
        color: #333;
    }

    .el-submenu__title,
    .el-menu-item,
    .el-dropdown,
    .el-submenu__title i {
        color: #fff;
    }

    .el-menu-item-group__title {
        color: #3e0078;
        background-color: #f5dd88;
    }

    .el-submenu__title:hover,
    .el-menu-item:hover {
        color: #000;
    }

    .el-submenu__title:hover .el-icon-message,
    .el-submenu__title:hover .el-icon-arrow-down,
    .el-submenu__title:hover .el-icon-menu,
    .el-submenu__title:hover .el-icon-setting {
        color: #000;
    }

    .el-menu {
        border-right: solid 1px #e6e6e6;
        list-style: none;
        position: relative;
        margin: 0;
        padding-left: 0;
        background-color: #250246;
        width: 201px;
    }

    .logo-title {
        height: 60px;
        display: flex;
        justify-content: space-between;
        align-items: center;
    }
</style>

<script>
    export default {
        data() {
            const item = {
                date: "2016-05-02",
                name: "王小虎",
                address: "上海市普陀区金沙江路 1518 弄",
            };
            return {
                tableData: Array(20).fill(item),
            };
        },
    };
</script>