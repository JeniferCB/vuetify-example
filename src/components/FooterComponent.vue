<template>
    <v-footer
    v-bind="localAttrs"
    :padless="padless"
  >
    <v-card
      flat
      tile
      width="100%"
      class="green lighten-1 text-center"
    >
      <v-card-text>
        <v-btn
          v-for="(icon, idx) in icons"
          :key="idx"
          class="mx-4"
          icon
        >
        <router-link :to="{name: links[idx]}" >
          <v-icon size="24px">
            {{ icon }}
          </v-icon>
        </router-link>
        </v-btn>
      </v-card-text>

      <v-divider></v-divider>

      <v-card-text class="white--text">
        {{ new Date().getFullYear() }} — <strong>FULP</strong>
      </v-card-text>
    </v-card>
  </v-footer>
</template>

<script>
export default {
  name: 'FooterBar',
  data () {
    return {
      icons: [
        'mdi-home',
        'mdi-email',
        'mdi-calendar',
        'mdi-account-cowboy-hat'
      ],
      links: [
        'home',
        'mail',
        'calendar',
        'cowboy'
      ]
    }
  }
}
</script>

<style scoped>

</style>
