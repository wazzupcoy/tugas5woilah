<template>
  <q-layout view="hHh lpR fFf">

    <!-- Navbar -->
    <q-header elevated class="bg-black text-white">
      <q-toolbar class="justify-center">
        <q-toolbar-title>
          <q-avatar>
            <img src="./assets/Thezshowroom.jpg">
          </q-avatar>
          THZ Luxury 
        </q-toolbar-title>
        <!-- Navigation Tabs -->
        <div class="flex flex-center flex-auto">
          <q-tabs dense v-model="activeTab">
            <q-tab name="home" @click="navigateTo('home')">Home</q-tab>
            <q-tab name="car" @click="navigateTo('car')">Car</q-tab>
            <q-tab name="product" @click="navigateTo('product')">Product</q-tab>
            <q-tab name="about" @click="navigateTo('about')">About Us</q-tab>
          </q-tabs>
        </div>
        <q-btn dense flat round icon="menu" @click="toggleRightDrawer" />
      </q-toolbar>
    </q-header>

    <!-- Right Drawer -->
    <q-drawer v-model="rightDrawerOpen" side="right" overlay>
      <!-- drawer content -->
      <q-list>
        <q-item clickable v-ripple>
          <q-item-section>Mercedes-Benz</q-item-section>
        </q-item>
        <q-item clickable v-ripple>
          <q-item-section>Bentley </q-item-section>
        </q-item>
        <q-item clickable v-ripple>
          <q-item-section>Aston Martin </q-item-section>
        </q-item>
        <q-item clickable v-ripple>
          <q-item-section>Rolls-Royce</q-item-section>
        </q-item>
        <q-item clickable v-ripple>
          <q-item-section>Bugatti</q-item-section>
        </q-item>
        <q-item clickable v-ripple>
          <q-item-section>BMW</q-item-section>
        </q-item>
        <q-item clickable v-ripple>
          <q-item-section>Koenigsegg</q-item-section>
        </q-item>
        <q-item clickable v-ripple>
          <q-item-section>Ferrari</q-item-section>
        </q-item>
        <q-item clickable v-ripple>
          <q-item-section>Lamborghini</q-item-section>
        </q-item>
      </q-list>
    </q-drawer>

    <!-- Page Container -->
    <q-page-container>
      <q-page class="q-pa-md">
        
        <!-- Carousel -->
        <q-carousel
          animated
          v-model="slide"
          arrows
          navigation
          infinite
          autoplay
          class="carousel-height"
        >
          <q-carousel-slide :name="1" img-src="./assets/koenigsegg.png" />
          <q-carousel-slide :name="2" img-src="./assets/mercedes.jpg" />
          <q-carousel-slide :name="3" img-src="./assets/porshce911.jpg" />
          <q-carousel-slide :name="5" img-src="./assets/KoenigseggLegera.jpg" />
          <q-carousel-slide :name="6" img-src="./assets/F8.jpg" />
        </q-carousel>

        <div class="container">
          <p class="paragraf">Initiated in 2024, THZ LUXURY <br> is an automotive dealership that <br> focuses on growing the luxury market.</p>
          <p class="paragraf2">THZ offers the best investment and ownership experience with the most efficient <br> operations. With a strong value in teamwork and a well-maintained community,<br> THZ builds and embeds the passion for luxury automotive within our practice.<br> Our goal is to serve people with unique & passionate thrill-seekers, which the<br> main thing THZ can provide.</p>
        </div>
        <!-- Cards -->
        <div class="q-gutter-md q-mt-md row justify-around">
          <q-card class="my-card">
            <q-img src="./assets/koenignseggregera.png" />
            <q-card-section>
              <div class="text-h6">Koenigsegg Regera</div>
              <div class="text-subtitle1">$1.900.000</div>
            </q-card-section>
            <q-card-actions align="right">
              <q-btn flat label="Buy" color="primary" />
            </q-card-actions>
          </q-card>

          <q-card class="my-card">
            <q-img src="./assets/carera911.png" />
            <q-card-section>
              <div class="text-h6">Carera 911 Turbo (966)</div>
              <div class="text-subtitle1">$130.900 </div>
            </q-card-section>
            <q-card-actions align="right">
              <q-btn flat label="Buy" color="primary" />
            </q-card-actions>
          </q-card>

          <q-card class="my-card">
            <q-img src="./assets/Aston.jpg" />
            <q-card-section>
              <div class="text-h6">Aston Martin 2023</div>
              <div class="text-subtitle1">$130,900 </div>
            </q-card-section>
            <q-card-actions align="right">
              <q-btn flat label="Buy" color="primary" />
            </q-card-actions>
          </q-card>

          <q-card class="my-card">
            <q-img src="./assets/mercy.jpg" />
            <q-card-section>
              <div class="text-h6">2024 Mercedes-AMG GT</div>
              <div class="text-subtitle1">$136,050</div>
            </q-card-section>
            <q-card-actions align="right">
              <q-btn flat label="Buy" color="primary" />
            </q-card-actions>
          </q-card>

          <q-card class="my-card">
            <q-img src="./assets/bentley.png" />
            <q-card-section>
              <div class="text-h6">Bentley Continental GT Coupe</div>
              <div class="text-subtitle1">$245,000</div>
            </q-card-section>
            <q-card-actions align="right">
              <q-btn flat label="Buy" color="primary" />
            </q-card-actions>
          </q-card>

        </div>

      </q-page>
    </q-page-container>

    <!-- Footer -->
    <footer>
	<p>Farhan Akbar</p>
	<p>Informatika</p>
	<div class="social">
		<a href="#"><i class='bx bxl-instagram-alt' ></i></a>
		<a href="#"><i class='bx bxl-discord-alt' ></i></a>
		<a href="#"><i class='bx bxl-twitter' ></i></a>
	</div>
	<p class="end">&copy; Copy right by HAN</p>
