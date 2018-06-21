<template>
  <div class="app-container">
    <el-dialog title="Kirobo Explanation" width="95%" :visible.sync="centerDialogVisible">
      <iframe v-if="centerDialogVisible" width="100%" height="480" src="https://www.youtube.com/embed/eJ4YCL-GNGI" frameborder="0" allow="autoplay; encrypted-media" allowfullscreen></iframe>
    </el-dialog>
    <div class="star-bg-container">
      <img class="star" :style="styleStar" :src="require('@/assets/star.png')" alt="">
      <img class="star-bg" :src="require('@/assets/bg.png')" alt="">
    </div>
    <div id="home" class="home-container">
      <svg class="home-bg-svg" width="100%" height="100%">
        <mask id="mask" x="0" y="0" width="100%" height="100%">
          <rect x="0" y="0" width="100%" height="100%" fill="#fff" />
          <image :href="require('@/assets/k.svg')" x="25%" y="10%" height="100%" width="100%" />
        </mask>
        <rect x="0" y="0" width="100%" height="100%" mask="url(#mask)" fill="#fff" />
      </svg>
      <div class="home-header">
        <img class="logo" :src="require('@/assets/logo.png')" alt="">
        <div class="menu">
          <div class="menu-items">
            <a href="#" v-scroll-to="'#home'">
              <span>HOME</span>
            </a>
            <a href="#" v-scroll-to="'#solving'">
              <span>WHAT WE’RE SOLVING?</span>
            </a>
            <a href="#" v-scroll-to="'#usecase'">
              <span>USE CASES</span>
            </a>
            <a href="#" v-scroll-to="'#token'">
              <span>TOKEN SALE</span>
            </a>
            <a href="#" v-scroll-to="'#roadmap'">
              <span>ROADMAP</span>
            </a>
            <a href="#" v-scroll-to="'#team'">
              <span>TEAM</span>
            </a>
            <a href="#" v-scroll-to="'#faq'">
              <span>FAQ</span>
            </a>
            <a href="#" v-scroll-to="'#contact'">
              <span>CONTACT</span>
            </a>
          </div>
        </div>
        <a href="https://goo.gl/ZVWgUz" target="_blank">
          <div class="white-paper-container">
            <div class="button-white-paper">WHITE PAPER</div>
          </div>
        </a>
      </div>
      <div class="home-content">
        <div class="home-content-left-wrapper">
          <div class="home-content-text-container">
            <span class="protect-text">Protect your crypto funds from loss ,no matter the reason.</span>
            <span class="protect-desc">1. For individuals, we offer the ability to protect crypto assets or crypto funds in case of loss of seed, robbery, and even death of the holder. </span>
            <span class="protect-desc" style="margin-bottom: 50px">2. For corporations and institutions, we offer secure financial management, allowing them to transfer capital from corporate and institutional holdings to the wallets of employees and suppliers, and receive one-time or recurring payments from clients</span>
            <div class="flex">
              <div class="column alignitems-center">
                <a href="https://kirobo.io/kyc/" target="_blank">
                  <div class="button-join">Join Our Whitelist</div>
                </a>
                <a href="#" class="token-text" v-scroll-to="'#token-dist'">
                  <span>token distribution ></span>
                </a>
              </div>
              <img class="telegram" :src="require('@/assets/telegram.png')" alt="">
            </div>
          </div>

        </div>
        <!-- <div class="home-content-right-wrapper">
          <img :src="require('@/assets/k.svg')" alt="">
        </div> -->
      </div>
    </div>
    <div id="solving" class="solving-container text-shadow">
      <div class="solving-header">
        <div class="solving-text">
          <span class="solving-title" style="margin-bottom: 20px">Protect your crypto funds</span>
          <span class="text-big">What We’re Solving -
            <span class="text-bold">For individuals</span>
          </span>
          <span class="solving-desc" style="margin-top: 16px;">For individuals, we offer the ability to protect crypto in the case of loss of seed, robbery, or death of the holder.</span>
        </div>
        <div class="solving-video-btn" @click="centerDialogVisible = true">
          <img :src="require('@/assets/play.png')" alt="">
          <div class="solving-video-btn-text">
            <span class="text-uppercase">Watch Video</span>
            <span class="">What and How it work</span>
          </div>
        </div>
      </div>
      <div class="solving-content">
        <div class="solving-indicator">
          <div class="solving-indicator-img-container">
            <img class="solving-indicator-img" :src="require('@/assets/lostseed.png')" alt="">
          </div>
          <span class="text-shadow">Loss of seed</span>
        </div>
        <div class="solving-indicator">
          <div class="solving-indicator-img-container">
            <img class="solving-indicator-img" :src="require('@/assets/robery.png')" alt="">
          </div>
          <span class="text-shadow">Robbery protection</span>
        </div>
        <div class="solving-indicator">
          <div class="solving-indicator-img-container">
            <img class="solving-indicator-img" :src="require('@/assets/secure.png')" alt="">
          </div>

          <span class="text-shadow">Secure large transfer</span>
        </div>
        <div class="solving-indicator">
          <div class="solving-indicator-img-container">
            <img class="solving-indicator-img" :src="require('@/assets/death.png')" alt="">
          </div>
          <span class="text-shadow">Death of the holder</span>
        </div>
      </div>
      <div class="solving-footer">
        <!-- <div class="solving-footer-indicators">
          <div class="solving-indicator">
            <img :src="require('@/assets/lostseed.png')" alt="">
            <span class="text-shadow">One Click Application</span>
          </div>
          <div class="solving-indicator">
            <img :src="require('@/assets/lostseed.png')" alt="">
            <span class="text-shadow">Secured Payment</span>
          </div>
          <div class="solving-indicator">
            <img :src="require('@/assets/lostseed.png')" alt="">
            <span class="text-shadow">Payment Getway</span>
          </div>
          <div class="solving-indicator">
            <img :src="require('@/assets/lostseed.png')" alt="">
            <span class="text-shadow">External Integration</span>
          </div>
          <div class="solving-indicator">
            <img :src="require('@/assets/lostseed.png')" alt="">
            <span class="text-shadow">Fully Secure</span>
          </div>
          <div class="solving-indicator">
            <img :src="require('@/assets/lostseed.png')" alt="">
            <span class="text-shadow">Integration Internal</span>
          </div>
        </div> -->
        <div class="solving-footer-text">
          <div class="solving-text">
            <span class="text-big ">What We’re Solving -
              <span class="text-bold">For Corporations</span>
            </span>
            <span class="solving-desc" style="margin-top: 1em;">Many companies control a lot of crypto, without any reliable means of protection. Kirobo’s smart rules technology prevent embezzlement and mismanagement of cryptofunds.</span>
          </div>
        </div>
      </div>
    </div>
    <div id="usecase" class="use-case-container">
      <carousel :perPage="1" :style="styleMaxWidth">
        <slide>
          <div class="use-case-slide-content">
            <div class="use-case-text">
              <div class="use-case-text-title">Product Use Cases</div>
              <div class="use-case-text-subtitle">Backup Wallets </div>
              <div class="use-case-text-desc">
                Coin Recovery Inheritance Planning
              </div>
            </div>
            <div class="use-case-img-container">
              <div style="position:relative">
                <hot-spot top="60%" left="20%">
                  <div class="hot-spot-desc-container">
                    <span class="hot-spot-title">
                      Set Up a Backup Wallet
                    </span>
                    <span class="hot-spot-desc">
                      The user set a time of inactivity after which a backup is activated
                    </span>
                  </div>
                </hot-spot>
                <hot-spot top="28%" left="16%">
                  <div class="hot-spot-desc-container">
                    <span class="hot-spot-title">
                      The Balance of the User’s Original Wallet
                    </span>
                    <span class="hot-spot-desc">
                      The user can log into the Kirobo platform using – Metamask, Ledger, Trezor
                    </span>
                  </div>
                </hot-spot>
                <hot-spot top="28%" left="84%">
                  <div class="hot-spot-desc-container">
                    <span class="hot-spot-title">
                      Creating a Smart Wallet
                    </span>
                    <span class="hot-spot-desc">
                      The user’s Smart Wallet
                    </span>
                  </div>
                </hot-spot>
                <img class="use-case-img" :src="require('@/assets/2.png')" alt="">
              </div>
            </div>
          </div>
        </slide>
        <slide>
          <div class="use-case-slide-content">
            <div class="use-case-text">
              <div class="use-case-text-title">Product Use Cases</div>
              <div class="use-case-text-subtitle">Rules to Prevent</div>
              <div class="use-case-text-subtitle">Hostile Activities</div>
              <div class="use-case-text-desc">
                Secure Large Transfers Blockchain-Based Two-Step Verification
              </div>
            </div>
            <div class="use-case-img-container">
              <div style="position:relative">
                <hot-spot top="32%" left="85%">
                  <div class="hot-spot-desc-container">
                    <span class="hot-spot-title">
                      Rules to Prevent Hostile Activities
                    </span>
                    <span class="hot-spot-desc">
                      Robbery Protection Secure Large Transfer
                    </span>
                  </div>
                </hot-spot>
                <img class="use-case-img" :src="require('@/assets/2.png')" alt="">
              </div>
            </div>
          </div>
        </slide>
        <slide>
          <div class="use-case-slide-content">
            <div class="use-case-text">
              <div class="use-case-text-title">Product Use Cases</div>
              <div class="use-case-text-subtitle">Secure Financial</div>
              <div class="use-case-text-subtitle">Management for Corporations</div>
              <div class="use-case-text-desc">
                Secure Large Transfers Blockchain-Based Two-Step Verification
              </div>
            </div>
            <div class="use-case-img-container">
              <div style="position:relative">
                <hot-spot top="8%" left="22%">
                  <div class="hot-spot-desc-container">
                    <span class="hot-spot-title">
                      1.The firm creates a central pool contract
                    </span>
                    <span class="hot-spot-desc">
                      The firm defines a waiting period for withdrawing capital from the central pool and into the wallet. Withdrawing capital from the central pool and into the wallet requires digital signatures of a specified number of pre-assigned signatories
                    </span>
                  </div>
                </hot-spot>
                <hot-spot top="13%" left="40%">
                  <div class="hot-spot-desc-container">
                    <span class="hot-spot-title">
                      2. The firm creates a series of smart contracts
                    </span>
                    <span class="hot-spot-desc">
                      When capital is transferred to the central pool, the firm creates a series of smart contracts to match the types of costs the firm incurs. For instance, the firm will create two separate contracts for two separate types of costs. Here, we’re looking at legal costs and employee salaries.
                    </span>
                  </div>
                </hot-spot>
                <hot-spot top="27%" left="82%">
                  <div class="hot-spot-desc-container">
                    <span class="hot-spot-title">
                      3. The smart contract can transfer funds to people who are approved in advance
                    </span>
                    <span class="hot-spot-desc">
                      The firm defines suppliers versus employees, further parsing apart the conditions and limitations of each wallet. For instance, the firm can define a wallet belonging to a specific employee, who we’ll call Sandra. The firm will approve Sandra’s wallet in advance using the relevant smart contract and set it up so she receives her monthly salary worth $5,000 USD with a capped value of $10,000 USD. That way, any attempt to transfer values exceeding $10,000 USD will require additional, predefined authorization.
                    </span>
                  </div>
                </hot-spot>
                <hot-spot top="32%" left="31%">
                  <div class="hot-spot-desc-container">
                    <span class="hot-spot-title">
                      4. Confirmation of unusual actions
                    </span>
                    <span class="hot-spot-desc">
                      That means that when an employee receives their monthly pay slip, the bookkeeper and the finance manager must both authorize that slip through the company’s salary app. If the amount is less the maximum, then the money will be immediately available to the employee.
                    </span>
                    <span class="hot-spot-desc">
                      When that amount exceeds the maximum, the company’s specified conditions come into play. If, in this case, the firm defined a contract to require a CFO signature if the pay slip exceeds the maximum, then the CFO must authorize payments above each employee’s set maximum.
                    </span>
                  </div>
                </hot-spot>
                <img class="use-case-img" :src="require('@/assets/3.png')" alt="">
              </div>
            </div>
          </div>
        </slide>
      </carousel>
      <div class="use-case-shadow"></div>
    </div>
    <div id="token" class="token-sale-container" :style="styleMaxWidth">
      <div class="token-presale-container">
        <div class="token-sale-title">Private sale and Pre Sale only</div>
        <div class="token-sale-desc">The smart contracts for Kirobo’s SmartWallet will be triggered by Operators, who will receive a reward of KBO Tokens in exchange for their services. Token holding: To use Kirobo’s SmartWallet services, the user must hold a minimum required reserve of KBO Tokens. Market forces will determine the minimum quantity required.</div>
        <div class="token-sale-timer" :style="styleMaxWidth">
          <CountDown :date="new Date(2018,7,1)" :style="styleMaxWidth" />
        </div>
        <div class="token-presale-details">
          <div class="token-presale-detail-item">
            <span class="text-bold">Pre Sale Start</span>
            <span class="">August 1, 2018 (9:00AM GMT)</span>
          </div>
          <div class="token-presale-detail-item">
            <span class="text-bold">Token Exchange Rate</span>
            <span class="">1 ETH = 4,850 KBO</span>
          </div>
          <div class="token-presale-detail-item">
            <span class="text-bold">CAP</span>
            <span class="">2,000,000,000 KBO</span>
          </div>
          <div class="token-presale-detail-item">
            <span class="text-bold">Pre-Sale Ends</span>
            <span class="">September 20 2018 , (11:00AM GMT)</span>
          </div>
          <div class="token-presale-detail-item">
            <span class="text-bold">Minimum Transaction Amount</span>
            <span class="">85 ETH</span>
          </div>
          <div class="token-presale-detail-item">
            <span class="text-bold">Number of Tokens for Sale</span>
            <span class="">Up to 800,000,000 KBO (40%)</span>
          </div>
        </div>
        <a href="https://kirobo.io/kyc/" target="_blank">
          <div class="button-join">Join Our Whitelist</div>
        </a>

      </div>
      <div id="token-dist" class="token-distribution-container">
        <span class="token-sale-title">Distribution Of Tokens</span>
        <PieChart />
      </div>
      <div class="token-budget-container">
        <div class="token-sale-title"> Budget Breakdown</div>
        <div class="token-budget-details" :style="maxWidth">
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
    <div id="roadmap" class="road-map-container">
      <span class="token-sale-title">Road map</span>
      <div class="road-map-carousel">
        <YearsSlider @yearChanged="yearChanged" :years="['2016','2017','2018','2019']" :selectedYear="selectedYear" />
        <carousel v-if="selectedYear=='2016'" :perPage="perPage" :style="styleMaxWidth">
          <slide>
            <div class="carousel-slide-content">
              <span class="carousel-slide-title">December</span>
              <span>Formulation of the concept</span>
            </div>
          </slide>
        </carousel>
        <carousel v-if="selectedYear=='2017'" :perPage="perPage" :style="styleMaxWidth">
          <slide>
            <div class="carousel-slide-content">
              <span class="carousel-slide-title">February</span>
              <span>Team formation</span>
            </div>
          </slide>
          <slide>
            <div class="carousel-slide-content">
              <span class="carousel-slide-title">March</span>
              <span>Development begins</span>
            </div>
          </slide>
          <slide>
            <div class="carousel-slide-content">
              <span class="carousel-slide-title">November</span>
              <span>First patent submission</span>
            </div>
          </slide>
          <slide>
            <div class="carousel-slide-content">
              <span class="carousel-slide-title">December</span>
              <span>Submit two additional patents</span>
            </div>
          </slide>
        </carousel>
        <carousel v-if="selectedYear=='2018'" :perPage="perPage" :style="styleMaxWidth">
          <slide>
            <div class="carousel-slide-content">
              <span class="carousel-slide-title">February</span>
              <span>Seed raised $2M</span>
            </div>
          </slide>
          <slide>
            <div class="carousel-slide-content">
              <span class="carousel-slide-title">May</span>
              <span>Private-Sale Starts</span>
            </div>
          </slide>
          <slide>
            <div class="carousel-slide-content">
              <span class="carousel-slide-title">July</span>
              <span>Expansion of the POC Will allow users to experiment on Rinkeby Test Network</span>
            </div>
          </slide>
          <slide>
            <div class="carousel-slide-content">
              <span class="carousel-slide-title">August</span>
              <span>POC revealed</span>
            </div>
          </slide>
          <slide>
            <div class="carousel-slide-content">
              <span class="carousel-slide-title">September</span>
              <span>Private Sale ends and pre-Sale starts</span>
            </div>
          </slide>
          <slide>
            <div class="carousel-slide-content">
              <span class="carousel-slide-title">December </span>
              <span>Alpha release of backup wallets, trusts, inheritance features, and robbery </span>
            </div>
          </slide>
        </carousel>
        <carousel v-if="selectedYear=='2019'" :perPage="perPage" :style="styleMaxWidth">
          <slide>
            <div class="carousel-slide-content">
              <span class="carousel-slide-title">March</span>
              <span>Beta release of backup trusts, inheritance features, and robbery protection</span>
            </div>
          </slide>
          <slide>
            <div class="carousel-slide-content">
              <span class="carousel-slide-title">May</span>
              <span>Production version of backup trusts, inheritance features, a nd robbery </span>
            </div>
          </slide>
          <slide>
            <div class="carousel-slide-content">
              <span class="carousel-slide-title">July</span>
              <span>POC revealed for the corporate platform</span>
            </div>
          </slide>
          <slide>
            <div class="carousel-slide-content">
              <span class="carousel-slide-title">September</span>
              <span>Alpha revealed of corporate platform</span>
            </div>
          </slide>
          <slide>
            <div class="carousel-slide-content">
              <span class="carousel-slide-title">November</span>
              <span>Beta revealed of corporate platform and development of SAP add-on</span>
            </div>
          </slide>
        </carousel>
      </div>
      <div class="use-case-shadow"></div>

    </div>
    <div id="team" class="team-container">
      <span class="team-title">Team</span>
      <div class="team-members-list">
        <TeamMember linkedin="https://www.linkedin.com/in/asafnaim/" :img="require('@/assets/asaf.png')" name="Asaf Naim" job="CEO" desc="CPA-Expert in international taxation, planning and tax structures, transfer prices, and the Encouragement of Capital Investments Law. Owner of technology companies in Israel and the United States." />
        <TeamMember linkedin="https://www.linkedin.com/in/doron-arbely-27049676/" :img="require('@/assets/doron.png')" name="Doron Arbely" job="CRO" desc="Doron spent 26 years working at the Israel Tax Authority (Israel’s equivalent of the IRS) in various management positions In his last position he served as  Commissioner of Internal Revenue (Israeli Tax Authority)" />
        <TeamMember linkedin="https://www.linkedin.com/in/rami-armon-83437835/" :img="require('@/assets/rami.png')" name="Armon Rami" job="CFO" desc="Has extensive experience in the capital market (over 20 years).Formerly, Chief Investment Officer in Menorah Mivtachim Pension. (the largest pension fund in Israel)," />
        <TeamMember linkedin="https://www.linkedin.com/in/tal-asa-aa500513/" :img="require('@/assets/tal.png')" name="Tal Asa" job="CTO" desc="Blockchain expert and software development leader with оvеr 16 уеаrѕ оf hands-on еxреrіеnсе іn building first class innovative products." />
      </div>
      <div class="team-members-list">
        <TeamMember linkedin="" :img="require('@/assets/yehoshua.png')" name="Yehoshua Westover" job="VP Business Development" desc="Angel Investor and Trusted Advisor, Yehoshua is the COO of China-Israel Science & Technology Innovation Center (CISTIC), attending to project selection, overall investor relations, corporate funding, Blockchain innovation." />
        <TeamMember linkedin="https://www.linkedin.com/in/alincooperman/" :img="require('@/assets/alin.png')" name="Alin Cooperman" job="VP Marketing" desc="10 years of business development & fundraising at startups. Founder & CEO of MakeMyPlate, a leading app in Health & Nutrition." />
        <TeamMember linkedin="https://www.linkedin.com/in/sumbat-tadevosian/" :img="require('@/assets/sumbat.png')" name="Sumbat Tadevosian" job="Frontend Developer" desc="Front-end development expert with 5 years of experience in the latest web & mobile technologies such as vue.js and react native" />
        <TeamMember linkedin="https://www.linkedin.com/in/arik-fux-3443a4112/" :img="require('@/assets/arik.png')" name="Arik Fux" job="Mobile Developer" desc="Mobile expert developer with 5 years of experience, Created and managed complex Android projects for a nutrition startup and leading a big applications for companies in the israeli market." />
      </div>
    </div>
    <div id="faq" class="faq-container ">
      <span class="faq-title">FAQ</span>
      <Collapse/>
    </div>
    <div id="contact" class="contact-container">
      <div class="contact-text-container">
        <span class="contact-us-title">Contact us</span>
        <span class="contact-us-desc">Any question? Reach out to us and we’ll get back to you.</span>
      </div>
      <ContactUs />
    </div>
    <div class="app-footer">
      <img :src="require('@/assets/logo-white.png')" alt="">
    </div>
    <img class="footer-bg" :src="require('@/assets/footer-bg.png')" alt="">
  </div>
