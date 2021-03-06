<template>
    <div>
        <div class="formation">
            <h2><i class="fas fa-code"></i> Formation Developpeur Web</h2>
            <div class="formation__part">
                <h3>Etablissement</h3>
                <p>OpenClassrooms est un établissement privé d'enseignement à distance déclaré au rectorat de l'Académie de Paris.</p>
            </div>
            <div class="formation__part">
                <h3>Compétences acquises</h3>
                <ul>
                    <li>découper, assembler et intégrer tous les éléments d’une maquette graphique en HTML5 et CSS ;</li>
                    <li>ajouter du contenu audio et vidéo en HTML5 ;</li>
                    <li>animer les pages web avec CSS3 ;</li>
                    <li>appliquer les standards du web et les normes en vigueur ;</li>
                    <li>construire un site web fluide s’adaptant à tout type d’écran (web, smartphone et tablette) ;</li>
                    <li>améliorer le référencement naturel en utilisant les balises selon leur sémantique ;</li>
                    <li>faire réagir la page web en fonction des actions de l’utilisateur en JavaScript ;</li>
                    <li>se connecter à un service web pour exploiter des données tierces (API) ;</li>
                    <li>gérer les comptes utilisateurs ;</li>
                    <li>concevoir un site maintenable grâce à la gestion des erreurs et exceptions ;</li>
                    <li>créer, gérer et afficher le contenu d’une base de données.</li>
                </ul>
            </div>
            <div class="formation__part formation__deroulement">
                <h3>Déroulement de la formation</h3>
                <p>La formation est composée de 7 projets a validé par des livrables puis un oral. Chaque projet doit etre validé pour passer au suivant.</p>
                <div class="formation__projets">
                    <h4>Projets :</h4>
                    <carousel>
                        <carousel-slide v-for="(projet, index) in projets" :key="index" class="formation__carousel">
                            <h5>Projet {{ index + 1 }} : {{  projet.nom }}</h5>
                            <p class="formation__projDescription">{{ projet.description }}</p>
                            <h6>Cours :</h6>
                            <ul>
                                <li v-for="cours in projet.cours" :key="cours.nomCours"><a :href="cours.lien" target="_blank">{{ cours.nomCours }}</a></li>
                            </ul> 
                            <div v-if="projet.livrables">
                                <h6>Livrables</h6>
                                <ul>
                                    <li v-if="projet.livrables.page"><a :href="projet.livrables.page">Page Web héberger sur GitHub</a></li>
                                    <li v-if="projet.livrables.lienGitHub"><a :href="projet.livrables.lienGitHub">Code enregistrer sur GitHub</a></li>
                                    <li v-if="projet.livrables.dossier"><a :href="projet.livrables.dossier">Dossier</a></li>
                                    <li v-if="projet.livrables.frontend"><a :href="projet.livrables.frontend">Frontend du projet</a></li>
                                </ul>
                            </div>
                        </carousel-slide>
                    </carousel>
                </div>
                <div class="formation__part formation__other">
                    <h3>Autres formations</h3>
                    <ul>
                        <li><a href="https://www.pierre-giraud.com/html-css-apprendre-coder-cours/" target="_blank">Cours sur HTML et CSS de Pierre Giraud (Janvier 2020)</a></li>
                        <li><a href="https://www.pierre-giraud.com/javascript-apprendre-coder-cours/" target="_blank">Cours sur JavaScript de Pierre Giraud (Mars 2020)</a></li>
                        <li><a href="https://www.udemy.com/course/flutter-bloc/" target="_blank">Cours "Flutter et l'architecture BLoC" sur le site Udemy (Juillet 2021)</a></li>
                        <li><a href="https://www.udemy.com/course/flutter_animations/" target="_blank">Cours "Les animations avec Flutter et Dart" sur le site Udemy (En cours)</a></li>
                        <li><a href="https://www.udemy.com/course/flutter-cloud-firestore/" target="_blank">Cours "Flutter 2 et Cloud Firestore:Créez votre réseau social" sur le site Udemy (En cours)</a></li>
                    </ul>
                </div>
            </div>
        </div>
        <div class="formationPrint">
            <h3>Projets professionnels en Développement Web (Octobre 2020 - Juin 2021)</h3>
            <p>Dans le cadre de la formation avec OpenClassrooms, j'ai réalisé 7 projets professionnels.</p>
            <div class="formationPrint__reverse">
                <div v-for="(projet, index) in projets" :key="index" :class="'formationPrint__card formationPrint__' + (index+1)">
                    <h4>Projet {{ index + 1 }} : {{  projet.nom }}</h4>
                    <p>{{ projet.description }}</p>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
import Carousel from "./carousel/Carousel"
import CarouselSlide from "./carousel/CarouselSlide"

