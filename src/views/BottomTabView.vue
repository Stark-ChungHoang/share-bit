
<template>
    <head>
        <!-- Other meta tags, stylesheets, etc. -->
        <link rel="stylesheet" href="https://fonts.googleapis.com/css2?family=Montserrat:wght@400;500;600&display=swap" />
    </head>

    <router-view></router-view>
    <div class="bottom-navigation">
        <router-link to="/" exact class="nav-item" active-class="active">
            <!-- <img :src="isActive('/') ? 'src/assets/images/ic-quotes-on@3x.png' : 'src/assets/images/ic-quotes-off@3x.png'"
                alt="Home" class="icon" /> -->
            시세 · 알림
        </router-link>
        <router-link to="/about" class="nav-item" active-class="active">
            <!-- <img :src="isActive('/about') ? 'src/assets/images/ic-news-on@3x.png' : 'src/assets/images/ic-news-off@3x.png'"
                alt="Home" class="icon" /> -->
            뉴스
        </router-link>
        <router-link to="/test" class="nav-item" active-class="active">
            <!-- <img :src="isActive('/test') ? 'src/assets/images/ic-rankings-on@3x.png' : 'src/assets/images/ic-rankings-off@3x.png'"
                alt="Home" class="icon" /> -->
            랭킹
        </router-link>
        <router-link to="/cc" class="nav-item" active-class="active">
            <!-- <img :src="isActive('/cc') ? 'src/assets/images/ic-discussions-on@3x.png' : 'src/assets/images/ic-discussions-off@3x.png'"
                alt="Home" class="icon" /> -->
            커뮤니티
        </router-link>
        <router-link to="/hehe" class="nav-item" active-class="active">
            <!-- <img :src="isActive('/hehe') ? 'src/assets/images/ic-more-h-on@3x.png' : 'src/assets/images/ic-more-h-off@3x.png'"
                alt="Home" class="icon" /> -->
            마이페이지
        </router-link>
    </div>
</template>
  
<script>
export default {
    
    // Your component configuration
    computed: {
        imageSrc() {
            return new URL(`./assets/images/${selectedItem}.png`, import.meta.url).href;
        }
    },
    methods: {
        isActive(path) {
            console.log("Sfsfsfsfsfsfs");
            return this.$route.path === path;
        }
    }
};
</script>
  
<style>
.container {
    display: flex;
    flex-direction: column;
    min-height: 100vh;
}

.bottom-navigation {
    display: flex;
    justify-content: space-around;
    align-items: center;
    background-color: #fff;
    position: fixed;
    bottom: 0;
    left: 0;
    right: 0;
    border-top: 1px solid #ebecef;
}

.nav-item {
    text-decoration: none;
    color: #cdd1da;
    padding: 10px;
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    font-size: 14px;
    flex-wrap: nowrap;
    font-family: 'Montserrat', sans-serif;
    font-weight: 600;
}

.nav-item.active {
    color: #232a72;
}

.icon {
    width: 24px;
    height: 24px;
    object-fit: contain;
    margin-bottom: 7px;
}</style>
  