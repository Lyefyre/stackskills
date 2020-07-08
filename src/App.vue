<template>
  <div class="container">
    <div class="row">
      <div class="col-sm-12">
        <nav-header @pageWasChanged="currentPage = $event"></nav-header>
        <keep-alive>
          <component :is="currentPage"></component>
        </keep-alive>
        <ccfooter>
          <p class="text-center" slot="app-name">&copy; {{ appName }}</p>
          <nav>
            <ul class="nav justify-content-center">
              <li class="nav-item"><a class="nav-link" @click="pageSelected='cardFront'">Home</a></li>
              <li class="nav-item"><a class="nav-link" @click="pageSelected='cardFront'">About us</a></li>
              <li class="nav-item"><a class="nav-link" @click="pageSelected='cardFront'">Contact us</a></li>
            </ul>
          </nav>
        </ccfooter>
      </div>
    </div>
  </div>
</template>

<script>
import FirebaseConfig from './firebaseConfig'
import Header from "./components/Header.vue"
import CardFront from "./components/card/CardFront.vue"
import CardInsideLeft from "./components/card/CardInsideLeft.vue"
import CardInsideRight from "./components/card/CardInsideRight.vue"
import CardBack from "./components/card/CardBack.vue"
import Footer from "./components/Footer.vue"

export default {
  data: function() {
    return {
      currentPage: "cardFront",
      appName: "Creative Cards"
    }
  },
  components: {
    navHeader: Header,
    cardFront: CardFront,
    cardInsideLeft: CardInsideLeft,
    cardInsideRight: CardInsideRight,
    cardBack: CardBack,
    ccfooter: Footer
  }
};
</script>

<style>
body {
  font-family: Verdana, Geneva, sans-serif;
  color: #333;
}

a {
  cursor: pointer;
}
</style>