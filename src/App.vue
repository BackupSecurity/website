<template>
  <div id="app">
    <b-navbar variant="white" type="light">
      <b-navbar-nav>
        <b-nav-item
          link-classes="text-primary"
          active-class="text-primary text-bold"
          :to="{ name: 'Home' }"
          >Home</b-nav-item
        >
        <b-nav-item-dropdown toggle-class="text-primary" text="Services">
          <b-dropdown-item :to="{ name: 'Alarms' }"
            >Alarm Fitting &amp; Monitoring</b-dropdown-item
          >
          <b-dropdown-item :to="{ name: 'Cctv' }"
            >CCTV Installation</b-dropdown-item
          >
          <b-dropdown-item :to="{ name: 'ConciergeService' }"
            >Concierge Service</b-dropdown-item
          >
          <b-dropdown-item :to="{ name: 'SecurityPatrols' }"
            >Security Patrols</b-dropdown-item
          >
        </b-nav-item-dropdown>
        <b-nav-item link-classes="text-primary" :to="{ name: 'Contact' }"
          >Contact Us</b-nav-item
        >
      </b-navbar-nav>
    </b-navbar>
    <router-view />
  </div>
</template>

<style lang="scss">
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  // text-align: center;
  // color: #2c3e50;
}

#nav {
  padding: 30px;

  a {
    font-weight: bold;
    color: #2c3e50;

    &.router-link-exact-active {
      color: #42b983;
    }
  }
}
</style>
