<template>
    <div id="app">
        <div id="nav">
            <router-link to="/">
                Vue Todos
            </router-link>
            |
            <router-link to="/about">
                About
            </router-link>
        </div>

        <router-view/>

        <footer>
            Made by <a href="https://markodenic.com">Marko</a>.
        </footer>
    </div>
</template>

<style>
    html, body {
        margin: 0;
    }
    #app {
        font-family: 'Avenir', Helvetica, Arial, sans-serif;
        -webkit-font-smoothing: antialiased;
        -moz-osx-font-smoothing: grayscale;
        text-align: center;
        color: #2c3e50;
        display: flex;
        flex-direction: column;
    }

    #nav {
        padding: 30px;
    }

    #nav a {
        font-weight: bold;
        color: #2c3e50;
    }

    #nav a.router-link-exact-active {
        color: #42b983;
    }

    footer {
        padding: 15px;
    }
</style>
