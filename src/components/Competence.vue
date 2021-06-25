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
          <div class="competence__softSkills competence__softSkills1">
              <i class="fas fa-users"></i>
              <p>Esprit d'équipe</p>
          </div>
          <div class="competence__softSkills competence__softSkills2">
              <i class="fas fa-hourglass-half"></i>
              <p>Rigueur</p>
          </div>
          <div class="competence__softSkills competence__softSkills3">
              <i class="far fa-clock"></i>
              <p>Ponctualité</p>
          </div>
      </div>
    </div>
</template>

<script>
export default {
  name: 'Logiciel',
  data () {
      return{
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
                  titre:  'Bases de données',
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
                  titre:  'Logiciels',
                  tableau:[
                    {
                        nom: 'Visual Studio Code',
                        maitrise: 3
                    },
                    {
                        nom: 'Adobe Illustrator',
                        maitrise: 3
                    },
                    {
                        nom: 'Pack Microsoft',
                        maitrise: 3
                    }
                  ],
              },
          ],
      }
  }
}
</script>