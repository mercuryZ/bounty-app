<template>
  <v-app id="inspire">
    <v-app-bar  
      app
      clipped-left
      color="blue darken-3"
      dark
      elevation="5"
      flat
    >
      <v-toolbar-title
        style="width: 300px"
        class="ml-0 pl-3"
      >
        <v-app-bar-nav-icon @click.stop="drawer = !drawer"></v-app-bar-nav-icon>
        <router-link tag="span" class="hidden-sm-and-down" to="/">THE Lab </router-link>
        <v-btn
          icon
          large
        >
          <v-avatar
            size="32px"
            item
          >
            <v-img
              src="https://cdn.vuetifyjs.com/images/logos/logo.svg"
              alt="Vuetify"
            >
            </v-img></v-avatar>
        </v-btn>
      </v-toolbar-title>
      <v-text-field
        flat
        solo-inverted
        hide-details
        prepend-inner-icon="mdi-magnify"
        label="Search"
        class="hidden-sm-and-down"
      ></v-text-field>
      <v-spacer></v-spacer>
      <v-btn icon>
        <v-icon>mdi-apps</v-icon>
      </v-btn>
      <v-btn icon>
        <v-icon>mdi-home</v-icon>
      </v-btn>
    </v-app-bar>
    <v-navigation-drawer
      app
      clipped
      v-model="drawer"
    >
      <v-list-item>
        <v-list-item-content class="white">
          <v-list-item-title class="title">
            Application
          </v-list-item-title>
          <v-list-item-subtitle>
            subtext
          </v-list-item-subtitle>
        </v-list-item-content>
      </v-list-item>
    </v-navigation-drawer>

  </v-app>
</template>

<script>
  export default {
    data: () => ({
      drawer: false,
      links: [
        ['mdi-inbox-arrow-down', '主页', '/'],
        ['mdi-send', '关于', '/about'],
      ],
      items: [
      { icon: 'contacts', text: 'Contacts', to: '/contacts', heading: '2018' },
      { icon: 'history', text: 'Frequently contacted', to: '/page1' },
      { icon: 'content_copy', text: 'Duplicates', to: '/404' },
      {
        icon: 'keyboard_arrow_up',
        'icon-alt': 'keyboard_arrow_down',
        text: 'Labels',
        model: true,
        children: [
          { icon: 'add', text: 'Create label' },
        ],
      },
      {
        icon: 'keyboard_arrow_up',
        'icon-alt': 'keyboard_arrow_down',
        text: 'More',
        model: false,
        children: [
          { text: 'Import' },
          { text: 'Export' },
          { text: 'Print' },
          { text: 'Undo changes' },
          { text: 'Other contacts' },
        ],
      },
      { icon: 'settings', text: 'Settings' },
      { icon: 'chat_bubble', text: 'Send feedback' },
      { icon: 'help', text: 'Help' },
      { icon: 'phonelink', text: 'App downloads' },
      { icon: 'keyboard', text: 'Go to the old version' },
    ],
    }),
  }
</script>