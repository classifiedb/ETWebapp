<template>
  <!-- Sidebar  -->
  <nav id="sidebar" :class="{ active: !$store.state.sidebar }">
    <div
      class="sidebar-header"
      :class="{
        'tw-p-2': $store.state.sidebar,
        'tw-pt-4 tw-pb-0 tw-px-6': !$store.state.sidebar,
      }"
    >
      <b-link class="top-nav-link" :to="{ name: 'index' }">
        <b-img
          v-if="sidebar"
          class="full-logo"
          src="~/assets/ETpic.jpg"
          fluid
          alt="logo"
        ></b-img>
        <span v-if="sidebar">Emperial Technologies</span>
        <b-img
          v-if="!sidebar"
          class="mini-logo"
          src="~/assets/ETpic.jpg"
          fluid
          alt="logo"
        ></b-img>
      </b-link>
    </div>
    <hr />
  </nav>
</template>

<script>
// import { mapActions, mapState } from "vuex";
// import roles from "@/assets/roles.json";

export default {
  data() {
    return {
      menu: [
        {
          title: "Dashboard",
          icon: "fa-home",
          collapsible: true,
          link: { name: "dashboard", params: {}, query: {} },
          links: [],
        },
      ],
    };
  },
  created() {},
  computed: {},
  methods: {
    toggle: function () {
      this.$store.state.sidebar = !this.$store.state.sidebar;
    },
  },
};
</script>

<style>
/* ---------------------------------------------------
    SIDEBAR STYLE
----------------------------------------------------- */

#sidebar {
  min-width: 250px;
  max-width: 250px;
  min-height: 100vh;
  border-right: 1px solid rgb(233, 233, 233);
  /* background: white; */
  transition: all 0.3s;
  box-shadow: 0 1px 3px 0 rgba(0, 0, 0, 0.1), 0 1px 2px 0 rgba(0, 0, 0, 0.06);
  position: relative;
}

#sidebar.active {
  min-width: 80px;
  max-width: 80px;
  text-align: center;
}

#sidebar.active .sidebar-header h3,
#sidebar.active .CTAs {
  display: none;
}

#sidebar.active .sidebar-header strong {
  display: block;
}

#sidebar ul li a {
  text-align: left;
}

#sidebar.active ul li a {
  padding: 20px 10px;
  text-align: center;
  font-size: 0.85em;
}

#sidebar.active ul li a i {
  margin-right: 0;
  display: block;
  font-size: 1.8em;
  margin-bottom: 5px;
}

#sidebar.active ul ul a {
  padding: 10px !important;
}

#sidebar.active .dropdown-toggle::after {
  top: auto;
  bottom: 10px;
  right: 50%;
  -webkit-transform: translateX(50%);
  -ms-transform: translateX(50%);
  transform: translateX(50%);
}

/* #sidebar .sidebar-header {
  padding: 20px;
} */

#sidebar .sidebar-header strong {
  display: none;
  font-size: 1.8em;
}

#sidebar ul.components {
  padding: 20px 0;
}

a.disabled {
  pointer-events: none;
}

#sidebar ul li a {
  padding: 12px;
  font-size: 0.9em;
  font-weight: 500;
  display: block;
  background: white;
  color: rgba(61, 68, 101, 0.7);
  text-transform: uppercase;
}

#sidebar a {
  font-size: 1.1em;
}

#sidebar ul li a:hover {
  color: rgba(61, 68, 101, 0.9);
  background: rgba(61, 68, 101, 0.2);
  text-decoration: none;
}

#sidebar ul li a i {
  margin-right: 10px;
}

#sidebar ul li.active > a,
a[aria-expanded="true"] {
  color: #fff;
  background: #6d7fcc;
}

a[data-toggle="collapse"] {
  position: relative;
}

.dropdown-toggle::after {
  display: block;
  position: absolute;
  top: 50%;
  right: 20px;
  transform: translateY(-50%);
}

ul ul a {
  font-size: 0.9em !important;
  padding-left: 30px !important;
  background: #6d7fcc;
}

/* ---------------------------------------------------
    CONTENT STYLE
----------------------------------------------------- */

#content {
  width: 100%;
  padding: 20px;
  min-height: 100vh;
  transition: all 0.3s;
}

/* ---------------------------------------------------
    MEDIAQUERIES
----------------------------------------------------- */

@media (max-width: 768px) {
  #sidebar {
    min-width: 80px;
    max-width: 80px;
    text-align: center;
    margin-left: -80px !important;
  }
  .dropdown-toggle::after {
    top: auto;
    bottom: 10px;
    right: 50%;
    -webkit-transform: translateX(50%);
    -ms-transform: translateX(50%);
    transform: translateX(50%);
  }
  #sidebar.active {
    margin-left: 0 !important;
  }
  #sidebar .sidebar-header h3,
  #sidebar.active .icon-text,
  #sidebar .CTAs {
    display: none;
  }
  #sidebar .sidebar-header strong {
    display: block;
  }
  #sidebar ul li a {
    padding: 20px 10px;
  }
  #sidebar ul li a span {
    font-size: 0.85em;
  }
  #sidebar ul li a i {
    margin-right: 0;
    display: block;
  }
  #sidebar ul ul a {
    padding: 10px !important;
  }
  #sidebar ul li a i {
    font-size: 1.3em;
  }
  #sidebar {
    margin-left: 0;
  }
  #sidebarCollapse span {
    display: none;
  }
}

/* ---------------------------------------------------
    LOGO / TOP NAVIGATION BAR LINK
----------------------------------------------------- */
.full-logo {
  /* position: absolute; */
  /* z-index: -10; */
  /* bottom: 0; */
  width: 30%;
  display: inline;
}
.top-nav-link {
  font-size: 24px !important;
}
.mini-logo {
  margin-bottom: 10px;
}

/* ---------------------------------------------------
    INSTITUTION STYLING
----------------------------------------------------- */
.labs {
  padding-left: 10px;
  font-weight: bold;
}
.institution-link {
  padding: 12px;
  cursor: pointer;
}
.institution-link:hover {
  background-color: rgba(61, 68, 101, 0.2);
}
.institution {
  /* padding-left: 25px; */
  font-weight: normal;
}
.institution-collection {
  padding-left: 35px;
}
.nuxt-link-exact-active {
  color: white !important;
  background-color: rgba(48, 51, 65, 0.4) !important;
}
</style>
