<template>
    <div class="container">
        <div class="tab">
            <button v-for="(tab, index) in tabs" :class="[`tab-item-${index}`, { 'active': activeTab === index }]"
                :key="index" @click="activeTab = index">
                {{ tab.name }}
            </button>
        </div>
        <div class="tab-content">
            <component :is="tabs[activeTab].component"></component>
        </div>
    </div>
</template>
  
<script>
import QuoteTab from './QuoteTab.vue';
import AlarmTab from './AlarmTab.vue';

export default {
    data() {
        return {
            tabs: [
                { name: '시세', component: QuoteTab },
                { name: '알림', component: AlarmTab },
            ],
            activeTab: 0
        };
    },

    components: {
        QuoteTab,
        AlarmTab,
    }
};
</script>
  
<style scoped>
.container {
    min-height: 100vh;
    padding: 20px;
    background: #fff;
    padding-top: 30px;
}

.tab {
    display: flex;
}

.tab button {
    border: none;
    background-color: transparent;
    cursor: pointer;
    color: #abb2c0;
    padding: 0;
    font-size: 24px;
    padding-bottom: 12px;
    border-bottom: 3px solid transparent;
    margin-left: 32px;
    font-weight: 900;
}

.tab .tab-item-0 {
    margin-left: 0;
}

.tab .active {
    color: #232a72;
    border-bottom: 3px solid #232a72;
}

.tab-content div {
    min-height: 100vh;
    margin-top: 20px;
}

.tab-content div.show {
    display: block;
}
</style>
  