<template>
  <footer class="footer">
    <nav>
      <div class="join">
        <img
          src="/img/movie.svg"
          alt="The Movie Database (TMDB)"
          width="130"
          height="94"
        />

        <a class="rounded" href="/">커뮤니티 참여</a>
      </div>

      <div>
        <h3>The Basics</h3>
        <ul>
          <li><a href="/about">TMDb에 대해</a></li>
          <li><a href="/about/staying-in-touch">문의하기</a></li>
          <li><a href="/talk">Support Forums</a></li>
          <li><a href="/documentation/api">API</a></li>
          <li>
            <a
              href="https://status.themoviedb.org/"
              target="_blank"
              rel="noopener"
              >System Status</a
            >
          </li>
        </ul>
      </div>
      <div>
        <h3>참여하기</h3>
        <ul>
          <li>
            <a href="/bible"
              ><span class="glyphicons glyphicons-asterisk"></span> 기여
              지침서</a
            >
          </li>
          <li><a href="/apps">타사 응용 프로그램</a></li>
          <li><a href="/movie/new">새 영화 추가</a></li>
          <li><a href="/tv/new">새 TV 프로그램 추가</a></li>
        </ul>
      </div>
      <div>
        <h3>커뮤니티</h3>
        <ul>
          <li><a href="/documentation/community/guidelines">가이드라인</a></li>
          <li><a href="/discuss">토론 내역</a></li>
          <li><a href="/leaderboard">기여 랭킹</a></li>
          <li>
            <a
              href="https://twitter.com/themoviedb"
              target="_blank"
              rel="noopener"
              >Twitter</a
            >
          </li>
        </ul>
      </div>
      <div>
        <h3>법적 사항</h3>
        <ul>
          <li>
            <a href="/documentation/website/terms-of-use">서비스 이용약관</a>
          </li>
          <li>
            <a href="/documentation/api/terms-of-use">API Terms of Use</a>
          </li>
          <li><a href="/privacy-policy">개인정보약관</a></li>
        </ul>
      </div>
    </nav>
  </footer>
</template>

<style>
.footer {
  max-width: 100%;
  width: 100%;
  box-sizing: border-box;
  padding: 0;
  background-color: #031d33;
  display: flex;
  flex-wrap: wrap;
  align-items: center;
  align-content: space-around;
  justify-content: center;
}
.footer nav {
  font-size: 15px;
  display: flex;
  justify-content: space-between;
  padding-top: 80px;
  padding-bottom: 80px;
  color: #fff;
}
.footer > div {
  margin-right: 40px;
  min-width: 0;
  box-sizing: border-box;
  display: block;
}
.footer nav > div h3 {
  font-weight: bold;
  font-size: 13px;
  line-height: 13px;
  text-transform: uppercase;
  color: #fff;
  white-space: nowrap;
}
.footer .join {
  text-align: right;
  position: relative;
  top: -36px;
  right: 0;
  margin-right: 30px;
}
.footer .join img {
  z-index: 1000;
  display: block;
  position: absolute;
  top: 0;
  right: 0;
  width: 130px;
  height: 94px;
}
.footer .join a.rounded {
  position: relative;
  top: 140px;
  border-color: #fff;
  background-color: #fff;
  color: rgba(1, 180, 228);
  font-weight: bold;
  display: inline-block;
  word-wrap: break-word;
  white-space: nowrap;
  text-transform: uppercase;
  border: 2px solid #fff;
  border-radius: 5px;
  padding: 8px 16px;
  transition: linear 0.1s;
}
.footer nav ul {
  font-size: 13px;
}
.footer nav ul li {
  display: flex;
  line-height: 1.6em;
  max-width: 260px;
  white-space: nowrap;
  overflow: hidden;
  text-overflow: ellipsis;
  color: #fff;
  font-size: 13px;
}
.footer nav ul li a {
  display: block;
  font-size: 13px;
}
</style>
