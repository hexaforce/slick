<template>
  <v-app id="app">
    <section class="slick-black">
      <div class="content">
        <div class="slider center">
          <div v-for="(item,i) in Currencys" :key="i">
            <h3>
              <SelectItem :item="item" />
            </h3>
          </div>
        </div>
      </div>
    </section>
  </v-app>
</template>

<script>
import SelectItem from './components/SelectItem.vue'
export default {
  name: 'app',
  data: () => ({
    Currencys: ["Bitcoin" ,"BitcoinCash" ,"Ethereum" ,"EthereumClassic" ,"Litecoin" ,"Nem" ,"Ripple"],
  }),
  components: {
    SelectItem
  },
  mounted: function () {
    /* eslint-env jquery */
    $('.center').slick({
      centerMode: true,
      infinite: true,
      centerPadding: '60px',
      slidesToShow: 3,
      speed: 500,
      responsive: [{
        breakpoint: 768,
        settings: {
          arrows: false,
          centerMode: true,
          centerPadding: '40px',
          slidesToShow: 3
        }
      }, {
        breakpoint: 480,
        settings: {
          arrows: false,
          centerMode: true,
          centerPadding: '40px',
          slidesToShow: 1
        }
      }]
    })
  }
}
</script>

<style>
* {
  -moz-box-sizing: border-box;
  box-sizing: border-box;
}

.slick-black {
  background: #212121;
  color: #FAFAFA;
}

.slick-white {
  background: #FAFAFA;
  color: #212121;
}

.slick-black h3 {
  background: #FAFAFA;
  color: #212121;
  font-size: 36px;
  line-height: 100％;
  margin: 10px;
  padding: 2%;
  position: relative;
  text-align: center;
}

body, html {
  -moz-osx-font-smoothing: grayscale;
  -webkit-font-smoothing: antialiased;
  background: #FAFAFA;
  font-family: 'Lato', 'Helvetica Neue', 'Helvetica', Helvetica, Arial, sans-serif;
  height: 100%;
  line-height: 1;
  margin: 0;
  padding: 0;
  text-rendering: optimizeLegibility;
  width: 100%;
}

section {
  width: 100%;
  position: relative;
}

.content {
  margin: auto;
  padding: 20px;
  width: 600px;
}

.center h3 {
  opacity: 0.8;
  transition: all 300ms ease;
}

.content:after, .buttons::after {
  clear: both;
  content: '';
  display: table;
}

.button {
  background: #212121;
  color: #FAFAFA;
  display: block;
  font-size: 16px;
  margin: 20px auto;
  padding: 20px;
  text-align: center;
  text-decoration: none;
  width: 48%;
}

.buttons {
  padding: 0 20px 20px;
  margin-bottom: 10px;
}

.buttons .button {
  background: #FAFAFA;
  color: #212121;
  float: left;
  margin: 5px;
}

.center .slick-center h3 {
  -moz-transform: scale(1.08);
  -ms-transform: scale(1.08);
  -o-transform: scale(1.08);
  -webkit-transform: scale(1.08);
  color: #e67e22;
  opacity: 1;
  transform: scale(1.08);
}

.slick-slide .image {
  padding: 10px;
}

.slick-slide img {
  border: 5px solid #FAFAFA;
  display: block;
  width: 100%;
}

.slick-slide img.slick-loading {
  border: 0;
}

.slick-slider {
  margin: 30px auto 50px;
}

@media (max-width: 420px) {
  ul.nav li a {
    display: block;
    font-size: 14px;
  }
}

@media (max-width: 768px) {
  .slick-black h3 {
    font-size: 24px;
  }
  .button {
    margin: 0 auto 20px;
    width: auto;
  }
  .button.first {
    margin-top: 40px;
  }
  .buttons {
    padding: 0 0 20px;
  }
  .buttons .button {
    float: left;
    font-size: 12px;
    margin: 1%;
    width: 48%;
  }
  .center {
    margin-left: -40px;
    margin-right: -40px;
  }
  .center .slick-center h3 {
    -moz-transform: scale(1);
    -ms-transform: scale(1);
    -o-transform: scale(1);
    -webkit-transform: scale(1);
    color: #e67e22;
    opacity: 1;
    transform: scale(1);
  }
  .center h3 {
    -moz-transform: scale(0.95);
    -ms-transform: scale(0.95);
    -o-transform: scale(0.95);
    -webkit-transform: scale(0.95);
    opacity: 0.8;
    transform: scale(0.95);
    transition: all 300ms ease;
  }
  .content {
    margin: auto;
    padding: 20px 40px;
    width: auto;
  }
}
</style>
