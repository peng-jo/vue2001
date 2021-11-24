<template>
  <div class="allBg">
    <div class="container">
      <!-- header -->
      <Header />
    </div>
    <!-- //container -->

    <!-- main -->
    <main id="main">
      <div
        class="banner"
        :style="{
          backgroundImage: `linear-gradient(rgba(0, 0, 0, 0.8), rgba(0, 0, 0, 0.8)), url('https://image.tmdb.org/t/p/w780/${this.selInfo.backdrop_path}')`,
        }"
      >
        <div class="container">
          <div class="mainCont">
            <div class="poster">
              <img
                :src="
                  'https://image.tmdb.org/t/p/w500/' + this.selInfo.poster_path
                "
                alt="포스터"
              />
            </div>
            <div class="info">
              <div class="info_cont">
                <h2 class="movieTitle">{{ this.selInfo.title }}</h2>
                <ul>
                  <li class="year">{{ this.selInfo.release_date }}</li>
                  <li class="runtime">{{ this.selInfo.runtime }}분</li>
                  <li class="genre">
                    <template
                      v-for="genres in this.selInfo.genres"
                      :key="genres.id"
                    >
                      <span v-if="genres.id !== 14">
                        {{ genres.name + '/' }}
                      </span>
                      <span v-else>
                        {{ genres.name }}
                      </span>
                    </template>
                  </li>
                </ul>
                <div class="stars">
                  <span class="percent">{{ this.selInfo.vote_average }}</span>
                </div>
                <p class="desc">
                  {{ this.selInfo.overview }}
                </p>
              </div>

              <a href="#">상세정보</a>
            </div>
          </div>
        </div>
      </div>
    </main>
    <!-- //main -->

    <!-- top10 -->
    <section id="top10">
      <div class="scontainer">
        <h3>TOP10 컨텐츠</h3>
        <swiper
          class="s0sliderWrap swiper-wrapper"
          :slides-per-view="5"
          :space-between="130"
        >
          <swiper-slide
            v-for="(movie, index) in movies.slice(0, 10)"
            :key="movie.id"
            class="s0 slider"
            v-on:click="movieClickHandler($event)"
            :id="movie.id"
          >
            <div class="s0 sliderNum">
              {{ index + 1 }}
            </div>
            <img
              class="s0 sliderImg"
              :src="'http://image.tmdb.org/t/p/w500' + movie.poster_path"
            />
          </swiper-slide>

          <!-- <swiper-slide class="s0 slider">
            <div class="s0 sliderNum">1</div>
            <div class="s0 sliderImg"></div>
          </swiper-slide> -->
        </swiper>
      </div>
    </section>
    <!-- //top10 -->

    <!-- section01 -->
    <section id="popular">
      <div class="scontainer">
        <h3>인기영화</h3>
        <swiper
          class="s1sliderWrap swiper-wrapper"
          :slides-per-view="5"
          :space-between="50"
        >
          <swiper-slide
            v-for="movie in movies"
            :key="movie.id"
            class="s1 slider"
          >
            <img
              :src="'http://image.tmdb.org/t/p/w500/' + movie.poster_path"
              class="s1 sliderImg"
            />
            <div class="s1 sliderDesc">
              <div class="s1 sliderTitle">{{ movie.original_title }}</div>
              <div class="s1 sliderDay">{{ movie.release_date }}</div>
            </div>
          </swiper-slide>
        </swiper>
      </div>
    </section>
    <!-- //section01 -->

    <!-- subject2 -->
    <section id="subject2">
      <div class="scontainer">
        <h3>주제2</h3>
        <swiper
          class="s1sliderWrap swiper-wrapper"
          :slides-per-view="5"
          :space-between="50"
        >
          <swiper-slide class="slider">
            <img class="sliderImg" />
            <div class="sliderDesc">
              <div class="sliderTitle">영화제목</div>
              <div class="sliderDay">상영일자</div>
            </div>
          </swiper-slide>
          <swiper-slide class="slider">
            <img class="sliderImg" />
            <div class="sliderDesc">
              <div class="sliderTitle">영화제목</div>
              <div class="sliderDay">상영일자</div>
            </div>
          </swiper-slide>
          <swiper-slide class="slider">
            <img class="sliderImg" />
            <div class="sliderDesc">
              <div class="sliderTitle">영화제목</div>
              <div class="sliderDay">상영일자</div>
            </div>
          </swiper-slide>
          <swiper-slide class="slider">
            <img class="sliderImg" />
            <div class="sliderDesc">
              <div class="sliderTitle">영화제목</div>
              <div class="sliderDay">상영일자</div>
            </div>
          </swiper-slide>
          <swiper-slide class="slider">
            <img class="sliderImg" />
            <div class="sliderDesc">
              <div class="sliderTitle">영화제목</div>
              <div class="sliderDay">상영일자</div>
            </div>
          </swiper-slide>
          <swiper-slide class="slider">
            <img class="sliderImg" />
            <div class="sliderDesc">
              <div class="sliderTitle">영화제목</div>
              <div class="sliderDay">상영일자</div>
            </div>
          </swiper-slide>
        </swiper>
      </div>
    </section>
    <!-- //subject2 -->

    <!-- subject2 -->
    <section id="subject2">
      <div class="scontainer">
        <h3>주제2</h3>
        <swiper
          class="s1sliderWrap swiper-wrapper"
          :slides-per-view="5"
          :space-between="50"
        >
          <swiper-slide class="slider">
            <img class="sliderImg" />
            <div class="sliderDesc">
              <div class="sliderTitle">영화제목</div>
              <div class="sliderDay">상영일자</div>
            </div>
          </swiper-slide>
          <swiper-slide class="slider">
            <img class="sliderImg" />
            <div class="sliderDesc">
              <div class="sliderTitle">영화제목</div>
              <div class="sliderDay">상영일자</div>
            </div>
          </swiper-slide>
          <swiper-slide class="slider">
            <img class="sliderImg" />
            <div class="sliderDesc">
              <div class="sliderTitle">영화제목</div>
              <div class="sliderDay">상영일자</div>
            </div>
          </swiper-slide>
          <swiper-slide class="slider">
            <img class="sliderImg" />
            <div class="sliderDesc">
              <div class="sliderTitle">영화제목</div>
              <div class="sliderDay">상영일자</div>
            </div>
          </swiper-slide>
          <swiper-slide class="slider">
            <img class="sliderImg" />
            <div class="sliderDesc">
              <div class="sliderTitle">영화제목</div>
              <div class="sliderDay">상영일자</div>
            </div>
          </swiper-slide>
          <swiper-slide class="slider">
            <img class="sliderImg" />
            <div class="sliderDesc">
              <div class="sliderTitle">영화제목</div>
              <div class="sliderDay">상영일자</div>
            </div>
          </swiper-slide>
        </swiper>
      </div>
    </section>
    <!-- //subject2 -->

    <!-- subject2 -->
    <section id="subject2">
      <div class="scontainer">
        <h3>주제2</h3>
        <swiper
          class="s1sliderWrap swiper-wrapper"
          :slides-per-view="5"
          :space-between="50"
        >
          <swiper-slide class="slider">
            <img class="sliderImg" />
            <div class="sliderDesc">
              <div class="sliderTitle">영화제목</div>
              <div class="sliderDay">상영일자</div>
            </div>
          </swiper-slide>
          <swiper-slide class="slider">
            <img class="sliderImg" />
            <div class="sliderDesc">
              <div class="sliderTitle">영화제목</div>
              <div class="sliderDay">상영일자</div>
            </div>
          </swiper-slide>
          <swiper-slide class="slider">
            <img class="sliderImg" />
            <div class="sliderDesc">
              <div class="sliderTitle">영화제목</div>
              <div class="sliderDay">상영일자</div>
            </div>
          </swiper-slide>
          <swiper-slide class="slider">
            <img class="sliderImg" />
            <div class="sliderDesc">
              <div class="sliderTitle">영화제목</div>
              <div class="sliderDay">상영일자</div>
            </div>
          </swiper-slide>
          <swiper-slide class="slider">
            <img class="sliderImg" />
            <div class="sliderDesc">
              <div class="sliderTitle">영화제목</div>
              <div class="sliderDay">상영일자</div>
            </div>
          </swiper-slide>
          <swiper-slide class="slider">
            <img class="sliderImg" />
            <div class="sliderDesc">
              <div class="sliderTitle">영화제목</div>
              <div class="sliderDay">상영일자</div>
            </div>
          </swiper-slide>
        </swiper>
      </div>
    </section>
    <!-- //subject2 -->
  </div>
  <Footer />
