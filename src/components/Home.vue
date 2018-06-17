<template>
  <div class="app-container">
    <div class="home-container">
      <div class="home-header">
        <img class="logo" :src="require('@/assets/logo.png')" alt="">
        <div class="menu justify-space-between">
          <span>HOME</span>
          <span>WHAT WE’RE SOLVING?</span>
          <span>USE CASES</span>
          <span>TOKEN SALE </span>
          <span>ROADMAP</span>
          <span>TEAM</span>
          <span>FAQ </span>
          <span>CONTACT</span>
        </div>
        <div class="white-paper-container">
          <div class="button-white-paper">WHITE PAPER</div>
        </div>
      </div>
      <div class="home-content">
        <div class="home-content-left-wrapper">
          <span class="protect-text">Protect your</span>
          <span class="protect-text">crypto funds</span>
          <span class="protect-desc">For individuals, we offer the ability to protect crypto in the case of loss of seed, robbery, or death of the holder. For corporations and institutions, we offer secure financial.</span>
          <div class="flex">
            <div class="column alignitems-center">
              <div class="button-join">Join Our Whitelist</div>
              <span class="token-text">token distribution</span>
            </div>
            <img class="telegram" :src="require('@/assets/telegram.png')" alt="">
          </div>
        </div>
        <div class="home-content-right-wrapper">
          <img :src="require('@/assets/logo-overlay.png')" alt="">
        </div>
      </div>
    </div>
    <div class="solving-container">
      <div class="solving-header">
        <div class="solving-text">
          <span class="text-big">What We’re Solving -
            <span class="text-bold">For individuals</span>
          </span>
          <span class="solving-title">Protect your crypto funds</span>
          <span class="solving-desc" style="margin-top: 2.5em;">For individuals, we offer the ability to protect crypto in the case of loss of seed, robbery, or death of the holder.</span>
        </div>
        <div class="solving-video-btn">
          <img :src="require('@/assets/play.png')" alt="">
          <div class="solving-video-btn-text">
            <span class="text-uppercase">Watch Video</span>
            <span class="">What and How it work</span>
          </div>
        </div>
      </div>
      <div class="solving-content">
        <div class="solving-indicator">
          <img :src="require('@/assets/lostseed.png')" alt="">
          <span class="">Loss of seed</span>
        </div>
        <div class="solving-indicator">
          <img :src="require('@/assets/robery.png')" alt="">
          <span class="">Robbery protection</span>
        </div>
        <div class="solving-indicator">
          <img :src="require('@/assets/secure.png')" alt="">
          <span class="">Secure large transfer</span>
        </div>
        <div class="solving-indicator">
          <img :src="require('@/assets/death.png')" alt="">
          <span class="">Death of the holder</span>
        </div>
      </div>
      <div class="solving-footer">
        <div class="solving-footer-indicators">
          <div class="solving-indicator" v-for="i in 6">
            <img :src="require('@/assets/lostseed.png')" alt="">
            <span class="">Loss of seed</span>
          </div>
        </div>
        <div class="solving-footer-text">
          <div class="solving-text">
            <span class="text-big">What We’re Solving -
              <span class="text-bold">For individuals</span>
            </span>
            <span class="solving-desc" style="margin-top: 1em;">Many companies control a lot of crypto, without any reliable means of protection. Kirobo’s smart rules technology prevent embezzlement and mismanagement of cryptofunds.</span>
          </div>
        </div>
      </div>
    </div>
    <div class="use-case-container">
    </div>
    <div class="token-sale-container">
      <div class="token-presale-container">
        <div class="token-sale-title">Private sale and Pre Sale only</div>
        <div class="token-sale-desc">The smart contracts for Kirobo’s SmartWallet will be triggered by Operators, who will receive a reward of KBO Tokens in exchange for their services.</div>
        <div class="token-sale-timer">
          <CountDown :date="new Date(2018,11,11)" />
        </div>
        <div class="token-presale-details">
          <div class="token-presale-detail-item" v-for="i in 6">
            <span class="text-bold">Pre Sale Start</span>
            <span class="">August 1, 2018 (9:00AM GMT)</span>
          </div>
        </div>
        <div class="button button-join">Join Our Whitelist</div>

      </div>
      <div class="token-distribution-container">
        <span class="token-sale-title">Distribution Of Tokens</span>
        <PieChart />
      </div>
      <div class="token-budget-container">
        <div class="token-sale-title"> Budget Breakdown</div>
        <div class="token-budget-details">
          <span>
            <span class="token-budget-dot" style="color:#142843">●</span> 50% R & D</span>
          <span>
            <span class="token-budget-dot" style="color:#34576a">●</span> 15% Business Development</span>
          <span>
            <span class="token-budget-dot" style="color:#53778a">●</span> 15% PR & Marketing</span>
          <span>
            <span class="token-budget-dot" style="color:#47cbff">●</span> 10% Legal & Accounting</span>
          <span>
            <span class="token-budget-dot" style="color:#87c8e2">●</span> 5% Administrative</span>
          <span>
            <span class="token-budget-dot" style="color:#1f2e71">●</span> 5% Various expenses</span>
        </div>
        <img :src="require('@/assets/waves.png')" alt="" class="token-budget-img">
      </div>
    </div>
    <div class="road-map-container">
      <span class="token-sale-title">Road map</span>
      <div class="road-map-carousel">
        <YearsSlider :years="['2017','2018','2019']" selectedYear="2018" />
        <carousel :perPage="4">
          <slide v-for="i in 5" >
            <div class="carousel-slide-content">
              <span class="carousel-slide-title">May</span>
              <span>Release of the software v.2.0</span>
            </div>
          </slide>
        </carousel>
      </div>
    </div>
    <div class="team-container">
      <span class="team-title">Team</span>
      <div class="team-members-list">
        <TeamMember :img="require('@/assets/asaf.png')" name="Asaf Naim" job="CEO" desc="Many companies control a lot of crypto, without any reliable means of protection. Kirobo’s smart rules technology prevent embezzlement and mismanagement of cryptofunds" />
        <TeamMember :img="require('@/assets/doron.png')" name="Doron Arbely" job="CRO" desc="Many companies control a lot of crypto, without any reliable means of protection. Kirobo’s smart rules technology prevent embezzlement and mismanagement of cryptofunds" />
        <TeamMember :img="require('@/assets/rami.png')" name="Armon Rami" job="CFO" desc="Many companies control a lot of crypto, without any reliable means of protection. Kirobo’s smart rules technology prevent embezzlement and mismanagement of cryptofunds" />
        <TeamMember :img="require('@/assets/tal.png')" name="Tal Asa" job="CTO" desc="Many companies control a lot of crypto, without any reliable means of protection. Kirobo’s smart rules technology prevent embezzlement and mismanagement of cryptofunds" />
      </div>
      <div class="team-members-list">
        <TeamMember :img="require('@/assets/yehoshua.png')" name="Yehoshua Westover" job="VP Business Development" desc="Many companies control a lot of crypto, without any reliable means of protection. Kirobo’s smart rules technology prevent embezzlement and mismanagement of cryptofunds" />
        <TeamMember :img="require('@/assets/alin.png')" name="Alin Cooperman" job="VP Marketing" desc="Many companies control a lot of crypto, without any reliable means of protection. Kirobo’s smart rules technology prevent embezzlement and mismanagement of cryptofunds" />
        <TeamMember :img="require('@/assets/sumbat.png')" name="Sumbat Tadevosian" job="Frontend Developer" desc="Many companies control a lot of crypto, without any reliable means of protection. Kirobo’s smart rules technology prevent embezzlement and mismanagement of cryptofunds" />
        <TeamMember :img="require('@/assets/arik.png')" name="Arik Fux" job="Mobile Developer" desc="Many companies control a lot of crypto, without any reliable means of protection. Kirobo’s smart rules technology prevent embezzlement and mismanagement of cryptofunds" />
      </div>
    </div>
    <div class="faq-container">
    </div>
    <div class="contact-container">
    </div>
  </div>
