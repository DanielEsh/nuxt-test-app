<template>
    <header>
        <div :class="$style.header__logo">
          <nuxt-link to="/" :class="$style.logo">
            <img :class="$style.logoImg" src="@/static/img/header-logo.svg" alt="logo" />
            <img :class="$style.logoImgMob" src="@/static/img/header-logo-mob.svg" alt="logo" />
          </nuxt-link>
          <span :class="$style.promoText">World's first affordable airsharing</span>
        </div>
      
        <div :class="$style.right">
          <a :class="$style.nightContainer" href="#" @click.prevent="setDarkMode()">
            <i :class="$style.nightModeIcon" class="nightModeIcon"></i>
            <span :class="$style.nightMode" v-if="this.$store.state.vehicles.isNightMode">Day mod</span>
            <span :class="$style.nightMode" v-else>Night mod</span>
          </a>
        
          <div :class="$style.buttons">
            <a href="#" :class="$style.questions"></a>
            <a href="#" :class="$style.bell"></a>
          </div>
        
          <a href="#" :class="$style.profile">
            <span :class="$style.name">Bessie Cooper</span>
            <img
              src="@/static/img/avatar.png"
              :class="$style.avatar"
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
  .header__logo {
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
  
  .promoText {
    display: block;
    font-weight: 300;
    font-size: 16px;
    line-height: 24px;
    color: var(--light-text);
  }
  
  .dark .promoText {
    color: var(--night-text);
  }
  
  .nightContainer {
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
  
  .buttons {
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
  
  .bell {
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
  
  .name {
    display: block;
    font-weight: bold;
    color: var(--night);
  }
  
  .dark .name {
    color:var(--white);
  }
  
  .avatar {
    margin-left: 16px;
    border-radius: 50%;
  }
  
  @media (max-width: 1200px) {
    .logo {
      margin-right: 25px;
    }
    
    .buttons {
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
    
    .name {
      display: none;
    }
  }
  
  @media (max-width: 880px) {
    .buttons {
      margin-left: 30px;
    }
  }
  
  @media (max-width: 760px) {
    .promoText {
      display: none;
    }
  }
  
  @media (max-width: 520px) {
    .header {
      margin: 48px 0 20px 0;
    }
    
    .logo {
      margin-right: 0;
    }
    
    .logoImg {
      display: none;
    }
    
    .logoImgMob {
      display: block;
    }
    
    .bell {
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
    
    .buttons {
      margin-left: 18px;
    }
    
    .profile {
      margin-left: 18px;
    }
    
    .name {
      margin-left: 0;
    }
    
    .avatar {
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
