<template>
  <div>
    <v-app :style="{background: $vuetify.theme.themes.light.background}">
      <v-layout row>
        <v-flex md8>
          <v-app :style="{background: $vuetify.theme.themes.dark.background}" class="rounded-tr-xl rounded-br-xl">
            <v-container>
              <v-row>
                <v-col cols="12" sm="12">
                  <v-app-bar color="rgba(0,0,0,0)" class="mx-8 mb-8 mt-3" flat>
                    <v-text-field 
                      prepend-icon="mdi-magnify" 
                      color="teal" 
                      placeholder="Search your symptons" 
                      flat 
                      success>
                    </v-text-field>
                    <v-spacer></v-spacer>
                    <v-chip class="ma-2" color="white">
                      <v-icon left color="teal">mdi-clock-time-nine</v-icon>
                      14:02 AM Today April, 2020
                    </v-chip>
                  </v-app-bar>
                </v-col>
                <v-col cols="12" sm="12">
                  <v-card class="mx-12 rounded-tl-xl rounded-tr-xl rounded-bl-xl rounded-br-xl mt-m15">
                    <v-list-item three-line>
                      <v-list-item-content class="pa-10">
                        <v-list-item-title class="headline mb-1">
                          <p> today <span class="teal--text">10%</span> discount <br>
                          on lung examinations </p>
                        </v-list-item-title>
                        <v-list-item-subtitle>
                          <p> The package price icludes: consulation <br>
                          of a pulmonologist, spirography, cardiogram <span class="teal--text"></span> </p>
                        </v-list-item-subtitle>
                      </v-list-item-content>
                      <v-list-item-avatar size="150" class="pr-10" tile>
                        <img src="../assets/img/lungs.png" alt="examination image">
                      </v-list-item-avatar>
                    </v-list-item>
                  </v-card>
                </v-col>
                <v-col cols="12" sm="12">
                  <v-card class="mx-12 rounded-tl-xl rounded-tr-xl rounded-bl-xl rounded-br-xl mt-m15">
                    <v-app-bar color="rgba(0,0,0,0)" class="ma-8" flat>
                      <h5>Statistics of your healyh</h5>
                      <v-spacer></v-spacer>
                        <v-btn color="teal" text>
                          2020
                          <v-icon right>mdi-chevron-down</v-icon>
                        </v-btn>
                        <v-btn color="teal" rounded dark depressed>Year</v-btn>
                        <v-btn text>Mounth</v-btn>
                    </v-app-bar>
                    <template>
                      <v-sparkline
                        :value="value"
                        color="teal"
                        :smooth="radius || false"
                        :padding="padding"
                        :line-width="width"
                        :stroke-lineCap="lineCap"
                        :fill="fill"
                        :type="type"
                        :auto-line-width="autoLineWidth"
                        auto-draw
                      >
                      </v-sparkline>
                    </template>
                  </v-card>
                </v-col>
                <v-col cols="12" sm="6">
                  <v-card class="mx-12 rounded-tl-xl rounded-tr-xl rounded-bl-xl rounded-br-xl mt-m4" color="teal" dark>
                    <v-list-item three-line>
                      <v-list-item-content class="pa-2">
                        <v-list-item-title class="headline mb-1">
                          Heart rate <br>
                          <h2>112 bpm</h2>
                        </v-list-item-title>
                      </v-list-item-content>
                      <v-list-avatar size="150" class="pr-10" tile>
                        <v-icon size="100">fas fa-heartbeat</v-icon>
                      </v-list-avatar>
                    </v-list-item>
                  </v-card>
                </v-col>
                <v-col cols="12" sm="6">
                  <v-card class="mx-12 rounded-tl-xl rounded-tr-xl rounded-bl-xl rounded-br-xl mt-m12" color="teal" dark>
                    <v-app-bar color="rgba(0,0,0,0)" class="ma-8" flat>
                      <h5>Your activity</h5>
                      <v-spacer></v-spacer>
                      <v-btn color="teal" rounded dark depressed>Week</v-btn>
                      <v-btn text>Mounth</v-btn>
                    </v-app-bar>
                    <v-progress-circular rotate="360" size="100" width="15" value="50" color="teal" class="mt-5 ml-5 mb-2">
                      50
                    </v-progress-circular>
                  </v-card>
                </v-col>
              </v-row>
            </v-container>
          </v-app>
        </v-flex>
        <v-flex md4>
          <v-app :style="{background: $vuetify.theme.themes.light.background}">
            <v-container>

            </v-container>
          </v-app>
        </v-flex>
      </v-layout>
    </v-app>
  </div>
</template>

<script>
 

  export default {
    name: 'Home',
    data() {
      return {
        width: 2,
        radius: 10,
        padding: 8,
        lineCap: 'round',
        value: [0,2,5,9,5,10,3,5,0,0,1,8,2,9,0],
        fill: false,
        type: 'trend',
        autoLineWidth: false
      }
    },
    computed: {
      theme() {
        return this.$vuetify.theme.dark ? "dark" : "light";
      }
    },
    components: {
    },
  }
</script>