</template>

<script>
import { Carousel, Slide } from "vue-carousel";
import TeamMember from "./TeamMember";
import YearsSlider from "./YearsSlider";
import CountDown from "./CircleCountDown/CountDown";
import PieChart from "./PieChart";
export default {
  components: {
    TeamMember,
    CountDown,
    PieChart,
    YearsSlider,
    Carousel,
    Slide
  }
};
</script>

<style>
.road-map-container {
  display: flex;
  flex-flow: column;
  text-align: center;
  align-items: center;
  background: #fff;
  box-sizing: border-box;
}
.road-map-carousel {
  display: flex;
  justify-content: center;
  align-items: center;
  padding: 20px;
}
.carousel-slide-content {
  font-size: 23px;
  display: flex;
  flex-flow: column;
  justify-content: flex-start;
  text-align: left;
  align-items: flex-start;
  max-width: 180px;
}
.carousel-slide-title{
  font-weight: bold;
color: #47cbff;
}
.token-sale-container {
  display: flex;
  flex-flow: column;
  text-align: center;
  align-items: center;
  background: #fff;
  box-sizing: border-box;
}
.token-budget-container {
  position: relative;
  display: flex;
  flex-flow: column;
  text-align: center;
  align-items: center;
  background: #fff;
  box-sizing: border-box;
  overflow: hidden;
  padding-bottom: 600px;
  width: 100%;
}
.token-budget-details {
  margin-top: 117px;
  display: flex;
  flex-flow: column;
  align-items: flex-start;
  /* align-self: flex-start; */
  width: 70%;
  font-size: 23px;
  line-height: 50px;
}
.token-distribution-container {
  display: flex;
  flex-flow: column;
  align-items: center;
  justify-content: center;
}
.token-budget-dot {
  font-size: 27px;
}
.token-budget-img {
  position: absolute;
  bottom: 0;
  width: 100%;
}
.token-sale-timer {
  margin-top: 91px;
  overflow: hidden;
  flex: 1 1;
}
.timer-container {
  display: flex;
}
.timer-container > *:not(:last-child) {
  margin-right: 84px;
}
.timer-number {
  font-size: 55px;
  line-height: 0.6em;
}
.timer-number-text {
  font-size: 27px;
}
.token-presale-container {
  padding: 2em;
  display: flex;
  flex-flow: column;
  text-align: center;
  align-items: center;
  margin-bottom: 310px;
  overflow: hidden;
}
.token-sale-title {
  font-size: 5em;
  color: #1f2e71;
}
.token-sale-desc {
  /* Style for "The smart" */
  margin-top: 40px;
  color: #1f2e71;
  font-size: 1.4375em;
  width: 644px;
}
.token-presale-details {
  margin: 110px 0;
  display: flex;
  flex-flow: row wrap;
  justify-content: space-between;
}
.token-presale-detail-item {
  font-size: 16px;
  flex-basis: 30%;
  display: flex;
  align-items: center;
  flex-flow: column;
  text-align: left;
}

