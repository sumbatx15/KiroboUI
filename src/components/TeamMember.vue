<template>
  <div class="team-member-card">
    <div class="team-member-img">
      <div class="team-member-img-container">
        <img class="member-img" :src="img" alt="">
      </div>
      <div class="team-member-img-overlay">
        <span class="team-member-name">{{name.split(' ')[0]}}</span>
        <span class="team-member-name">{{name.split(' ')[1]}}</span>
        <span class="team-member-job">{{job}}</span>
      </div>
      <a :href="linkedin" target="_blank">
        <img class="linkedin-icon" :src="require('@/assets/linkedin.png')" width="40" alt="">
      </a>
    </div>
    <div class="team-member-desc">
      <span>{{desc}}</span>
    </div>
  </div>
</template>

<script>
export default {
  props: ["name", "img", "job", "desc", "linkedin"]
};
</script>

<style>
.team-member-card {
  width: 14.0625vw;
  display: flex;
  flex-flow: column;
}
.linkedin-icon {
  position: absolute;
  right: 0;
  bottom: 0;
  margin: 10px;
}
.team-member-desc {
  margin-top: 15px;
  font-weight: 100;
  font-size: 1.1vw;
}
.team-member-img {
  position: relative;
}
.team-member-img-container {
  overflow: hidden;
  height: 17.083333333333336vw;
  width: 100%;
}
.member-img {
  max-width: 120%;
  max-height: 120%;
}

.team-member-img-overlay {
  margin: 1.1vw;
  width: 7.8125vw;
  color: white;
  display: flex;
  flex-flow: column;
  position: absolute;
  bottom: 0;
  left: 0;
  text-shadow: 0 0 10px black;
}
.team-member-name {
  font-size: 1.5vw;
  font-weight: bold;
  line-height: 1em;
}
.team-member-job {
  margin-top: 10px;
  font-size: 1.2vw;
  line-height: 1em;

}
.linkedin-icon{
  width: 2.5vw;
  height: 2.5vw;
}
.linkedin-icon:hover {
  transform: scale(1.1);
}

@media screen and (max-width: 1000px) {
  .team-member-card {
    width: 270px;
    display: flex;
    flex-flow: column;
  }
  .linkedin-icon {
    position: absolute;
    right: 0;
    bottom: 0;
    margin: 10px;
  }
  .team-member-desc {
    margin-top: 15px;
    font-weight: 100;
    font-size: 20px;
  }
  .team-member-img {
    position: relative;
  }
  .team-member-img-container {
    overflow: hidden;
    height: 328px;
    width: 100%;
  }
  .member-img {
    max-width: 120%;
    max-height: 120%;
  }

  .team-member-img-overlay {
    margin: 21px;
    width: 150px;
    color: white;
    display: flex;
    flex-flow: column;
    position: absolute;
    bottom: 0;
    left: 0;
    text-shadow: 0 0 10px black;
  }
  .team-member-name {
    font-size: 34px;
    font-weight: bold;
    line-height: 1em;
  }
  .team-member-job {
    font-size: 20px;
  }
  .linkedin-icon:hover {
    transform: scale(1.1);
  }
}
</style>
