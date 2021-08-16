<template>
    <div class="competence">
      <h2>Compétences</h2>
      <div class="competence__dev">
          <div v-for="(competence, index) in competences" :key="competence.titre" :class="'competence__part competence__' + (index  + 1)">
            <h3>{{ competence.titre }}</h3>
            <div class="competence__list">
                <div v-for="item in competence.tableau" :key="item.nom">
                    <p>{{ item.nom }}</p>
                    <div v-if="item.maitrise == 1" class="competence__note">
                        <div class="circle circle__full"></div>
                        <div class="circle"></div>
                        <div class="circle"></div>
                        <div class="circle"></div>
                        <div class="circle"></div>
                    </div>
                    <div v-else-if="item.maitrise == 2" class="competence__note">
                        <div class="circle circle__full"></div>
                        <div class="circle circle__full"></div>
                        <div class="circle"></div>
                        <div class="circle"></div>
                        <div class="circle"></div>
                    </div>
                    <div v-else-if="item.maitrise == 3" class="competence__note">
                        <div class="circle circle__full"></div>
                        <div class="circle circle__full"></div>
                        <div class="circle circle__full"></div>
                        <div class="circle"></div>
                        <div class="circle"></div>
                    </div>
                    <div v-else-if="item.maitrise == 4" class="competence__note">
                        <div class="circle circle__full"></div>
                        <div class="circle circle__full"></div>
                        <div class="circle circle__full"></div>
                        <div class="circle circle__full"></div>
                        <div class="circle"></div>
                    </div>
                    <div v-else-if="item.maitrise == 5" class="competence__note">
                        <div class="circle circle__full"></div>
                        <div class="circle circle__full"></div>
                        <div class="circle circle__full"></div>
                        <div class="circle circle__full"></div>
                        <div class="circle circle__full"></div>
                    </div>
                </div>
            </div>
        </div>
      </div>
      <div class="competence__soft">
          <h3>Soft Skills</h3>
          <div v-for="(softSkill, index) in softSkills" :key="softSkill.nom" :class="'competence__softSkills competence__softSkills' + (index + 1)">
              <i :class="softSkill.icon"></i>
              <p>{{ softSkill.nom }}</p>
          </div>
      </div>
    </div>
</template>

<script>
export default {
  name: 'Logiciel',
  data () {
      return{
          softSkills: [
              {
                  nom: "Esprit d'équipe",
                  icon: "fas fa-users"
              },
              {
                  nom: "Rigueur",
                  icon: "fas fa-hourglass-half"
              },
              {
                  nom: "Ponctualité",
                  icon: "far fa-clock"
              },
              {
                  nom: "Autonome",
                  icon: "fas fa-user"
              },
              {
                  nom: "Adaptabilité",
                  icon: "fas fa-tools"
              },
          ],
          competences: [
              {
                  titre: 'Langages',
                  tableau:[
                    {
                        nom: 'HTML5',
                        maitrise: 4
                    },
                    {
                        nom: 'CSS3',
                        maitrise: 4
                    },
                    {
                        nom: 'JavaScript',
                        maitrise: 3
                    },
                    {
                        nom: 'Dart',
                        maitrise: 2
                    },
                    {
                        nom: 'VBA',
                        maitrise: 2
                    },
                  ],
              },
              {
                  titre:  'Outils Frontend',
                  tableau:[
                    {
                        nom: 'Sass',
                        maitrise: 4
                    },
                    {
                        nom: 'Vue.js',
                        maitrise: 3
                    },
                    {
                        nom: 'Flutter',
                        maitrise: 2
                    }
                  ],
              },
              {
                  titre:  'Outils Backend',
                  tableau:[
                    {
                        nom: 'Node.js',
                        maitrise: 3
                    },
                    {
                        nom: 'Express',
                        maitrise: 2
                    }
                  ],
              },
              {
                  titre:  'Base de données',
                  tableau:[
                    {
                        nom: 'MySQL',
                        maitrise: 3
                    },
                    {
                        nom: 'Sequelize',
                        maitrise: 3
                    },
                    {
                        nom: 'MongoDB',
                        maitrise: 3
                    },
                    {
                        nom: 'Firestore',
                        maitrise: 1
                    },
                  ],
              },
              {
                  titre:  'Gestion de  projets',
                  tableau:[
                    {
                        nom: 'Git',
                        maitrise: 3
                    },
                    {
                        nom: 'GitHub',
                        maitrise: 3
                    }
                  ],
              },
              {
                  titre:  'Logiciels',
                  tableau:[
                    {
                        nom: 'VS Code',
                        maitrise: 3
                    },
                    {
                        nom: 'Illustrator',
                        maitrise: 3
                    },
                    {
                        nom: 'Pack Microsoft',
                        maitrise: 3
                    }
                  ],
              },
              {
                  titre:  'Langues',
                  tableau:[
                    {
                        nom: 'Anglais',
                        maitrise: 3
                    },
                    {
                        nom: 'Allemand',
                        maitrise: 2
                    }
                  ],
              },
          ],
      }
  }
}
</script>