.app-container {
  padding: 1em;
}
.app-container * {
  transition: all 300ms;
}
.button-white-paper {
  display: flex;
  justify-content: center;
  align-items: center;
  width: 100px;
  height: 12px;
  color: #25215c;
  font-weight: bold;
  font-size: 1em;
  text-transform: uppercase;
  width: 143px;
  height: 52px;
  border-radius: 100px;
  border: 3px solid #31ccff;
}
.home-container {
  display: flex;
  flex-flow: column;
  box-sizing: border-box;
  border-radius: 1em;
  padding: 1em;
  background: #fff;
}

.home-header {
  display: flex;
  justify-content: space-between;
}
.logo {
  margin: 2.125em;
  width: 128px;
  height: 110px;
}
.home-content {
  display: flex;
}
.home-content-left-wrapper {
  display: flex;
  flex-flow: column;
  padding: 4.875em 5em 10em 10.25em;
  flex: 1 1;
}
.home-content-right-wrapper {
  margin-top: -10em;
  display: flex;
  justify-content: center;
  align-items: center;
  flex: 1 1;
}
.use-case-container {
  box-sizing: border-box;
  border-top-left-radius: 1em;
  border-top-right-radius: 1em;
  padding: 1em;
  background: #fff;
}
.solving-container {
  padding-top: 9.625em;
  width: 70%;
  color: white;
  display: flex;
  margin: 0 auto;
  flex-flow: column;
}
.solving-content {
  display: flex;
  width: 87%;
  justify-content: space-between;
  margin-top: 7em;
}
.solving-footer {
  margin-top: 15em;
  margin-bottom: 7.5em;
  display: flex;
}
.solving-footer-indicators {
  display: flex;
  flex-flow: row wrap;
}
.solving-footer-indicators > * {
  flex: 1 1 30%;
  transform: scale(0.8);
}
.solving-footer-text {
  margin-left: 3em;
  display: flex;
  justify-content: center;
  align-items: center;
  flex: 1 1;
}
.solving-video-btn {
  display: flex;
  flex: 1 1;
  align-items: center;
  justify-content: center;
}
.solving-video-btn-text {
  margin-left: 1em;
  color: #31ccff;
  font-size: 1.9375em;
  font-weight: bolder;
  display: flex;
  flex-flow: column;
}
.solving-header {
  display: flex;
}
.solving-title {
  font-size: 3.875em;
  font-weight: lighter;
}
.solving-desc {
  font-size: 1.4375em;
  font-weight: 100;
  width: 675px;
}
.solving-text {
  display: flex;
  flex-flow: column;
}
.solving-indicator {
  text-align: center;
  display: flex;
  flex-flow: column;
  font-size: 1.6875em;
  justify-content: space-between;
  height: 5.6em;
  align-items: center;
}
.telegram {
  align-self: flex-start;
  margin-left: 2.3125em;
  margin-top: 0.9375em;
}
.protect-text {
  /* Style for "Protect yo" */
  color: #1f2e71;
  font-size: 7.0625em;
  font-weight: bold;
  line-height: 0.9em;
}
.protect-desc {
  /* Style for "For indivi" */
  width: 675px;
  height: 104px;
  color: #25215c;
  font-size: 1.4375em;
  font-weight: 400;
  margin: 2em 0;
  margin-bottom: 4em;
  line-height: 2em;
}
.button-join {
  /* Style for "Join Our W" */
  color: #31cbfe;
  font-size: 1.5em;
  font-weight: 700;
  text-transform: uppercase;
  border: 3px solid #31cbfe;
  border-radius: 100px;
  padding: 23px 67px;
}
.menu {
  flex: 1 1;
  color: #25215c;
  font-weight: bold;
}
.menu * {
  margin-right: 10px;
}
.token-text {
  margin-top: 2em;
  color: #1e293d;
  font-weight: 700;
  text-transform: uppercase;
}
.team-container {
  border-bottom-left-radius: 1em;
  border-bottom-right-radius: 1em;
  padding: 1em;
  background: #fff;
  display: flex;
  flex-flow: column;
  align-items: center;
}
.team-members-list {
  display: flex;
  flex-flow: row wrap;
  justify-content: space-between;
  width: 70%;
}
.team-members-list > * {
  margin-bottom: 40px;
}
.team-title {
  /* Style for "Team" */
  color: #1f2e71;
  font-family: Exo;
  font-size: 5em;
  margin-bottom: 1.5em;
}