</template>

<script>
import HotSpot from "./HotSpot";
import ContactUs from "./ContactUs";
import { Carousel, Slide } from "vue-carousel";
import Collapse from "./Collapse";
import TeamMember from "./TeamMember";
import YearsSlider from "./YearsSlider";
import CountDown from "./CircleCountDown/CountDown";
import PieChart from "./PieChart";
export default {
  components: {
    HotSpot,
    ContactUs,
    TeamMember,
    CountDown,
    PieChart,
    YearsSlider,
    Carousel,
    Slide,
    Collapse
  },
  data() {
    return {
      centerDialogVisible: false,
      maxWidth: this.getWidth(),
      selectedYear: "2018",

      starPos: {
        top: 0,
        left: 60,
        width: 50,
        height: 50
      }
    };
  },
  mounted() {
    window.addEventListener("resize", () => {
      console.log("gas");
      this.maxWidth = this.getWidth();
      console.log("this.maxWidth ", this.maxWidth);
    });
    window.addEventListener("scroll", event => {
      event.preventDefault();
      if (pageYOffset >= 900) return;
      this.starPos.top = 0 + pageYOffset * 0.055;
      this.starPos.left = 60 - pageYOffset * 0.071;
      this.starPos.width = 50 + pageYOffset * 0.03;
      this.starPos.height = 50 + pageYOffset * 0.03;
      console.log("styleStar", this.styleStar);
    });
  },
  methods: {
    yearChanged(year) {
      this.selectedYear = year;
    },
    getWidth() {
      return window.innerWidth;
    }
  },
  computed: {
    styleStar() {
      return {
        top: this.starPos.top + "%",
        left: this.starPos.left + "%",
        width: this.starPos.width + "vw",
        height: this.starPos.height + "vw"
      };
    },
    perPage() {
      return parseInt(this.maxWidth / 400) || 1;
    },
    styleMaxWidth() {
      return {
        maxWidth: this.maxWidth + "px"
      };
    }
  }
};
</script>

