<template>
    <nav class="navbar navbar-dark sticky-top bg-dark flex-md-nowrap p-0">
      <router-link :to="{name: 'Dashboard'}" class="navbar-brand col-sm-3 col-md-2 mr-0">RESTaurant</router-link>
      <!-- <input class="form-control form-control-dark w-100" type="text" placeholder="Search" aria-label="Search"> -->
      <p class="col-sm-6 form-control-dark">Logged in as {{user.name}} ({{user.email}})</p>
      <ul class="navbar-nav px-3">
        <li class="nav-item text-nowrap">
          <a class="nav-link" href="#" @click="logout">Sign out</a>
        </li>
      </ul>
    </nav>
</template>

<script>
import { mapState } from 'vuex';
export default {
  name: 'Navbar',
  data () {
    return {
    }
  },
  computed: mapState('auth', {
    user: state => state.user
  }),
  methods: {
    logout(){
      this.$store.dispatch('auth/logout');
      this.$router.push('/')
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.navbar-brand {
  padding-top: .75rem;
  padding-bottom: .75rem;
  font-size: 1rem;
  background-color: rgba(0, 0, 0, .25);
  box-shadow: inset -1px 0 0 rgba(0, 0, 0, .25);
}

.navbar .form-control {
  padding: .75rem 1rem;
  border-width: 0;
  border-radius: 0;
}

.form-control-dark {
  color: #fff;
  /* background-color: rgba(255, 255, 255, .1); */
  border-color: rgba(255, 255, 255, .1);
}

.form-control-dark:focus {
  border-color: transparent;
  box-shadow: 0 0 0 3px rgba(255, 255, 255, .25);
}
</style>
