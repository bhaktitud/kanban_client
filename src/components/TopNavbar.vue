<template>
  <!--Navbar Section-->
    <section class="top-navbar">
        <nav class="topbar border border-5 border-primary fixed-top split-nav">
            <div class="navbar-brand">
                <p >KANBAN - PROJECT 51</p>
            </div>
            <div class="collapsible">
                <ul class="inline">
                    <li class="paper-btn btn-small pb-0 pt-0"><h5><a href="https://kanban4.docs.apiary.io/"></a>Documentation</h5></li>
                    <li class="paper-btn btn-small pb-0 pt-0"><h6><a href="https://github.com/bhaktitud/kanban_client"></a>Github</h6></li>
                    <li v-if="isLogin" v-on:click="logout" class="logout-btn paper-btn btn-small">Logout</li>
                </ul>
            </div>
        </nav>
    </section>
    <!---->
</template>

<script>
export default {
    name: "TopNavbar",
    data () {
        return {
            isLogin : false
        }
    },
    created () {
        const access_token = localStorage.getItem('access_token')
        if(access_token){
            this.isLogin = true
        }
    },
    methods : {
        logout : function() {
            localStorage.clear()
            this.$emit('changePage', 'home')
        }
    }
}
</script>

<stylec scoped>
.topbar {
    background-color: ivory;
    display: flex;
    flex-direction: row;
    align-items: baseline;
    
}

</style>