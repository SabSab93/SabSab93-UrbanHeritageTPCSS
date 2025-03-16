<template>
  <div class="container">
    <!-- Offre Défilante -->
    <div class="offer-bar bg-white border-bottom py-2">
      <div class="container">
        <span class="offer-text fs-5">
          LIVRAISON OFFERTE DÈS 180 € D’ACHAT (FRANCE MÉTROPOLITAINE) /
          LIVRAISON OFFERTE DÈS 180 € D’ACHAT (FRANCE MÉTROPOLITAINE) /
          LIVRAISON OFFERTE DÈS 180 € D’ACHAT (FRANCE MÉTROPOLITAINE) /
          LIVRAISON OFFERTE DÈS 180 € D’ACHAT (FRANCE MÉTROPOLITAINE) /
          LIVRAISON OFFERTE DÈS 180 € D’ACHAT (FRANCE MÉTROPOLITAINE) /
          LIVRAISON OFFERTE DÈS 180 € D’ACHAT (FRANCE MÉTROPOLITAINE) /
          LIVRAISON OFFERTE DÈS 180 € D’ACHAT (FRANCE MÉTROPOLITAINE) /
        </span>
      </div>
    </div>

    <Navbar />
    <HeroSection />
    
    <section class="most-wanted py-5">
      <h2 class="text-center mb-4">MOST WANTED</h2>
      <div class="row row-cols-1 row-cols-sm-2 row-cols-md-3 row-cols-lg-4 g-4">
        <ProductCard 
          v-for="product in products" 
          :key="product.id" 
          :product="product" 
          class="col"
        />
      </div>
    </section>
    
    <Footer />
  </div>
</template>

<script>
import Navbar from "@/components/AppNavbar.vue";
import HeroSection from "@/components/HeroSection.vue";
import ProductCard from "@/components/ProductCard.vue";
import Footer from "@/components/AppFooter.vue";

export default {
  components: {
    Navbar,
    HeroSection,
    ProductCard,
    Footer,
  },
  data() {
    return {
      products: [
        { id: 1, name: "T-Shirt", image: "tshirt.png", description: "Superbe t-shirt", price: "100€" },
        { id: 2, name: "Sweater", image: "sweater.png", description: "Chaud et confortable", price: "100€" },
        { id: 3, name: "Sweater", image: "sweater.png", description: "Chaud et confortable", price: "100€" },
        { id: 4, name: "Blue Pants", image: "pants.png", description: "Jeans moderne", price: "100€" },
      ],
    };
  },
};
</script>

<style scoped>
/* Offer Bar */
.offer-bar {
  background-color: white;
  border-bottom: 1px solid black;
  overflow: hidden; /* Cache tout excédent de texte */
}

.offer-text {
  display: inline-block;
  white-space: nowrap; /* Evite que le texte soit coupé */
  animation: scroll-left 30s linear infinite; /* Animation de défilement */
}

@keyframes scroll-left {
  0% {
    transform: translateX(100%); /* Le texte commence hors de l'écran à droite */
  }
  100% {
    transform: translateX(-100%); /* Le texte se déplace complètement à gauche */
  }
}
</style>
