<template>
    <div calss="advertisement-banner">
        <div class="bannerr">
            <div class="first-banner">
                <div class="first-banner-content">
                    баннер с рекламой
                </div>
            </div>
            <div class="second-banner">
                <div class="second-banner-content">
                    баннер с рекламой
                </div>
            </div>
            <div class="third-banner">
                <div class="third-banner-content">
                    баннер с рекламой
                </div>
            </div>
            <div class="fourth-banner">
                <div class="fourth-banner-content">
                    баннер с рекламой
                </div>
            </div>
        </div>
    </div>
</template>

<script>

</script>

<style>
@import url('https://fonts.googleapis.com/css2?family=Montserrat:wght@400;600&display=swap');


* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

body {
  font-family: 'Montserrat', sans-serif;
}

.advertisement-banner {
  display: flex;
  justify-content: center;
  align-items: center;
  background-size: 100% 100%;
  background-repeat: no-repeat; 
  background-position: center; 
  width: 100vw; 
  height: auto;
  min-height: 500px;
  margin: 0 auto; 
  box-sizing: border-box;
  margin-top: 20px; 
  margin-bottom: -40px;
  background-color: #f2f4f0;
}

.bannerr {
  max-width: 1200px;
  margin: 0 auto;
  display: flex;
  flex-wrap: wrap; 
  justify-content: space-between; 
  padding: 20px;
  background-color: #f2f4f0;
  min-height: 500px;
  border-radius: 25px;
  margin-top: 50px;
}

.first-banner, .second-banner, .third-banner, .fourth-banner {
  display: flex;
  width: 570px; 
  min-height: 150px;
  background-color: white;
  border-radius: 15px;
  margin-bottom: 20px; 
  justify-content: center;
  align-items: center;
}



</style>