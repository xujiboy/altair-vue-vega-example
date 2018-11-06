
<template>
<v-app>
  <v-content>
  <v-container fluid grid-list-lg>
      <v-layout row>
        <v-layout col wrap fill-height>
          <v-flex d-flex>
          <!-- <div> -->
            <v-card>
              <!-- <v-responsive :aspect-ratio="16/9"> -->
              <v-card-text>1</v-card-text>
              <div id="vega-box"></div>
              <v-btn @click.native="reloadImage()">Reload</v-btn>
              <!-- </v-responsive> -->
            </v-card>
          <!-- </div> -->
          </v-flex>

          <v-flex d-flex>
          <!-- <div> -->
            <v-card>
              <v-card-text>2</v-card-text>
              <div id="vega-box2"></div>
              <v-btn @click.native="reloadImage2()">Reload</v-btn>
            </v-card>
          <!-- </div> -->
          </v-flex>
        </v-layout>

        <v-flex d-flex>
          <v-card>
            <v-card-text>3</v-card-text>
            
          </v-card>

        </v-flex>
      </v-layout>
    
  </v-container>
  </v-content>
</v-app>
</template>




<script>
import {default as vegaEmbed} from 'vega-embed'

export default {
  methods: {
    reloadImage () {
      fetch('/vega-example').then(response => {
        response.json().then(spec => {
          vegaEmbed('#vega-box', spec, {actions: false})
        })
      })
    },
    reloadImage2 () {
      fetch('/vega-example').then(response => {
        response.json().then(spec => {
          vegaEmbed('#vega-box2', spec, {actions: false})
        })
      })
    }
  }
}
</script>



<!-- Add "scoped" attribute to limit CSS to this component only -->
<style>

</style>
