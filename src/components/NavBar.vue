<template>
  <div>
    <b-navbar type="dark" variant="dark">
      <b-navbar-brand ><router-link to="/" style="color:#FFFFFF">WebBlog</router-link> </b-navbar-brand>
        <router-link to="/Mystories">Mystories</router-link> |
        <router-link to="/about">About</router-link>
      <b-navbar-nav class="mx-auto">
        <b-navbar-form>
            <b-input-group>
                <b-form-input type="search"></b-form-input>
               
                <b-input-group-append>
                    <b-button variant="outline-secondary">search</b-button>
                </b-input-group-append>
            </b-input-group>
        </b-navbar-form>
      </b-navbar-nav>
     
      
    </b-navbar>
  </div>
</template>

<script>
import { BNavbar,BNavbarNav,BNavbarBrand } from "bootstrap-vue";
import {BNavForm,BInputGroup,BInputGroupAppend,BButton,BFormInput} from "bootstrap-vue"
export default {
  name: "NavBar",
  components: {
    "b-navbar": BNavbar,
    "b-navbar-brand": BNavbarBrand,
    "b-navbar-form":BNavForm,
    "b-navbar-nav":BNavbarNav,
    "b-input-group":BInputGroup,
    "b-input-group-append":BInputGroupAppend,
    "b-button":BButton,
    "b-form-input":BFormInput,
  }
};
</script>

<style scoped>
</style>

