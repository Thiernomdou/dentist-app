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
                      placeholder="Recherchez vos symptômes" 
                      flat 
                      success>
                    </v-text-field>
                    <v-spacer></v-spacer>
                    <v-chip class="ma-2" color="white">
                      <v-icon left color="teal">mdi-clock-time-nine</v-icon>
                      Avril 2020 14:02, Aujourd'hui 
                    </v-chip>
                  </v-app-bar>
                </v-col>
                <v-col cols="12" sm="12">
                  <v-card class="mx-12 rounded-tl-xl rounded-tr-xl rounded-bl-xl rounded-br-xl mt-m15">
                    <v-list-item three-line>
                      <v-list-item-content class="pa-10">
                        <v-list-item-title class="headline mb-1">
                          <p>  aujourd'hui <span class="teal--text">-10%</span> de réduction <br>
                          sur les examens pulmonaires </p>
                        </v-list-item-title>
                        <v-list-item-subtitle>
                          <p> Le prix du forfait comprend: la consulation <br>
                          d'un pneumologue, spirographie, cardiogramme <span class="teal--text"></span> </p>
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
                      <h5>Statistiques santé</h5>
                      <v-spacer></v-spacer>
                        <v-btn color="teal" text>
                          2020
                          <v-icon right>mdi-chevron-down</v-icon>
                        </v-btn>
                        <v-btn color="teal" rounded dark depressed>Année</v-btn>
                        <v-btn text>Mois</v-btn>
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
                          Rythme cardiaque <br>
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
                  <v-card class="mx-12 rounded-tl-xl rounded-tr-xl rounded-bl-xl rounded-br-xl mt-m12">
                    <v-app-bar color="rgba(0,0,0,0)" class="ma-8" flat>
                      <h5>Votre activité</h5>
                      <v-spacer></v-spacer>
                      <v-btn color="teal" rounded dark depressed>Semaine</v-btn>
                      <v-btn text>Mois</v-btn>
                    </v-app-bar>
                    <v-progress-circular rotate="360" size="100" width="15" value="50" color="teal" class="mt-m5 ml-5 mb-2">
                      50
                    </v-progress-circular>
                    <v-progress-circular rotate="360" size="100" width="15" value="70" color="red" class="mt-m5 ml-5 mb-2">
                      70
                    </v-progress-circular>
                    <v-progress-circular rotate="360" size="100" width="15" value="80" color="blue" class="mt-m5 ml-5 mb-2">
                      80
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
              <v-row>
                <v-col cols="12" sm="12">
                  <v-list two-line>
                    <v-list-item>
                      <v-list-item-avatar>
                        <img src="https://cdn.vuetifyjs.com/images/lists/3.jpg" alt="profil">
                      </v-list-item-avatar>
                      <v-list-item-content>
                        <v-list-item-title>Chloé Garcia</v-list-item-title>
                        <v-list-item-subtitle class="teal--text">15 ans, Lyon</v-list-item-subtitle>
                      </v-list-item-content>
                      <v-spacer></v-spacer>
                      <v-icon color="teal">mdi-menu</v-icon>
                    </v-list-item>
                  </v-list>
                </v-col>
                <v-col cols="12" md="4">
                  <v-row>
                    <v-col cols="12" md="2">
                      <v-card height="50px" width="10px" color="green"></v-card>
                    </v-col>
                    <v-col cols="12" md="10">
                      <v-list two-line subheader class="ml-m8">
                        <v-list-item>
                          <v-list-item-content>
                            <v-list-item-subtitle>Sang</v-list-item-subtitle>
                            <v-list-item-title>A+</v-list-item-title>
                          </v-list-item-content>
                        </v-list-item>
                      </v-list>
                    </v-col>
                  </v-row>
                </v-col>
                <v-col cols="12" md="4">
                  <v-row>
                    <v-col cols="12" md="2">
                      <v-card height="50px" width="10px" color="red"></v-card>
                    </v-col>
                    <v-col cols="12" md="10">
                      <v-list two-line subheader class="ml-m8">
                        <v-list-item>
                          <v-list-item-content>
                            <v-list-item-subtitle>Taille</v-list-item-subtitle>
                            <v-list-item-title>1.75cm</v-list-item-title>
                          </v-list-item-content>
                        </v-list-item>
                      </v-list>
                    </v-col>
                  </v-row>
                </v-col>
                <v-col cols="12" md="4">
                  <v-row>
                    <v-col cols="12" md="2">
                      <v-card height="50px" width="10px" color="grey"></v-card>
                    </v-col>
                    <v-col cols="12" md="10">
                      <v-list two-line subheader class="ml-m8">
                        <v-list-item>
                          <v-list-item-content>
                            <v-list-item-subtitle>Poids</v-list-item-subtitle>
                            <v-list-item-title>64kg</v-list-item-title>
                          </v-list-item-content>
                        </v-list-item>
                      </v-list>
                    </v-col>
                  </v-row>
                </v-col>
                <v-col cols="12" sm="12">
                  <v-btn text>Novembre</v-btn>
                  <v-icon right>mdi-chevron-down</v-icon>
                </v-col>
                <v-col cols="12" sm="12">
                  <v-list-item>
                    <v-list-item-content>
                      <v-btn class="mr-1" outlined color="teal darken-1">LU</v-btn>
                    </v-list-item-content>
                    <v-list-item-content>
                      <v-btn class="mr-1" outlined color="teal darken-1">MA</v-btn>
                    </v-list-item-content>
                    <v-list-item-content>
                      <v-btn class="mr-1" outlined color="teal darken-1">ME</v-btn>
                    </v-list-item-content>
                    <v-list-item-content>
                      <v-btn class="mr-1"  color="teal darken-1" dark>JE</v-btn>
                    </v-list-item-content>
                    <v-list-item-content>
                      <v-btn class="mr-1" outlined color="teal darken-1">VE</v-btn>
                    </v-list-item-content>
                    <v-list-item-content>
                      <v-btn class="mr-1" outlined color="teal darken-1">SA</v-btn>
                    </v-list-item-content>
                  </v-list-item>
                </v-col>
                <v-col cols="12" sm="12">
                  <v-card class="mx-12 rounded-tl-xl rounded-tr-xl rounded-bl-xl rounded-br-xl mt-m4 py-4" color="teal" dark flat>
                    <v-list-item three-line>
                      <v-list-item-avatar tile size="30">
                        <v-icon size="30">mdi-tooth</v-icon>
                      </v-list-item-avatar>
                      <v-list-item-content class="pa-2">
                        <v-list-item-title class="headline mb-1">
                          Dentiste <br>
                          <h6>8: 00 - 9: 30</h6>
                          <h6>Dr. Alexandre Brown(cab 39)</h6>
                        </v-list-item-title>
                      </v-list-item-content>
                    </v-list-item>
                  </v-card>
                </v-col>
                <v-col cols="12" sm="12">
                  <v-card class="mx-12 rounded-tl-xl rounded-tr-xl rounded-bl-xl rounded-br-xl mt-m4 py-4" color="teal lighten-5" flat>
                    <v-list-item three-line>
                      <v-list-item-avatar size="30" tile>
                        <v-icon size="30">fas fa-heartbeat</v-icon>
                      </v-list-item-avatar>
                      <v-list-item-content class="pa-2">
                        <v-list-item-title class="headline mb-1">
                          Medecin généraliste <br>
                          <h6>9: 45 - 11:45</h6>
                          <h6>Dr. Pascal Grangier(cab 61)</h6>
                        </v-list-item-title>
                      </v-list-item-content>
                    </v-list-item>
                  </v-card>
                </v-col>
                <v-col cols="12" sm="12">
                  <v-btn text>Votre traitement
                    <v-icon right>mdi-chevron-down</v-icon>
                  </v-btn>
                </v-col>
                <v-col cols="12" sm="12">
                  <v-card class="mx-12 rounded-tl-xl rounded-tr-xl rounded-bl-xl rounded-br-xl mt-m4" color="teal lighten-5" flat>
                    <v-list-item three-line>
                      <v-list-avatar size="30" tile>
                        <v-icon size="30" color="teal">mdi-pill</v-icon>
                      </v-list-avatar>
                      <v-list-item-content class="pa-2">
                        <v-list-item-title class="headline mb-1">
                          Gentle iron <br>
                          <h6><span class="teal--text">2 capsules</span> avec mais tous les jours</h6>
                        </v-list-item-title>
                      </v-list-item-content>
                    </v-list-item>
                  </v-card>
                </v-col>
              </v-row>
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
