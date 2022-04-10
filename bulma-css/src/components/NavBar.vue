<template>
    <nav class="navbar is-dark">
      <div class="navbar-brand">
        <a class="navbar-burger" data-target="navbar-example" :class="{ 'is-active': isActive }" @click="isActive = !isActive">
          <span aria-hidden="true"></span>
          <span aria-hidden="true"></span>
          <span aria-hidden="true"></span>
        </a>
      </div>
      <div id="navbar-example" class="navbar-menu" :class="{ 'is-active': isActive }">
      <!-- This class will float on the left side of the navbar -->
        <div class="navbar-start">
            <a class="navbar-item is-hoverable">Home</a>
            <a class="navbar-item is-hoverable">About</a>
            <div class="navbar-item has-dropdown is-hoverable">
                <a class="navbar-link is-hoverable">Stuff</a>
                <div class="navbar-dropdown is-boxed">
                    <a class="navbar-item" href="#">Option</a> 
                    <hr class="navbar-divider">
                    <a class="navbar-item" href="#">Option</a>                    
                </div>  
            </div>             
        </div>
        <!-- This class will float on the right side of the navbar -->
        <div class="navbar-end">
            <div class="navbar-item">
                <div class="buttons">
                    <a class="button is-outlined">
                        Sign Up
                    </a>
                    <a class="button is-outlined">Log In</a>
                </div>
            </div>
        </div>
      </div>
    </nav>   
</template>

<script>
    export default {
        data() {
            return {
                isActive: false
            }
        }
    }
</script>