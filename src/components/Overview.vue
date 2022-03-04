<template>
  <section>
      <div class="container">
          <h3 class="fw-bold text-muted mb-4 pt-5">Overview - Today</h3>
          <div class="miniCards">
              <div class="boxe p-3 rounded mb-3" v-for="data in overviewData" :key="data.id">
                  <div class="top d-flex justify-content-between">
                      <p class="title fw-bold text-muted">{{data.title}}</p>

                      <a href="#">
                          <i :class="[data.icon]"></i>
                      </a>
                  </div>

                  <div class="bottom d-flex align-items-center justify-content-between">
                      <p class="number">{{data.number}}</p>

                      <p class="percent fw-bold" :class="data.type">
                        <i :class="data.type === 'up' ? 'fa-solid fa-angle-up' : 'fa-solid fa-angle-down'"></i> {{data.percent}}
                      </p>
                  </div>
              </div>
          </div>
      </div>
  </section>
</template>

<script>
export default {
    data() {
        return {
            name: 'Overview',
            overviewData: [
                {title: 'Page Views', icon: 'fa-brands fs-2 fa-facebook-square', number: '87', percent: '3%', type: 'up'},

                {title: 'Likes', icon: 'fa-brands fs-2 fa-facebook-square', number: '52', percent: '2%', type: 'down'},

                {title: 'Likes', icon: 'fa-brands fs-2 fa-instagram', number: '5482', percent: '2257%', type: 'up'},

                {title: 'Profile Views', icon: 'fa-brands fs-2 fa-instagram', number: '52k', percent: '1375%', type: 'up'},

                {title: 'Retweets', icon: 'fa-brands fs-2 fa-twitter', number: '117', percent: '303%', type: 'up'},

                {title: 'Likes', icon: 'fa-brands fs-2 fa-twitter', number: '507', percent: '553%', type: 'up'},

                {title: 'Likes', icon: 'fa-brands fs-2 fa-youtube-square', number: '107', percent: '19%', type: 'down'},

                {title: 'Total Views', icon: 'fa-brands fs-2 fa-youtube-square', number: '1407', percent: '12%', type: 'down'},
            ]
        }
    },
}
</script>

<style scoped>
.boxe {
    background: var(--bg-LightGrayishBlue);
    transition: background .5s;
    cursor: pointer;
}

.boxe .title {
    color: var(--bg-VeryDarkBlue);
}

.boxe:hover {
    background: var(--tg-white);
}

.boxe .number {
    font-size: 40px;
    font-weight: bold;
}

.fa-youtube-square {
    color: var(--clr-youTube);
}

.fa-instagram {
    background: -webkit-linear-gradient(0deg, #fdc468 0%, #df4996 100%);
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
}

.up {
    color: var(--clr-LimeGreen);
}

.down {
    color: var(--clr-youTube);
}

.miniCards {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
    gap: 20px;
}

/* Dark Mode */
.night {
  background: var(--bg-VeryDarkBlue);
  color: #fff;
}

.night .boxe {
    background: var(--bg-DarkDesaturatedBlue);
}

.night .boxe:hover {
    background: var(--bg-DesaturatedBlue);
}
</style>