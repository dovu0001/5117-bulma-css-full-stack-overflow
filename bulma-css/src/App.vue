<template>
  <div>
    <nav class="breadcrumb is-centered has-bullet-separator is-large">
      <ul>
        <li>
          <router-link to="/"> 
            <span class="icon is-small"><i class="fas fa-home" aria-hidden="true"></i></span> 
            <span>Home</span>
          </router-link>
        </li>
        <li><router-link to="/about">About</router-link></li>
        <li><router-link to="/form">Form</router-link></li>
      </ul>
    </nav>

    <aside v-show='sidebarActive' class="menu">
          <p class="menu-label">
            General
          </p>
          <ul class="menu-list">
            <li>
              <router-link to="/"> 
                  <span class="icon is-small"><i class="fas fa-home" aria-hidden="true"></i></span> 
                  <span> Home</span>
              </router-link>
            </li>
            <li><router-link to="/about">About</router-link></li>
            <li><router-link to="/form">Form</router-link></li>
          </ul>
          <p class="menu-label">
            Administration
          </p>
          <ul class="menu-list">
            <li><a>Team Settings</a></li>
            <li>
              <a class="is-active">Manage Your Team</a>
              <ul>
                <li><a>Members</a></li>
                <li><a>Plugins</a></li>
                <li><a>Add a member</a></li>
              </ul>
            </li>
            <li><a>Invitations</a></li>
            <li><a>Cloud Storage Environment Settings</a></li>
            <li><a>Authentication</a></li>
          </ul>
          <p class="menu-label">
            Transactions
          </p>
          <ul class="menu-list">
            <li><a>Payments</a></li>
            <li><a>Transfers</a></li>
            <li><a>Balance</a></li>
          </ul>
      </aside>
      <div @click='toggleSidebar()' id="sidebar-toggle" v-bind:class="{ 'sidebar-active': sidebarActive }">
        <span class="icon is-large"><i class="fas fa-2x fa-bars" aria-hidden="true"></i></span> 
      </div>



    <router-view/>
  </div>

  
</template>

<script>

export default({
  data() {
    return {
      sidebarActive: false
    }
  },
  methods: {
    toggleSidebar() {
        this.sidebarActive = !this.sidebarActive;
    }
  }
})

</script>


<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
  text-align: center;
}



nav {
  padding: 30px;
}

nav a {
  font-weight: bold;
  color: #2c3e50;
}

nav a.router-link-exact-active {
  color: #42b983;
}


.breadcrumb a{
  color: rgb(12, 83, 150);
}


.menu {
    max-width: 200px;
    position: absolute;
    left: 0;
    top: 0;
    height: 100%;
    text-align: left;
    box-shadow: 5px 5px 5px rgb(182, 182, 182);
}

#sidebar-toggle{
    position: absolute;
    left: 0;
    top: 0;
}

.sidebar-active {
    left: 200px !important;
}

aside a.router-link-exact-active {
  background-color: #485fc7;
  color: white;
}

</style>