export default {
  name: 'Formation',
  data() {
      return {
          projets: [
              {
                  nom: "Prenez en main votre formation de développeur web",
                  description:"Introduction au monde du web et mise en place des meilleures conditions pour apprendre activement et de manière autonome.",
                  cours: [
                      {nomCours: "Apprenez à apprendre", lien:"https://openclassrooms.com/fr/courses/4312781-apprenez-a-apprendre"},
                      {nomCours: "Comprendre le web", lien:"https://openclassrooms.com/fr/courses/1946386-comprendre-le-web"},
                      {nomCours: "Découvrez les métiers de développeur", lien:"https://openclassrooms.com/fr/courses/6817086-decouvrez-les-metiers-de-developpeur"},
                      {nomCours: "Mettre en place une vieille informationnelle", lien:"https://openclassrooms.com/fr/courses/4805776-mettez-en-place-un-systeme-de-veille-informationnelle"}
                  ]
              },
              {
                  nom: "Transformez une maquette en site web",
                  description:"Créer le frontend d'une plateforme de réservation de vacances avec CSS et HTML pour le développement et Git et GitHub pour la gestion des versions.",
                  cours: [
                      {nomCours: "Apprenez à utiliser la ligne de commande dans un terminal", lien:"https://openclassrooms.com/fr/courses/6173491-apprenez-a-utiliser-la-ligne-de-commande-dans-un-terminal"},
                      {nomCours: "Gérez du code avec Git et GitHub", lien:"https://openclassrooms.com/fr/courses/7162856-gerez-du-code-avec-git-et-github"},
                      {nomCours: "Apprenez à créer votre site webavec HTML5 et CSS3", lien:"https://openclassrooms.com/fr/courses/1603881-apprenez-a-creer-votre-site-web-avec-html5-et-css3"},
                      {nomCours: "Découpez et intégrez une maquette", lien:"https://openclassrooms.com/fr/courses/3504431-decoupez-et-integrez-une-maquette"}
                  ],
                  livrables: {
                      page: "https://evan267.github.io/EvanBerger_2_20112020/",
                      lienGitHub: "https://github.com/Evan267/EvanBerger_2_20112020"
                  }
              },
              {
                  nom: "Dynamisez une page web avec des animations CSS",
                  description:"Créer le frontend d'un site de foodtech responsive avec des animations en CSS en utilisant Sass.",
                  cours: [
                      {nomCours: "Simplifiez-vous le CSS avec Sass", lien:"https://openclassrooms.com/fr/courses/6106181-simplifiez-vous-le-css-avec-sass"},
                      {nomCours: "Créez des animations CSS modernes", lien:"https://openclassrooms.com/fr/courses/5919246-creez-des-animations-css-modernes"}
                  ],
                  livrables: {
                      page: "https://evan267.github.io/EvanBerger_3_24122020/",
                      lienGitHub: "https://github.com/Evan267/EvanBerger_3_24122020"
                  }
              },
              {
                  nom: "Optimisez un site web existant",
                  description:"Analyser et optimiser le SEO et l'accessibilité d'un site Web déjà existant.",
                  cours: [
                      {nomCours: "Optimisez le référencement de votre site (SEO) en améliorant ses preformances techniques", lien:"https://openclassrooms.com/fr/courses/5922626-optimisez-le-referencement-de-votre-site-seo-en-ameliorant-ses-performances-techniques"},
                      {nomCours: "Augmentez votre trafic grâce au référencement naturel (SEO)", lien:"https://openclassrooms.com/fr/courses/5561431-augmentez-votre-trafic-grace-au-referencement-naturel-seo"},
                      {nomCours: "Concevez un contenu web accessible", lien:"https://openclassrooms.com/fr/courses/6691346-concevez-un-contenu-web-accessible"},
                  ],
                  livrables: {
                      dossier: "./assets/P4_Berger_Evan.zip",
                  }
              },
              {
                  nom: "Construisez un site e-commerce",
                  description:"Créer le frontend d'un site e-commerce en utilisant JavaScript et Bootstrap avec notamment la possibilité de gérer son panier et de passer commande.",
                  cours: [
                      {nomCours: "Apprenez à programmer avec JavaScript", lien:"https://openclassrooms.com/fr/courses/6175841-apprenez-a-programmer-avec-javascript"},
                      {nomCours: "Écrivez du JavaScript pour le web", lien:"https://openclassrooms.com/fr/courses/5543061-ecrivez-du-javascript-pour-le-web"},
                      {nomCours: "Créez des sites web responsive avec Bootstrap 4", lien:"https://openclassrooms.com/fr/courses/6391096-creez-des-sites-web-responsive-avec-bootstrap-4"},
                  ],
                  livrables: {
                      lienGitHub: "https://github.com/Evan267/EvanBerger_5_01032021",
                      dossier: "./assets/P5_Berger_Evan.zip",
                  }
              },
              {
                  nom: "Construisez une API sécurisée pour une application d'avis gastronomiques",
                  description:"Créer le backend(API REST) d'une application d'avis gastronomiques en utilisant les technologies OWASP, Node.js, MongoDB et Express.",
                  cours: [
                      {nomCours: "Passez au Full stack vec Node.js, Express et MongoDB", lien:"https://openclassrooms.com/fr/courses/6390246-passez-au-full-stack-avec-node-js-express-et-mongodb"},
                      {nomCours: "Sécurisez vos applications web avec l'OWASP", lien:"https://openclassrooms.com/fr/courses/6179306-securisez-vos-applications-web-avec-lowasp"},
                      {nomCours: "Adoptez les API REST pour vos projets web", lien:"https://openclassrooms.com/fr/courses/6573181-adoptez-les-api-rest-pour-vos-projets-web"},
                  ],
                  livrables: {
                      lienGitHub: "https://github.com/Evan267/EvanBerger_6_060421",
                      frontend: "https://github.com/OpenClassrooms-Student-Center/dwj-projet6",
                  }
              },
              {
                  nom: "Créez un réseau social d'entreprise",
                  description:"Créer un réseau social d'une entreprise et manipulation des bases de données SQL en utilisant de Vue.js pour le frontend et de Node.js et Sequelize en backend. ",
                  cours: [
                      {nomCours: "Administrez vos bases de données avec MySQL", lien:"https://openclassrooms.com/fr/courses/1959476-administrez-vos-bases-de-donnees-avec-mysql"},
                      {nomCours: "Créez une application web avec Vue.js", lien:"https://openclassrooms.com/fr/courses/6390311-creez-une-application-web-avec-vue-js"}
                  ],
                  livrables: {
                      lienGitHub: "https://github.com/Evan267/EvanBerger_7_07052021",
                  }
              },
          ]
      }
  },
  components: {
      Carousel,
      CarouselSlide
  },
}
</script>
