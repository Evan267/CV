<template>
  <div id="appp">
    <div id="nav" class="nav__mobile">
      <button v-on:click="CacherNavBar()"><i class="fas fa-arrow-left"></i></button>
      <nav>
        <ul>
          <li>
            <a href="#etudes" class="nav__link" v-on:click="CacherNavBar()">Études</a>
          </li>
          <li>
            <a href="#formation" class="nav__link" v-on:click="CacherNavBar()">Formation Developpeur Web</a>
          </li>
          <li>
            <a href="#experience" class="nav__link" v-on:click="CacherNavBar()">Expérience professionelle</a>
          </li>
          <li>
            <a href="#competence" class="nav__link" v-on:click="CacherNavBar()">Compétences</a>
          </li>
          <li>
            <a href="#contact" class="nav__link" v-on:click="CacherNavBar()">Contact</a>
          </li>
        </ul>
      </nav>
    </div>
    <div>
      <div class="loader">
        <div class="loader__spinner">
        </div>
      </div>
      <button class="nav__responsiveButton" v-on:click="AffichNavBar()"><i class="fas fa-bars"></i></button>
      <header class="header" v-on:click="CacherNavBar()">
        <div class="header__info">
          <img class="header__img" alt="Vue logo" src="./assets/129503904_374638387162926_3392795190868680163_n.jpg">
          <div class="header__txt">
            <h1>Evan Berger</h1>
            <p>Développeur Web en CDI/CDD</p>
            <p>(HTML, CSS, JS, Dart, MySQL)</p>
          </div>
        </div>
        <nav>
          <ul class="nav">
            <li>
              <a href="#etudes" class="nav__link">Études</a>
            </li>
            <li>
              <a href="#formation" class="nav__link">Formation Developpeur Web</a>
            </li>
            <li>
              <a href="#experience" class="nav__link">Expérience professionelle</a>
            </li>
            <li>
              <a href="#competence" class="nav__link">Compétences</a>
            </li>
            <li>
              <a href="#contact" class="nav__link">Contact</a>
            </li>
          </ul>
        </nav>
      </header>
      <div class="grid-print" v-on:click="CacherNavBar()">
        <section id="etudes" class="reveal-visible-etudes">
          <Etudes></Etudes>
        </section>
        <section id="formation" class="reveal">
          <Formation></Formation>
        </section>
        <section id="experience" class="reveal">
          <Experience></Experience>
        </section>
        <section id="competence" class="reveal">
          <Competence></Competence>
        </section>
        <section id="centredinteret" class="reveal">
          <CentreDinteret></CentreDinteret>
        </section>
        <footer id="contact">
          <Contact></Contact>
        </footer>
      </div>
    </div>
    
  </div>
</template>

<script>
import Experience from "./components/Experience"
import Etudes from "./components/Etudes"
import Formation from "./components/Formation"
import CentreDinteret from "./components/CentreDinteret"
import Competence from "./components/Competence"
import Contact from "./components/Contact"


export default {
  name: 'App',
  components: {
    Experience,
    Etudes,
    Formation,
    CentreDinteret,
    Competence,
    Contact
  },
  mounted(){
    this.AffichElement()
  },
  methods: {
    async CacherNavBar(){
      const element = document.getElementById('nav');
      element.classList.remove('nav__mobile--view');
    },
    async AffichNavBar(){
      const element = document.getElementById('nav');
      element.classList.add('nav__mobile--view');
    },
    async AffichElement(){
      const ratio = .4;
      const options = {
          root: null,
          rootMargin: '0px',
          threshold: ratio
      }

      const handleIntersect = function (entries, observer) {
        entries.forEach(function(entry) {
          if(entry.intersectionRatio > ratio){
            entry.target.classList.add('reveal-visible')
            observer.unobserve(entry.target);
          }
        })
      }

      const observer = new IntersectionObserver(handleIntersect, options);
      document.querySelectorAll('.reveal').forEach(function(r){
        observer.observe(r);
      })   
    }
  }
}

</script>

<style lang="scss">
@import "./scss/style.scss";
</style>