</footer>


  </q-layout>
</template>

<script>
import { ref } from 'vue'

export default {
  setup () {
    const slide = ref(1)
    const rightDrawerOpen = ref(false)
    const activeTab = ref('home')

    const toggleRightDrawer = () => {
      rightDrawerOpen.value = !rightDrawerOpen.value
    }

    const navigateTo = (tab) => {
      activeTab.value = tab
      // Here you can add logic to navigate to the respective route
    }

    return {
      slide,
      rightDrawerOpen,
      toggleRightDrawer,
      activeTab,
      navigateTo
    }
  }
}
</script>

<style lang="scss" scoped>
.carousel-height {
  height: 400px; /* Atur tinggi sesuai kebutuhan */
}

.my-card {
  width: 100%;
  max-width: 250px;
}
.container{
  background-color:#f6f5f2;
}


.paragraf {
  font-size: 25px;
  margin-left: 130px;
  padding-top: 70px;
  padding-bottom: 120px;
  color: rgb(120, 120, 120);
}

.paragraf2{
  font-size: 18px;
  position: absolute;
  margin-left: 800px;
  margin-top: -245px;
  color: rgb(120, 120, 120);
}

/* Centered Tabs */
.q-tabs {
  margin-right: 500px;
}

footer{
	position: relative;
	width: 100%;
	height: 200px;
	background: #101010;
	display: flex;
	flex-direction: column;
	align-items: center;
	justify-content: center;
}
footer p:nth-child(1){
	font-size: 30px;
	color: white;
	margin-bottom: 5px;
	font-weight: bold;
}
footer p:nth-child(2){
	color: white;
	font-size: 17px;
	width: 500px;
	text-align: center;
	line-height: 26px;
}

.social{
	display: flex;

}
.social a{
	width: 45px;
	height: 45px;
	display: flex;
	align-items: center;
	justify-content: center;
	border-radius:50% ;
	background: #1A2C50;
	margin: 22px 10px;
	color: white;
	text-decoration: none;
	font-size: 20px;
}
.social a:hover{
	transition: .4s;
	transform: scale(1.3);
}
.end{
	position: absolute;
	color: #1A2C50;
	margin-bottom: -6px;
	font-size: 14px;
}

</style>
