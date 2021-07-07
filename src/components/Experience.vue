<template>
    <div id="xp">
      <h2><i class="fas fa-hammer"></i> Expérience professionnelle</h2>
      <div class="exp">
        <div v-for="(item, index) in expPro" :key="item.emploi" :class="'exp__' + (index + 1) + ' reveal-' + (index + 1)">
            <p class="exp__date">{{ item.periode }}</p>
            <div class="exp__card">
                <h3 class="exp__emploi">{{ item.emploi }}</h3>
                <p class="exp__entreprise"><a :href="item.lienEntreprise" target="_blank">{{ item.entreprise }}</a> à <a :href="item.lienGMaps" target="_blank">{{ item.ville }} <i class="fas fa-map-marker-alt"></i></a></p>
                <h4>Tâches</h4>
                <ul>
                    <li v-for="tache in item.tache" :key="tache">{{ tache }}</li>
                </ul>
            </div>
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
                  emploi: "Apprenti Vendeur",
                  entreprise: "Super U",
                  lienEntreprise: "https://www.magasins-u.com/magasin/superu-valdoie",
                  ville: "Valdoie",
                  lienGMaps: "https://www.google.fr/maps/place/Super+U+et+Drive/@47.6685574,6.8412068,17z/data=!3m1!4b1!4m5!3m4!1s0x47923ba875e2cacb:0xa0ac95f54aa75d1f!8m2!3d47.6686669!4d6.8430615",
                  periode: "Septembre 2016 - Août 2018",
                  tache: [
                      "Manager une équipe de 2 personnes",
                      "Gérer des stocks",
                      "Optimiser le CA en quantité et en qualité"
                  ]
              },
              {
                  emploi: "Assistant de gestion logistique",
                  entreprise: "Sharp Manufacturing France",
                  lienEntreprise: "https://www.sharp.fr/fr",
                  ville: "Soultz",
                  lienGMaps: "https://www.google.fr/maps/place/Sharp+Manufacturing+France/@47.8757444,7.2419335,17z/data=!3m1!4b1!4m5!3m4!1s0x479178ceeec02303:0xed3809e79b7bbbc2!8m2!3d47.8757408!4d7.2441222",
                  periode: "Décembre  2018",
                  tache: [
                      "Gérer des réceptions, de la démarque et de la production dans SAP"
                  ]
              },
              {
                  emploi: "Assistant chef de projet",
                  entreprise: "Sharp Manufacturing France",
                  lienEntreprise: "https://www.sharp.fr/fr",
                  ville: "Soultz",
                  lienGMaps: "https://www.google.fr/maps/place/Sharp+Manufacturing+France/@47.8757444,7.2419335,17z/data=!3m1!4b1!4m5!3m4!1s0x479178ceeec02303:0xed3809e79b7bbbc2!8m2!3d47.8757408!4d7.2441222",
                  periode: "Janvier 2019 - Avril 2020",
                  tache: [
                      "Suivre des projets (lancement des  nouveaux produits)",
                      "Gérer des fiches produits dans le logiciel SAP",
                      "Utiliser VBA avec Excel",
                      "Créer des documents avec Illustrator",
                      "Télétravail"
                  ]
              },
          ]
      };

  },
}
</script>
