<template>
  <div id="appp">
    <header class="header">
      <div class="header__info">
        <img class="header__img" alt="Vue logo" src="./assets/129503904_374638387162926_3392795190868680163_n.jpg">
        <div class="header__txt">
          <h1>Evan Berger</h1>
          <p>Developpeur Web</p>
        </div>
      </div>
      <nav>
        <ul class="nav">
          <li>
            <a href="#experience" class="nav__link">Expérience professionelle</a>
          </li>
          <li>
            <a href="#etudes" class="nav__link">Études</a>
          </li>
          <li>
            <a href="#formation" class="nav__link">Formation Developpeur Web</a>
          </li>
          <li>
            <a href="#centredinteret" class="nav__link">Centre d'interet</a>
          </li>
          <li>
            <a href="#contact" class="nav__link">Contact</a>
          </li>
        </ul>
      </nav>
    </header>
    <section id="experience" class="reveal">
      <Experience></Experience>
    </section>
    <section id="etudes" class="reveal">
      <Etudes></Etudes>
    </section>
    <section id="formation" class="reveal">
      <Formation></Formation>
    </section>
    <section id="centredinteret" class="reveal">
      <CentreDinteret></CentreDinteret>
    </section>
    <footer id="contact">
      <Contact></Contact>
    </footer>
  </div>
  
</template>

<script>
import Experience from "./components/Experience"
import Etudes from "./components/Etudes"
import Formation from "./components/Formation"
import CentreDinteret from "./components/CentreDinteret"
import Contact from "./components/Contact"

export default {
  name: 'App',
  components: {
    Experience,
    Etudes,
    Formation,
    CentreDinteret,
    Contact
  },
  mounted(){
    this.affichElement()
  },
  methods: {
    async affichElement(){
      const ratio = .5;
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




.reveal{
  opacity: 0;
}

.reveal-visible{
  opacity:1;
  transition: 1000ms cubic-bezier(.45,0,.35,1);
}


</style>