</template>
<script>
import { Swiper, SwiperSlide } from 'swiper/vue';
import Footer from '@/components/Footer.vue';
import Header from '@/components/Header.vue';
import 'swiper/swiper-bundle.min.css';
import 'swiper/swiper.min.css';
export default {
  components: {
    Swiper,
    SwiperSlide,
    Footer,
    Header,
  },

  data() {
    return {
      movieAPI: process.env.VUE_APP_MOVIE_KEY,
      requestOptions: {
        method: 'GET',
        redirect: 'follow',
      },
      movies: [],
      search: '',
      selId: 0,
      selInfo: {},
    };
  },
  methods: {
    movieClickHandler: function (event) {
      this.selId = event.target.parentNode.id;
    },
  },
  watch: {
    selId: function (newVal, oldVal) {
      console.log(newVal, oldVal);
      fetch(
        `https://api.themoviedb.org/3/movie/${newVal}?api_key=9624fce3bdac977743225762a42acb15&language=ko`,
        this.requestOptions
      )
        .then((response) => response.json())
        .then((result) => {
          this.selInfo = result;
        })
        .catch((error) => {
          console.error(error);
        });
    },
  },
  mounted() {
    fetch(
      `https://api.themoviedb.org/3/movie/popular?api_key=${this.movieAPI}&page=1`,
      this.requestOptions
    )
      .then((response) => response.json())
      .then((result) => {
        this.movies = result.results;
        console.log(this.movies);
        this.selId = result.results[0].id;
        console.log(result.results);
      })
      .catch((error) => console.log('error', error));
  },

  setup() {
    return {
      swiperOption: {
        loop: true,
      },
    };
  },
};
</script>
<style lang="scss">
@import url('https://fonts.googleapis.com/css2?family=Londrina+Outline&display=swap');
.allBg {
  font-family: 'GmarketSans';
  color: #fff;
  background-color: #000;
  overflow: hidden;
}
.container {
  max-width: 1280px;
  margin: 0 auto;
}
#header {
  padding-top: 20px;
  display: flex;
  font-family: 'S-CoreDream-3Light';
  background-color: #000;
  color: #fff;
  height: 80px;
}

