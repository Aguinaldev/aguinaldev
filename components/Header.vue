<template>
  <div class="container-fluid">
    <div class="row bg-info">
      <div class="col">
        <b-navbar toggleable="lg" type="dark" variant="info">
          <b-navbar-brand href="#" v-b-toggle.sidebar-1>
            <b-icon-house-door></b-icon-house-door>
            Menu
          </b-navbar-brand>

          <b-navbar-toggle target="nav-collapse"></b-navbar-toggle>

          <b-collapse id="nav-collapse" is-nav>
            <b-navbar-nav v-for="item in menuItems" :key="item.id">
              <b-nav-item :href="item.link">{{item.label}}</b-nav-item>
            </b-navbar-nav>

            <!-- Right aligned nav items -->
            <b-navbar-nav class="ml-auto">
              <b-nav-form>
                <b-form-input
                  size="sm"
                  class="mr-sm-2"
                  placeholder="Search"
                ></b-form-input>
                <b-button size="sm" class="my-2 my-sm-0" type="submit"
                  >Search</b-button
                >
              </b-nav-form>

              <b-nav-item-dropdown text="Lang" right>
                <b-dropdown-item href="#">EN</b-dropdown-item>
                <b-dropdown-item href="#">ES</b-dropdown-item>
                <b-dropdown-item href="#">RU</b-dropdown-item>
                <b-dropdown-item href="#">FA</b-dropdown-item>
              </b-nav-item-dropdown>

              <b-nav-item-dropdown right>
                <!-- Using 'button-content' slot -->
                <template #button-content>
                  <em>User</em>
                </template>
                <b-dropdown-item href="#">Profile</b-dropdown-item>
                <b-dropdown-item href="#">Sign Out</b-dropdown-item>
              </b-nav-item-dropdown>
            </b-navbar-nav>
          </b-collapse>
        </b-navbar>
        <!-- <b-button v-b-toggle.sidebar-1>Toggle Sidebar</b-button> -->

        <b-sidebar id="sidebar-1" title="Sidebar" shadow visible>
          <div class="px-3 py-2">
            <ul id="menu-lateral">
              <li v-for="item in menuItems" :key="item.id">
                  <a :href="item.link">
                    <b-icon-house-door v-if="item.label === 'Home'"></b-icon-house-door>
                    <b-icon-card-checklist v-if="item.label === 'Cronogramas'"></b-icon-card-checklist>
                    <b-icon-plus-circle v-if="item.label === 'Criar Novo'"></b-icon-plus-circle>
                    {{item.label}}
                  </a>
              </li>
            </ul>

            <b-img
              src="https://picsum.photos/500/500/?image=54"
              fluid
              thumbnail
            ></b-img>
          </div>
        </b-sidebar>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name:"Header",
  data:() => ({
    menuItems: [
      {
        id:1,
        label:"Home",
        link:"/"
      },
      {
        id:2,
        label:"Cronogramas",
        link:"/cronogramas"
      },
      {
        id:3,
        label:"Criar Novo",
        link:"/criar-cronograma"
      },
    ],
  })
};
</script>

<style>
</style>