@media screen and (max-width: 1080px) {
  .menu {
    display: none;
  }
  .home-container {
    border-radius: 0;
  }
  .app-container {
    padding: 0px;
    font-size: 0.7em;
  }
  .protect-text {
    font-size: 4em;
  }
  .protect-desc {
    width: auto;
  }
  .button-white-paper {
    transform: scale(0.7);
    position: absolute;
    top: 0;
    right: 0;
  }
  .home-content-right-wrapper {
    display: none;
  }
  .home-header {
    margin-top: 20px;
    justify-content: center;
  }
  .home-content-left-wrapper {
    text-align: center;
    justify-content: center;
    align-items: center;
    padding: 10px;
  }
  .telegram {
    display: none;
  }
  .solving-container {
    width: 100%;
    text-align: center;
  }
  .solving-header {
    flex-flow: column;
  }
  .solving-title {
    margin-top: 30px;
    line-height: 0.8em;
  }
  .solving-desc {
    width: auto;
  }
  .solving-video-btn {
    margin-top: 30px;
  }
  .solving-content {
    flex-flow: column;
    flex: 1 1;
    width: auto;
    overflow: hidden;
    padding: 20px 0;
  }
  .solving-content > *:not(:last-child) {
    margin-bottom: 6em;
  }
  .solving-content > * {
    transform: scale(1.2);
  }
  .solving-footer {
    margin-top: 50px;
    padding: 10px;
    text-align: center;
    flex-flow: column;
  }
  .solving-footer-text {
    margin: 0;
    margin-bottom: 30px;
  }
  .solving-footer-indicators {
    order: 1;
  }
  .token-sale-desc {
    width: auto;
  }
  .token-sale-timer {
    transform: scale(0.5);
  }
  .timer-container > *:not(:last-child) {
    margin-right: 10px;
  }
  .token-budget-img {
    width: auto;
    height: 50%;
  }
  .road-map-carousel{
    flex-flow: column;
  }
  .team-members-list{
    flex-flow: column;
    align-items: center;
  }
}
</style>
