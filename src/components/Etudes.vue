<template>
    <div class="etudes">
      <h2><i class="fas fa-user-graduate"></i> Études</h2>
      <div v-for="(item, index) in etudes" :key="item.intitule" :class="'etudes__' + (index+1)">
          <p class="etudes__date">{{ item.fin }}<br>{{ item.debut }}</p>
          <div class='etudes__card'>
            <h3>{{ item.intitule }}</h3>
            <p><a :href="item.lienEtablissement" target="_blank">{{ item.etablissement }}</a><span v-if="item.ville"> à <a :href="item.lienGMaps" target="_blank">{{ item.ville }}  <i class="fas fa-map-marker-alt"></i></a></span></p>
            <p>{{ item.description }}</p>
          </div>
          
      </div>
    </div>
</template>

<script>
export default {
  name: 'Etudes',
  data() {
      return {
          etudes: [
              {
                  intitule: "Formation Développeur Web (RNCP niveau 5 BAC+2)",
                  etablissement: "OpenClassroom",
                  lienEtablissement: "https://openclassrooms.com/fr/",
                  debut: "2020",
                  fin:  "2021",
                  description: "" 
              },
              {
                  intitule: "DUT Gestion Administrative et Commerciale des organisations",
                  etablissement: "IUT Belfort-Montbeliard",
                  lienEtablissement: "http://www.iut-bm.univ-fcomte.fr/",
                  ville: "Montbeliard",
                  lienGMaps: "https://www.google.fr/maps/place/D%C3%A9partement+GACO/@47.4942242,6.8012278,17z/data=!3m1!4b1!4m5!3m4!1s0x4792172790ff29b7:0x3ed4a40fc7173593!8m2!3d47.4942211!4d6.8031244",
                  debut: "2016",
                  fin:  "2018",
                  description: "Études commerciales (Management, Marketing,...), financières (Comptabilité, analyse financière, controle de gestion,...) et administratives (Gestion des ressources humaines,...)" 
              },
              {
                  intitule: "Baccalauréat Economique et Social",
                  etablissement: "Lycée Jean-Jacques Henner",
                  lienEtablissement: "https://lycee-jjhenner.fr/",
                  ville: "Altkirch",
                  lienGMaps: "https://www.google.com/maps/place/Lyc%C3%A9e+Jean+Jacques+HENNER/@47.6115658,7.2313051,15z/data=!4m2!3m1!1s0x0:0x53dfc0ee81d4ed0f?sa=X&ved=2ahUKEwiL4qnS_JbxAhWvDGMBHSUEBkcQ_BIwHHoECEMQBQ",
                  debut: "2013",
                  fin:  "2016",
                  description: "" 
              },
          ]
      };
  },
}
</script>