ul {
  li {
    display: inline-block;
    margin-right: 20px;

    a {
      font-size: 24px;
      font-weight: 400;
    }
    a.active {
      border-bottom: 1px solid #fff;
    }
  }
}
.search {
  input {
    background: #282828;
    border-radius: 50px;
    font-family: 'S-CoreDream-3Light';
    padding: 15px 20px;
    outline: #000;
    color: #fff;
    width: 800px;
    height: 36px;
    border: 0;

    &::placeholder {
      font-size: 16px;
      font-weight: 400;
      color: #fff;
    }
  }
}

#main {
  font-family: 'GmarketSans';
  .banner {
    background-image: linear-gradient(rgba(0, 0, 0, 0.5), rgba(0, 0, 0, 0.5));
    background-repeat: no-repeat;
    background-size: cover;
    background-position: 50% 0%;
    // filter: brightness(20%);
    .mainCont {
      display: flex;
      justify-content: space-around;
      gap: 22px;
      padding: 100px 0;
      font-weight: 700;
      .poster {
        flex: 0 0 30%;
        display: inline-block;
        width: 100%;

        img {
          object-fit: cover;
          width: 100%;
          height: 63vh;
        }
      }
      .info_cont {
      }
      .info {
        display: flex;
        justify-content: space-around;
        flex-direction: column;
        flex: 0 0 70%;

        .movieTitle {
          font-size: 4.1vw;
          margin-bottom: 12px;
          display: inline-block;
        }
        ul {
          margin-bottom: 26px;
          li {
            font-size: 1.1vw;
            font-weight: 400;
            display: inline-block;
            margin-right: 30px;
          }
        }
        .stars {
          margin-bottom: 26px;
          .percent {
            font-size: 1.1vw;
            font-weight: 400;
          }
        }
        .desc {
          font-size: 1.14vw;
          font-weight: 300;
          line-height: 1.5;
        }
        // .more {
        //   text-align: center;
        //   border-radius: 50px;
        //   border: 1px solid rgba(255, 255, 255, 1);
        //   background-color: rgba(0, 0, 0, 1);
        //   display: inline-block;

        a {
          width: 8.9vw;
          padding: 0.8vh;
          text-align: center;
          font-size: 1.1vw;
          font-weight: 400;
          text-align: center;
          border-radius: 50px;
          border: 1px solid rgba(255, 255, 255, 1);
          background-color: rgba(0, 0, 0, 1);
          display: inline-block;
        }
      }
    }
  }
}

