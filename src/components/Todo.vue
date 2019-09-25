<template>
    <li class="todo">
        <el-row
            type="flex"
            align="middle"
        >
            <el-col
                :xs="16"
                :sm="20"
                class="todo__content"
            >
                {{ todo.title }} ({{ todo.done ? 'Yep!' : 'Nah!' }})
            </el-col>

            <el-col
                class="todo__actions"
                :xs="8"
                :sm="4"
            >
                <el-button
                    size="small"
                    type="success"
                    @click="$emit('toggle', todo)"
                >
                    toggle
                </el-button>
            </el-col>
        </el-row>
    </li>
</template>

<script>
    export default {
        name: 'Todo',
        props: {
            todo: {
                type: Object,
                required: true,
            }
        }
    }
</script>

<style lang="less">
    .todo {
        list-style: none;
        margin-bottom: 10px;
        &__content {
            text-align: left;
        }
        &__actions {
            text-align: right;
        }
    }
</style>