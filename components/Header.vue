<template>
    <header :class="{ [$style.dark]: this.$store.state.vehicles.isNightMode }">
        <div :class="$style.headerLogo">
          <nuxt-link to="/" :class="$style.logo">
            <img :class="$style.logoImg" src="@/static/img/header-logo-dark.svg" v-if="this.$store.state.vehicles.isNightMode" alt="logo" />
            <img :class="$style.logoImg" src="@/static/img/header-logo.svg" v-else alt="logo" />
            <img :class="$style.logoImgMob" src="@/static/img/header-logo-mob-dark.svg" v-if="this.$store.state.vehicles.isNightMode"alt="logo" />
            <img :class="$style.logoImgMob" src="@/static/img/header-logo-mob.svg"  v-else alt="logo" />
          </nuxt-link>
          <span :class="$style.logoText">World's first affordable airsharing</span>
        </div>
      
        <div :class="$style.right">
          <a :class="$style.nightModeContainer" href="#" @click.prevent="setDarkMode()">
            <i :class="$style.nightModeIcon" class="nightModeIcon"></i>
            <span :class="$style.nightMode" v-if="this.$store.state.vehicles.isNightMode">Day mod</span>
            <span :class="$style.nightMode" v-else>Night mod</span>
          </a>
        
          <div :class="$style.utils">
            <a href="#" :class="$style.questions"></a>
            <a href="#" :class="$style.notifications"></a>
          </div>
        
          <a href="#" :class="$style.profile">
            <span :class="$style.profileUserName">Bessie Cooper</span>
            <img
              src="@/static/img/avatar.png"
              :class="$style.profileImg"
              alt="avatar"
            />
          </a>
        </div>
    </header>
</template>

<script>
  export default {
    methods: {
      setDarkMode() {
        console.log('setDarkMode()')
        this.$store.commit("vehicles/setNightMode");

        if (this.$store.state.vehicles.isNightMode) {
          document.body.style.backgroundColor = "var(--night)";
        } else {
          document.body.style.backgroundColor = "#ffffff";
        }
      }
    }
  };
</script>

<style module>
  
  header {
    display: flex;
    justify-content: space-between;
    align-items: center;
    margin: 0px 0 40px 0;
    padding-top: 48px;
  }
  .headerLogo {
    display: flex;
    align-items: center;
  }
  
  .right {
    display: flex;
    align-items: center;
  }
  
  .logo {
    margin-right: 65px;
    cursor: pointer;
    user-select: none;
  }
  
  .logoImgMob {
    display: none;
  }
  
  .logoText {
    display: block;
    font-weight: 300;
    font-size: 16px;
    line-height: 24px;
    color: var(--light-text);
  }
  
  .dark .logoText {
    color: var(--night-text);
  }
  
  .nightModeContainer {
    display: flex;
    align-items: center;
    user-select: none;
  }
  
  .nightMode {
    position: relative;
    display: block;
    margin-left: 20px;
    font-weight: 300;
    color: var(--light-text);
    transition: .2s ease;
  }
  
  .nightMode:hover {
    color: var(--night-darken);
  }
  
  .dark .nightMode:hover {
    color: #fff;
  }
  
  .nightModeIcon {
    display: block;
    width: 24px;
    height: 24px;
    background: url("~static/img/ic-night-mode.svg");
  }
  
  .dark .nightModeIcon {
    width: 22px;
    height: 22px;
    background: url("~static/img/ic-light.svg");
  }
  
  .utils {
    display: flex;
    margin-right: 59px;
    margin-left: 97px;
  }
  
  .questions {
    display: block;
    width: 24px;
    height: 24px;
    background: url("~static/img/ic-questions.svg");
  }
  
  .notifications {
    display: block;
    width: 24px;
    height: 24px;
    margin-left: 30px;
    background: url("~static/img/ic-bell.svg");
  }
  
  .profile {
    display: flex;
    align-items: center;
    user-select: none;
  }
  
  .profileUserName {
    display: block;
    font-weight: bold;
    color: var(--night);
  }
  
  .dark .profileUserName {
    color:var(--white);
  }
  
  .profileImg {
    margin-left: 16px;
    border-radius: 50%;
  }
  
  @media (max-width: 1200px) {
    .logo {
      margin-right: 25px;
    }
    
    .utils {
      margin-left: 50px;
    }
  }
  
  @media (max-width: 1000px) {
    .nightMode {
      display: none;
    }
    
    .profile {
      margin-left: 40px;
    }
    
    .profileUserName {
      display: none;
    }
  }
  
  @media (max-width: 880px) {
    .utils {
      margin-left: 30px;
    }
  }
  
  @media (max-width: 760px) {
    .logoText {
      display: none;
    }
  }
  
  @media (max-width: 520px) {
    .header {
      margin: 48px 0 20px 0;
    }
    
    .logoText {
      margin-right: 0;
    }
    
    .logoImg {
      display: none;
    }
    
    .logoImgMob {
      display: block;
    }
    
    .notifications {
      width: 20px;
      height: 20px;
      margin-left: 18px;
    }
    
    .questions {
      width: 20px;
      height: 20px;
    }
    
    .nightModeIcon {
      width: 20px;
      height: 20px;
    }
    
    .utils {
      margin-left: 18px;
    }
    
    .profile {
      margin-left: -18px;
    }
    
    .profileUserName {
      margin-left: 0;
    }
    
    .profileImg {
      width: 32px;
      height: 32px;
    }
  }
  
  @media (max-width: 340px) {
    .profile {
      margin-left: 0px;
    }
  }

</style>
