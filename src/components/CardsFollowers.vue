<template>
  <section :class="darkmode === true ? 'night' : ''">
      <div class="container">
          <div class="header_card">
              <div class="Toggledesktop d-flex justify-content-between align-items-center">
                  <div>
                      <h2 class="fw-bold mt-3">Social Media Dashboard</h2>
                      <p class="fw-bold">Total Followers: 23,004</p>
                  </div>

                  <div class="d-none d-md-block d-md-flex gap-2">
                    <p class="fw-bold m-0">Dark Theme</p>

                    <label for="btn" class="switch">
                        <input id="btn" type="checkbox">
                        <span class="slider" @click="$emit('customChange', $event.target.value)"></span>
                    </label>
                  </div>
              </div>
              

              <!-- Display Menu Toggle Mobile -->
              <hr class="d-block d-md-none">

              <div class="d-block d-md-none d-flex align-items-center justify-content-between">
                  <p class="fw-bold m-0">Dark Theme</p>

                  <label for="btn" class="switch">
                      <input id="btn" type="checkbox" :checked='darkmode'>
                      <span class="slider" @click="$emit('customChange', $event.target.value)"></span>
                  </label>
              </div>
          </div>

          <div class="cards mt-5 d-md-flex gap-3 pb-3">
              <div class="box mt-3 w-100" v-for="data in sociaisInfo" :key="data.id">
                    <div class="user-social text-center p-3 d-flex flex-column gap-3 rounded" :style="[data.borderColor]">
                          <a href="#" class="d-flex align-items-center gap-2 justify-content-center">
                              <i :class="[data.icon]"></i>
                              <span class="fw-bold text-muted">{{data.nameUser}}</span>
                          </a>

                          <div class="followers">
                              <p class="number m-0 fw-bold">{{data.numbers}}</p>
                              <span class="follow text-muted">{{data.type}}</span>
                          </div>

                          <div class="day">
                              <a href="#" :style="[data.color]" class="d-flex align-items-center gap-2 justify-content-center">
                                  <i class="fa-solid fa-angle-up"></i>
                                  <span class="fw-bold">{{data.days}} Today</span>
                              </a>
                          </div>
                    </div>
              </div>
          </div>
      </div>
  </section>
</template>

<script>
export default {
    props: ['darkmode'],
    data() {
        return {
            sociaisInfo: [
                {nameUser: '@nathanf', numbers: 1987, days: 12, borderColor: 'border-top: 4px solid var(--clr-Facebook);', icon: 'fa-brands fs-2 fa-facebook-square', color: 'color: var(--clr-LimeGreen);', type: 'followers'},

                {nameUser: '@nathanf', numbers: 1044, days: 99, borderColor: 'border-top: 4px solid var(--clr-Twitter);', icon: 'fa-brands fs-2 fa-twitter', color: 'color: var(--clr-LimeGreen);', type: 'followers'},

                {nameUser: '@realnathanf', numbers: '11k', days: 1099, borderColor: 'border-top: 4px solid #df4996;', icon: 'fa-brands fs-2 fa-instagram', color: 'color: var(--clr-LimeGreen);', type: 'followers'},

                {nameUser: 'Nathan F.', numbers: 8239, days: 144, borderColor: 'border-top: 4px solid var(--clr-youTube);', icon: 'fa-brands fs-2 fa-youtube', color: 'color: var(--clr-youTube);', type: 'subscribe'},
            ]
        }
    },
}
</script>

<style scoped>
h2 {
    color: var(--bg-VeryDarkBlue);
}

p {
    color: var(--bg-DarkGrayishBlue);
}

a {
    text-decoration: none;
}

.box {
    background-color: var(--bg-LightGrayishBlue);
    transition: background .5s;
    cursor: pointer;
}

.box:hover {
    background-color: var(--tg-white);
}

.number {
    font-size: 60px;
    color: var(--bg-VeryDarkBlue);
}

.follow {
    text-transform: uppercase;
    letter-spacing: 5px;
}

.fa-youtube {
    color: var(--clr-youTube);
}

.fa-instagram {
    background: -webkit-linear-gradient(0deg, #fdc468 0%, #df4996 100%);
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
}

/* Toggle Button */
.switch {
  position: relative;
  display: inline-block;
  width: 50px;
  height: 25px;
}

.switch input {
  opacity: 0;
  width: 0;
  height: 0;
}

.slider {
  position: absolute;
  cursor: pointer;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  background-color: var(--tg-white);
  -webkit-transition: .4s;
  transition: .4s;
  border-radius: 20px;
}

.slider:before {
  position: absolute;
  content: "";
  height: 16px;
  width: 16px;
  left: 4px;
  bottom: 4px;
  background-color: white;
  -webkit-transition: .4s;
  transition: .4s;
  border-radius: 50%;
}

input:checked + .slider {
  background: linear-gradient(0deg, hsl(210, 78%, 56%) 0%, hsl(146, 68%, 55%) 100%);
}

input:focus + .slider {
  box-shadow: 0 0 1px #2196F3;
}

input:checked + .slider:before {
  -webkit-transform: translateX(26px);
  -ms-transform: translateX(26px);
  transform: translateX(26px);
}

/* Dark Mode */
.night {
  background: var(--bg-DarkDesaturatedBlue);
  color: #fff;
}

.night h2 {
    color: #fff;
}

.night p {
    color: #fff;
}

.night .box {
    background: var(--bg-VeryMediumBlue);
}

.night .box:hover {
    background: var(--bg-DarkDesaturatedBlue);
}
</style>