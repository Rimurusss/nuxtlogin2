<template>
  <div>
    <b-navbar toggleable="lg" type="dark" variant="info">
      <b-navbar-brand href="#">NavBar</b-navbar-brand>

      <b-navbar-toggle target="nav-collapse"></b-navbar-toggle>

      <b-collapse id="nav-collapse" is-nav>
        <b-navbar-nav>
          <nuxt-link class="nav-item nav-link" to="/">หน้าแรก </nuxt-link>
          <nuxt-link class="nav-item nav-link" to="/posts">บทความ </nuxt-link>
          <nuxt-link class="nav-item nav-link" to="/admin">admin </nuxt-link>
        </b-navbar-nav>

        <b-navbar-nav class="ml-auto">
          <b-nav-form>
            <b-form-input size="sm" class="mr-sm-2" placeholder="Search"></b-form-input>
            <b-button size="sm" class="my-2 my-sm-0" type="submit">Search</b-button>
          </b-nav-form>

          <b-nav-item-dropdown text="Lang" right>
            <b-dropdown-item href="#">TH</b-dropdown-item>
            <b-dropdown-item href="#">EN</b-dropdown-item>
            
          </b-nav-item-dropdown>

          <b-nav-item-dropdown right>
            <template #button-content>
              <em>User</em>
            </template>
              <div v-if="$auth.loggedIn">
                  {{$auth.user.email}}
                  <b-dropdown-item test to="/loout">Logout</b-dropdown-item>
              </div>
              <div v-else>
                <b-dropdown-item test to="/login">Login</b-dropdown-item>
                <b-dropdown-item test to="/register">Register</b-dropdown-item>

              </div>
          </b-nav-item-dropdown>
        </b-navbar-nav>
      </b-collapse>
    </b-navbar>
    <nuxt/>
  </div>
</template>