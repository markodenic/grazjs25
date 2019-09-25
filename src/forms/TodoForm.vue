<template>
    <el-dialog
        title="New Todo"
        :visible.sync="dialogVisible"
        :before-close="handleClose"
        class="todo-form"
    >
        <el-form
            ref="form"
            :model="form"
            label-position="top"
            @submit.native.prevent
        >
            <el-form-item label="Title">
                <el-input v-model="form.title"/>
            </el-form-item>

            <el-form-item label="Description">
                <el-input
                    type="textarea"
                    v-model="form.description"
                />
            </el-form-item>

            <el-form-item label="Done">
                <el-switch v-model="form.done" />
            </el-form-item>
        </el-form>

        <span slot="footer" class="dialog-footer">
            <el-button @click="handleClose">
                Cancel
            </el-button>
            <el-button
                type="primary"
                @click="submit"
            >
                Confirm
            </el-button>
        </span>
    </el-dialog>
</template>

<script>
    export default {
        name: "TodoForm",
        data () {
            return {
                dialogVisible: false,
                form: {
                    title: '',
                    done: false,
                    description: ''
                }
            }
        },

        methods: {
            show () {
                this.resetForm();
                this.dialogVisible = true;
            },
            close () {
                this.dialogVisible = false;
            },
            resetForm () {
                this.form.title = '';
                this.form.description = '';
                this.form.done = false;
            },
            submit () {
                this.$emit('created', this.form);
                this.close();
            },
            handleClose() {
                this.$confirm('Are you sure to close this dialog?')
                    .then(() => {
                        this.$message('Cancelled');
                        this.close();
                    })
                    .catch(() => {});
            }
        }
    }
</script>

<style lang="less">
    .todo-form {
        .el-form {
            text-align: left;
            &-item__label {
                padding: 0;
            }
        }
    }
</style>