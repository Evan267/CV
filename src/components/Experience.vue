<template>
    <div id="xp" :class="visible">
      <h2>Experience professionelle</h2>
      <div class="exp">
        <div v-for="(item, index) in expPro" :key="item.emploi" :class="'exp__' + (index + 1) + ' reveal-' + (index + 1)">
            <h3 class="exp__emploi">{{ item.emploi }}</h3>
            <p class="exp__entreprise"><a :href="item.lienEntreprise" target="_blank">{{ item.entreprise }}</a> à <a :href="item.lienGMaps" target="_blank">{{ item.ville }}</a></p>
            <p class="exp__date">{{ item.periode }}</p>
            <h4>Tâches</h4>
            <ul>
                <li v-for="item in item.tache" :key="item">{{ item }}</li>
            </ul>
        </div>
      </div>
    </div>
</template>

<script>
export default {
  name: 'Experience',
  data() {
      return {
          expPro: [
              {
                  emploi: "Assistant chef de projet",
                  entreprise: "Sharp Manufacturing France",
                  lienEntreprise: "https://www.sharp.fr/fr",
                  ville: "Soultz",
                  lienGMaps: "https://www.google.fr/maps/place/Sharp+Manufacturing+France/@47.8757444,7.2419335,17z/data=!3m1!4b1!4m5!3m4!1s0x479178ceeec02303:0xed3809e79b7bbbc2!8m2!3d47.8757408!4d7.2441222",
                  periode: "Janvier 2019 - Avril 2020",
                  tache: [
                      "Suivi des projets (lancement des  nouveaux produits)",
                      "Gestion des fiches produits dans le logiciel SAP",
                      "Utilisation de VBA avec Excel"
                  ]
              },
              {
                  emploi: "Assistant de gestion logistique",
                  entreprise: "Sharp Manufacturing France",
                  lienEntreprise: "https://www.sharp.fr/fr",
                  ville: "Soultz",
                  lienGMaps: "https://www.google.fr/maps/place/Sharp+Manufacturing+France/@47.8757444,7.2419335,17z/data=!3m1!4b1!4m5!3m4!1s0x479178ceeec02303:0xed3809e79b7bbbc2!8m2!3d47.8757408!4d7.2441222",
                  periode: "Decembre  2018",
                  tache: [
                      "Gestion des réceptions, de la démarque et de la production dans SAP"
                  ]
              },
              {
                  emploi: "Apprenti Vendeur",
                  entreprise: "Super U",
                  lienEntreprise: "https://www.magasins-u.com/magasin/superu-valdoie",
                  ville: "Valdoie",
                  lienGMaps: "https://www.google.fr/maps/place/Super+U+et+Drive/@47.6685574,6.8412068,17z/data=!3m1!4b1!4m5!3m4!1s0x47923ba875e2cacb:0xa0ac95f54aa75d1f!8m2!3d47.6686669!4d6.8430615",
                  periode: "Septembre 2016 - Août 2018",
                  tache: [
                      "Management d'une petit équipe de 2 personnes",
                      "Gestion des stocks",
                      "Optimisation du CA en quantité et en qualité"
                  ]
              },
          ]
      };

  },
  props: {
      visible: String
  }
}
</script>