<style>
.footer-bg {
  position: absolute;
  bottom: 0;
  left: 0;
  z-index: -1;
}
.app-footer {
  display: flex;
  flex-flow: column;
  align-items: center;
  padding: 50px 0;
}
.hot-spot-desc-container {
  display: flex;
  flex-flow: column;
}
.hot-spot-title {
  font-weight: bold;
  margin-bottom: 10px;
}
.hot-spot-desc {
  margin-bottom: 10px;
}
.contact-container {
  border-bottom-left-radius: 1em;
  border-bottom-right-radius: 1em;
  background: #fff;
  position: relative;
  display: flex;
  align-items: center;
  flex-flow: column;
  color: #25215c;
  padding: 100px 20px !important;
}
.contact-text-container {
  display: flex;
  flex-flow: column;
  align-items: center;
}
.contact-us-title {
  font-size: 45px;
}
.contact-us-desc {
  font-size: 23px;
  font-weight: bold;
  margin-bottom: 30px;
}
.text-shadow {
  text-shadow: 0 2px 5px black;
}
.use-case-container {
  box-sizing: border-box;
  border-top-left-radius: 1em;
  border-top-right-radius: 1em;
  background: #fff;
  padding: 6.770833333333334vw;
  position: relative;
  display: flex;
  justify-content: center;
  align-items: center;
}
.use-case-text {
  flex: 1 1 50%;
  max-width: 100%;
}
.use-case-slide-content {
  display: flex;
  padding: 1em;
  margin: 0 auto;
  box-sizing: border-box;
  max-width: 100%;
}
.use-case-text-title {
  font-size: 1.5vw;
  color: #31cafd;
}
.use-case-text-subtitle {
  font-size: 3.5vw;
  line-height: 1em;
}
.use-case-text-desc {
  margin-top: 2em;
  max-width: 540px;
  font-size: 1.3vw;
  line-height: 1.8em;
}
.use-case-shadow {
  position: absolute;
  bottom: 0;
  width: 100%;
  height: 10vw;
  background: linear-gradient(transparent, black);
  opacity: 0.1;
  z-index: 0;
}
.use-case-img-container {
  flex: 1 1 50%;
  align-self: flex-start;
  z-index: 1;
  overflow: hidden;
  border-radius: 10px;
  box-shadow: 0 0 10px rgba(0, 0, 0, 0.137);
}
.use-case-img {
  max-width: 100%;
  max-height: 100%;
}
.faq-container {
  display: flex;
  flex-flow: column;
  align-items: center;
  color: white;
  min-height: 831px;
  background: url("../assets/faq-bg.png");
  background-size: contain;
}
.faq-title {
  font-size: 4em;
  color: white;
  margin-top: 50px;
  margin-bottom: 30px;
}
.road-map-container {
  position: relative;
  display: flex;
  flex-flow: column;
  text-align: center;
  align-items: center;
  justify-content: center;
  background: #fff;
  box-sizing: border-box;
  overflow: hidden;
  height: 800px;
}
.road-map-carousel {
  display: flex;
  align-items: center;
  padding: 20px;
  width: 60%;
}
.VueCarousel {
  flex: 1 1 !important;
}
.carousel-slide-content {
  padding-left: 20px;
  font-size: 1.3vw;
  display: flex;
  flex-flow: column;
  justify-content: flex-start;
  text-align: left;
  align-items: flex-start;
  max-width: 15.625vw;
  min-width: 0px;
}
.carousel-slide-title {
  font-weight: bold;
  color: #47cbff;
}
.token-sale-container {
  padding-top: 3em;
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
  margin-top: 6vw;
  display: flex;
  flex-flow: column;
  align-items: flex-start;
  /* align-self: flex-start; */
  width: 70%;
  font-size: 1.3vw;
  line-height: 50px;
}
.token-distribution-container {
  display: flex;
  flex-flow: column;
  align-items: center;
  justify-content: center;
  padding-bottom: 100px;
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
  width: 100%;
  display: flex;
  justify-content: center;
  margin-top: 91px;
}
.timer-container {
  display: flex;
  width: 100%;
  justify-content: center;
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
  box-sizing: border-box;
  padding: 2em;
  display: flex;
  flex-flow: column;
  text-align: center;
  align-items: center;
  margin-bottom: 10em;
  overflow: hidden;
}
.token-sale-title {
  font-size: 2.604166666666667vw;
  font-weight: bold;
  color: #1f2e71;
  padding: 20px;
}
.token-sale-desc {
  /* Style for "The smart" */
  margin-top: 3vw;
  color: #1f2e71;
  font-size: 1.4375vw;
  width: 33.54166666666667vw;
  padding: 20px;
}
.token-presale-details {
  margin: 110px 0;
  padding: 20px;
  max-width: 90%;
  display: flex;
  flex-flow: row wrap;
  justify-content: space-between;
}
.token-presale-detail-item {
  font-size: 16px;
  flex-basis: 30%;
  display: flex;
  flex-flow: column;
  justify-content: space-between;
  text-align: left;
  margin-bottom: 20px;
}

