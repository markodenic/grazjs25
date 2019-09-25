<template>
    <div class="home">
        <el-button
            type="primary"
            @click="showTodoForm">
            add todo
        </el-button>

        <el-row
            type="flex"
            justify="center"
        >
            <el-col
                :xs="22"
                :sm="12"
                :md="8"
                class="home__todos-wrapper"
            >
                <h1>
                    Todos:
                </h1>

                <ul>
                    <todo
                        v-for="(todo, index) in todos"
                        :todo="todo"
                        :key="index"
                        @toggle="toggleTodo"
                    />
                </ul>
            </el-col>
        </el-row>

        <el-row
            type="flex"
            justify="center"
        >
            <el-col
                class="home__todos-wrapper"
                :xs="22"
                :sm="12"
                :md="8"
            >
                <h1 v-if="notDoneTodos.length > 0">
                    Not Done Todos:
                </h1>

                <h1 v-else>
                    Hurray! All done!
                </h1>

                <ul>
                    <todo
                        v-for="(todo, index) in notDoneTodos"
                        :todo="todo"
                        :key="index"
                        @toggle="toggleTodo"
                    />
                </ul>
            </el-col>
        </el-row>

        <todo-form
            ref="todoForm"
            @created="addTodo"
        />
    </div>
</template>

<script>
    // @ is an alias to /src
    import Todo from '@/components/Todo.vue'
    import TodoForm from '@/forms/TodoForm.vue'

    export default {
        name: 'home',
        components: {
            Todo,
            TodoForm
        },
        data() {
            return {
                todos: [
                    {
                        title: 'grazjs 25 introduction',
                        description: 'Just a description',
                        done: true
                    },
                    {
                        title: 'talk about reactivity',
                        description: 'Just a description',
                        done: false
                    },
                    {
                        title: 'talk about components',
                        description: 'Just a description',
                        done: false
                    }
                ]
            }
        },
        computed: {
            notDoneTodos() {
                let notDoneTodos = [];
                this.todos.forEach(function (todo) {
                    if (!todo.done) {
                        notDoneTodos.push(todo);
                    }
                });
                return notDoneTodos;
            }
        },
        methods: {
            showTodoForm () {
                this.$refs.todoForm.show();
            },
            addTodo(todo) {
                this.todos.push(todo);
                this.$notify({
                    title: 'Todo added',
                    message: 'Successfully added new todo: ' + todo.title,
                    type: 'success'
                });
            },
            toggleTodo(todo) {
                todo.done = !todo.done;
            }
        }
    }
</script>

<style lang="less">
    .home {
        &__todos-wrapper {
            max-width: 450px;
        }
    }
</style>