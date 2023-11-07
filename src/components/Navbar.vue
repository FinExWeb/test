<script>
export default {
    methods: {
        ctrl_V(e) {
            if (e.ctrlKey && e.key === 'v') {
                alert(true)
            }
        },
        showNav() {
            const ulList = document.getElementById('ulList');
            ulList.classList.add('show-nav');
        }
    },
    mounted() {
        document.addEventListener('keyup', this.ctrl_V);
    },
    beforeDestroy() {
        document.removeEventListener('keyup', this.ctrl_V);
    },
};
</script>

<template>
    <div class="navbar justify-content-evenly py-3">
        <div class="brand">
            <img class="img-fluid" src="/logo.svg" alt="logo">
        </div>

        <div class="nav-right navbar">
            <div class="mobil-views nav">
                <a href="/" class="mx-4">
                    <div class="news d-flex align-items-center">
                        <code class="text-uppercase">my team</code>
                        <span>news</span>
                    </div>
                </a>
                <ul class="nav" id="ulList">
                    <li>
                        <a href="/" class="nav-link">home</a>
                    </li>
                    <li>
                        <a href="/" class="nav-link">sponsor</a>
                    </li>
                    <li>
                        <a href="/" class="nav-link">contact</a>
                    </li>
                </ul>
            </div>
            <div class="search mx-3">
                <button @keyup.ctrl.v="ctrl_V">
                    ctrl + v
                </button>
            </div>
            <div class="form mx-3">
                <button>Login</button>
            </div>
        </div>
        <button class="show-navbar" v-on:click="showNav">
            <i class="fas fa-bars"></i>
        </button>
    </div>
</template>

<style scoped>
.show-nav {
    display: block !important;
}

.navbar {
    background: rgb(15 23 42);
    font-family: 'Electrolize', sans-serif;
}

.navbar .brand img {
    width: 50px;
}

.navbar ul li a {
    color: #ccdae3;
    font-size: 16px;
    text-transform: uppercase;
    opacity: 0.8;
}

.navbar .news span {
    background-color: #006aff;
    border-radius: 5px;
    padding: 5px 10px;
    text-transform: uppercase;
    margin: 0 10px;
    /* color: rgb(15 23 42); */
    color: #ccdae3;
    box-shadow: 0 0 10px #006aff;
}

.navbar .news code {
    color: #006aff;
    text-shadow: 0 0 10px #006aff;
}

.navbar .form button {
    border: none;
    outline: none;
    background-color: #006aff;
    border-radius: 10px;
    padding: 6px 15px;
    color: #ccdae3;
    width: 100px;
    /* box-shadow: 0 0 10px #006aff; */
    letter-spacing: 1px;
    font-size: 1.1rem;
}

.navbar .search button {
    /* border: 1px solid #68686865; */
    border: none;
    outline: none;
    background: #006aff;
    border-radius: 10px;
    padding: 6px 15px;
    color: #ccdae3;
    width: 100px;
    text-transform: uppercase;
    box-shadow: 0 0 20px -5px #006aff;
}

.navbar .show-navbar {
    border: none;
    display: none;
    outline: none;
    background: none;
    color: #ccdae3;
    font-size: 1.6rem;
}

@media screen and (max-width: 800px) {
    .navbar .mobil-views {
        display: none;
    }

    .navbar .form button {
        padding: 10px 15px;
        width: 80px;
        font-size: 0.9rem;
        height: 40px;
    }

    .navbar .search button {
        padding: 10px 15px;
        width: 80px;
        font-size: 0.7rem;
        height: 40px;
    }

    .navbar .search {
        margin-right: 0.5rem !important;
        margin-left: 0.5rem !important;
    }

    .navbar .form {
        margin-right: 0.5rem !important;
        margin-left: 0.5rem !important;
    }

    .navbar .brand img {
        width: 40px;
    }

    .navbar .show-navbar {
        display: block;
    }
}
</style>