.app-container {
  padding: 1em;
  position: relative;
  overflow: hidden;
}
.star-bg-container {
  z-index: -1;
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
}
.star {
  z-index: 0;
  position: absolute;
  width: 50vw;
  height: 50vw;
  transition: all 1s !important;
  animation-name: spin;
  animation-duration: 132000ms;
  animation-iteration-count: infinite;
  animation-timing-function: linear;
}
@keyframes spin {
  100% {
    -webkit-transform: rotate(360deg);
    transform: rotate(360deg);
  }
}

.star-bg {
  z-index: -2;
  margin-top: 593px;
  left: 0;
  width: 100%;
}
.app-container * {
  transition: all 200ms;
}
.button-white-paper {
  display: flex;
  justify-content: center;
  align-items: center;
  color: #25215c;
  font-weight: bold;
  font-size: 1vw;
  text-transform: uppercase;
  width: 9.71666666666667vw;
  height: 2.7083333333333335vw;
  border-radius: 100px;
  border: 3px solid #31ccff;
}
.home-container {
  position: relative;
  opacity: 1;
  display: flex;
  flex-flow: column;
  box-sizing: border-box;
  border-radius: 1em;
  padding: 20px;
  padding-bottom: 10vw;
  overflow: hidden;
  /* background: #fff; */
  /* -webkit-mask-clip: url("../assets/k.svg"); */
}
.home-bg-svg {
  position: absolute;
  z-index: -1;
  top: 0;
  left: 0;
}
.home-header {
  display: flex;
  justify-content: space-between;
}
.home-header > img {
  width: 7.266666666666667vw;
  height: 6.25vw;
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
  align-items: flex-start;
  flex: 1 1 50%;
  margin: 0 auto;
}
.home-content-text-container {
  display: flex;
  flex-flow: column;
  max-width: 33.85416666666667vw;
  padding: 20px;
  margin-left: 4vw;
}
.home-content-right-wrapper {
  margin-top: -100px;
  display: flex;
  justify-content: center;
  align-items: center;
  flex: 1 1 50%;
  background: #000;
  width: 32.29166666666667vw;
}
.home-content-right-wrapper > img {
}
.solving-container {
  box-sizing: border-box;
  padding: 20px;
  padding-top: 150px;
  width: 75%;
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
  margin-top: 9vw;
  margin-bottom: 7.5vw;
  display: flex;
  justify-content: flex-end;
}
.solving-footer-indicators {
  display: flex;
  flex-flow: row wrap;
  flex: 1 1 50%;
  margin: 0 auto;
  max-width: 670px;
}
.solving-footer-indicators > * {
  flex: 1 1 30%;
  transform: scale(0.8);
}
.solving-footer-text {
  display: flex;
  justify-content: center;
  align-items: center;
  align-self: flex-end;
}
.solving-video-btn {
  cursor: pointer;
  display: flex;
  align-items: center;
  justify-content: center;
  flex: 1 1 50%;
}
.solving-video-btn-text {
  margin-left: 1em;
  color: #31ccff;
  font-size: 1.9375vw;
  font-weight: bolder;
  display: flex;
  flex-flow: column;
}
.solving-header {
  display: flex;
}
.solving-title {
  font-size: 3.875vw;
  font-weight: lighter;
  max-width: 26.041666666666668vw;
  line-height: 1em;
}
.solving-desc {
  font-size: 1.4375vw;
  font-weight: 100;
  max-width: 675px;
}
.solving-text {
  display: flex;
  flex-flow: column;
  align-self: flex-end;
  flex: 1 1 50%;
  max-width: 32vw;
}
.solving-indicator {
  text-align: center;
  display: flex;
  flex-flow: column;
  font-size: 1.6875vw;
  justify-content: space-between;
  height: 11.6vw;
  width: 11.6vw;
  align-items: center;
}
.solving-indicator-img-container {
  width: 5vw;
  height: 5vw;
}
.solving-indicator-img {
  max-width: 100%;
  max-height: 100%;
}
.telegram {
  align-self: flex-start;
  margin-left: 2.3125vw;
  margin-top: 0.9375vw;
}
.protect-text {
  /* Style for "Protect yo" */
  color: #1f2e71;
  font-size: 3.5vw;
  font-weight: bold;
  line-height: 0.9em;
}
.protect-desc {
  /* Style for "For indivi" */
  max-width: 35vw;
  color: #25215c;
  font-size: 1.4375vw;
  font-weight: 400;
  margin: 2vw 0;
  margin-bottom: 0.2vw;
}
.button-join {
  /* Style for "Join Our W" */
  white-space: nowrap;
  color: #31cbfe;
  font-size: 1.5vw;
  font-weight: 700;
  text-transform: uppercase;
  border: 3px solid #31cbfe;
  border-radius: 100px;
  padding: 1.2vw 5vw;
  transform: all 300ms;
}
.button-join:hover,
.button-white-paper:hover,
.solving-video-btn:hover {
  transform: scale(1.1);
}
.menu {
  margin-top: 30px;
  display: flex;
  flex: 1 1;
  color: #25215c;
  font-weight: bold;
  justify-content: center;
  font-size: 1vw;
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
.text-big {
  font-size: 1.5vw;
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
  color: #1f2e71;
  font-size: 50px;
  margin-bottom: 100px;
  font-weight: bold;
  margin-top: 100px;
}
@media screen and (max-width: 1300px) {
  .token-sale-timer {
    transform: scale(0.7);
  }
}
@media screen and (max-width: 1000px) {
  .use-case-slide-content {
    max-width: 100%;
  }
  .carousel-slide-title {
    font-size: 23px;
  }
  .carousel-slide-content {
    font-size: 1.2em;
    max-width: 300px;
  }
  .home-content-text-container {
    align-items: center;
    padding: 0;
    max-width: none;
  }
  .home-header > img {
    width: auto;
    height: auto;
  }
  .solving-indicator-img-container {
    width: 5em;
    height: 5em;
  }
  .solving-video-btn-text {
    margin-left: 1em;
    color: #31ccff;
    font-size: 25px;
    font-weight: bolder;
    display: flex;
    flex-flow: column;
  }
  .text-big {
    font-size: 20px;
  }
  .solving-indicator {
    text-align: center;
    display: flex;
    flex-flow: column;
    font-size: 1.6875em;
    justify-content: space-between;
    height: 6.6em;
    width: 11.6em;
    align-items: center;
  }
  .token-presale-detail-item {
    align-items: center;
    text-align: center;
  }
  .contact-us-fields {
    flex-flow: column;
  }
  .token-presale-container {
    margin-bottom: 50px;
  }
  .use-case-text-title {
    font-size: 22px;
    color: #31cafd;
  }
  .use-case-text-subtitle {
    font-size: 35px;
    line-height: 1em;
  }
  .use-case-text-desc {
    margin-top: 2em;
    margin-bottom: 2em;
    max-width: 540px;
    line-height: 1.8em;
    font-size: 16px;
  }
  .menu {
    display: none;
  }
  .solving-text {
    align-items: center;
    max-width: none;
  }
  .home-container {
    background: #fff;
    border-radius: 0;
  }
  .app-container {
    padding: 0px;
    font-size: 1em;
  }
  .protect-text {
    font-size: 2.5em;
    margin-bottom: 40px;
  }
  .protect-desc {
    max-width: none;
    line-height: 2em;
    font-size: 16px;
    margin-bottom: 2em;
  }
  .road-map-container {
    padding-top: 40px;
  }
  .years-slider-container {
    margin-bottom: 30px;
  }
  .button-white-paper {
    display: flex;
    justify-content: center;
    align-items: center;
    color: #25215c;
    font-weight: bold;
    font-size: 1em;
    text-transform: uppercase;
    width: 9.71666666666667em;
    height: 2.7083333333333335em;
    border-radius: 100px;
    border: 3px solid #31ccff;
  }
  .button-white-paper {
    transform: scale(0.7);
    position: absolute;
    top: 0;
    right: 0;
  }
  .token-presale-details {
    margin-top: 30px;
  }
  .token-presale-details > * {
    flex: 1 1 100%;
    margin-bottom: 30px;
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
    flex: 1 1 50%;
  }
  .telegram {
    display: none;
  }
  .button-join {
    /* Style for "Join Our W" */
    color: #31cbfe;
    font-size: 1em;
    font-weight: 700;
    text-transform: uppercase;
    border: 3px solid #31cbfe;
    border-radius: 100px;
    padding: 16px 57px;
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
    font-size: 2.5em;
    line-height: 1.1em;
    max-width: none;
  }
  .solving-desc {
    width: auto;
    font-size: 16px;
  }
  .solving-video-btn {
    margin-top: 30px;
    transform: scale(0.8);
    font-size: 0.65vw;
  }
  .solving-content {
    flex-flow: column;
    flex: 1 1;
    width: auto;
    align-items: center;
    overflow: hidden;
    padding: 20px 0;
  }
  .solving-content > * {
    margin-bottom: 120px;
  }
  .solving-content > * {
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
    font-size: 18px;
    width: auto;
  }
  .token-sale-timer {
    margin-top: 20px;
    transform: scale(0.8);
  }
  .token-sale-title {
    font-size: 2em;
  }
  .timer-container > *:not(:last-child) {
    margin-right: 30px;
  }
  .token-budget-img {
    width: auto;
  }
  .token-budget-details {
    font-size: 16px;
    width: 100%;
    margin-top: 2em;
    margin-left: 3em;
  }
  .road-map-carousel {
    flex-flow: column;
    flex: 1 1;
  }
  .team-members-list {
    flex-flow: column;
    align-items: center;
  }
  .use-case-container {
    padding: 20px;
    max-width: 100%;
    box-sizing: border-box;
  }
  .use-case-slide-content {
    flex-flow: column;
  }
  .star-bg {
    opacity: 0.9;
  }
}

@media screen and (max-width: 750px) {
  .token-sale-timer {
    transform: scale(0.3);
  }
}
</style>