/* top10 */
#top10 {
  background-color: #141414;
  overflow: hidden;
  padding: 136px 0;

  h3 {
    font-size: 40px;
    font-weight: 500;
    color: #fff;
    margin-bottom: 28px;
  }
  .s0sliderWrap {
    width: 100%;
    cursor: move;
    display: flex;
    white-space: nowrap;
    overflow: hidden;
    padding-right: 10%;

    .slider {
      position: relative;
      .sliderNum {
        font-size: 220px;
        color: #000;
        -webkit-text-stroke-width: 3px;
        -webkit-text-stroke-color: #595959;
        font-family: 'NEXONLv2';
      }
      .sliderImg {
        position: absolute;
        top: 10%;
        left: 70%;
        background-color: #333;
        width: 100%;
        height: 200px;
      }
    }
  }
}

/* popular */
#popular {
  background-color: #000;
  overflow: hidden;
  padding: 136px 0;
}
.scontainer {
  width: 1320px;
  margin: 0 auto;
}
#popular h3 {
  font-size: 40px;
  font-weight: 500;
  color: #fff;
  margin-bottom: 28px;
}
#popular .s1sliderWrap {
  width: 100%;
  cursor: move;
  display: flex;
  white-space: nowrap;
  overflow: hidden;
}

#popular .s1sliderWrap .slider .sliderImg {
  background-color: #333;
  width: 100%;
  height: 302px;
  margin-bottom: 20px;
}
#popular .s1sliderWrap .slider .sliderDesc {
}
#popular .s1sliderWrap .slider .sliderDesc .sliderTitle {
  overflow: hidden;
  text-overflow: ellipsis;
  font-size: 20px;
  font-weight: 300;
  color: #fff;
  margin-bottom: 5px;
}
#popular .s1sliderWrap .slider .sliderDesc .sliderDay {
  font-size: 18px;
  font-weight: 300;
  color: rgba(255, 255, 255, 0.5);
}

/* subject2 */
#subject2 {
  background-color: #000;
  overflow: hidden;
  padding: 136px 0;
}
.scontainer {
  width: 1320px;
  margin: 0 auto;
}
#subject2 h3 {
  font-size: 40px;
  font-weight: 500;
  color: #fff;
  margin-bottom: 28px;
}
#subject2 .s1sliderWrap {
  width: 100%;
  cursor: move;
  display: flex;
  white-space: nowrap;
  overflow: hidden;
}

#subject2 .s1sliderWrap .slider .sliderImg {
  background-color: #333;
  width: 100%;
  height: 302px;
  margin-bottom: 20px;
}
#subject2 .s1sliderWrap .slider .sliderDesc .sliderTitle {
  overflow: hidden;
  text-overflow: ellipsis;
  font-size: 20px;
  font-weight: 300;
  color: #fff;
  margin-bottom: 5px;
}
#subject2 .s1sliderWrap .slider .sliderDesc .sliderDay {
  font-size: 18px;
  font-weight: 300;
  color: rgba(255, 255, 255, 0.5);
}
</style>
