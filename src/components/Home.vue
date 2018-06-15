<template>
  <div class="app-container">
    <div class="home-container column">
      <div class="header flex justify-space-between">
        <img :src="require('@/assets/logo.png')" alt="">
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
      </div>
      <div class="home-content column">
        <span class="protect-text">Protect your crypto funds</span>
        <span class="font23px">For individuals, we offer the ability to protect crypto in the case of loss of seed, robbery, or death of the holder. For corporations and institutions, we offer secure financial.</span>
        <div class="flex">
          <div class="column alignitems-center">
            <div class="button button-join">Join Our Whitelist</div>
            <span class="token-text">token distribution</span>
          </div>
          <img class="telegram" :src="require('@/assets/telegram.png')" alt="">

        </div>
      </div>
    </div>
    <div class="solving-container">

    </div>
  </div>
</template>

<script>
export default {};
</script>

<style>
.app-container {
  padding: 1em;
}
.home-container {
  border-radius: 1em;
  padding: 1em;
  background: #fff;
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
  line-height: 96.41px;
}
.button-join {
  /* Style for "Join Our W" */
  color: #31cbfe;
  font-size: 23px;
  font-weight: 700;
  line-height: 13.79px;
  text-transform: uppercase;
  padding: 23px 67px;
}
.menu {
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
</style>
