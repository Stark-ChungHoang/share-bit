
<template>
    <div class="quote-tab">
        <div class="items">
            <div class="category-container">
                <div class="category">
                    <img alt="" class="logo" src="~@/assets/images/icon-01@3x.png" />빗썸 (Bithumb)
                </div>
                <div class="arrow">
                    <img alt="" class="arrow" src="~@/assets/images/ic-drop-down@3x.png" />
                </div>
            </div>
            <div class="line"></div>
            <div class="language">
                KRW
                <div class="arrow">
                    <img alt="" class="arrow" src="~@/assets/images/ic-drop-down@3x.png" />
                </div>
            </div>
        </div>

        <div class="items">
            <div class="input-wrapper">
                <input
                  type="text"
                  class="input-field"
                  :placeholder="placeholder"
                  v-model="inputValue"
                  @input="handleInput"
                />
                <img alt="" class="arrow" src="~@/assets/images/ic-search@3x.png" />
              </div>
        </div>
        <div class="divide"></div>
        <Table />

    </div>
</template>

<script>
import Table from "./Table.vue"
export default {
    data() {
    return {
      inputValue: ''
    };
  },
  props: {
    iconClass: {
      type: String,
      required: true
    },
    placeholder: {
      type: String,
      default: '검색어를 입력하세요.'
    }
  },
  methods: {
    handleInput(event) {
      // Do something with the input value
      console.log('Input value:', event.target.value);
    }
  },
  components: {
    Table
  }
  
};

</script>


<style>



.items {
    margin-top: 10px;
    background: #f8f9fa;
    padding: 16px;
    border: 1px solid #ebecef;
    display: flex;
    align-items: center;
    justify-content: space-between;
    border-radius: 12px;
}

.category-container {
    display: flex;
    align-items: center;
    justify-content: space-between;
    cursor: pointer;
    width: 60%;

}

.category {
    display: flex;
    align-items: center;
    color: #101012;
    font-weight: 600;

}

.logo {
    width: 24px;
    height: 24px;
    margin-right: 5px;
}

.arrow {
    width: 20px;
    height: 20px;
}

.line {
    height: 26px;
    background: #e4e6ec;
    width: 1px;
    margin: 0 20px;
}

.language {
    font-weight: 600;
    display: flex;
    align-items: center;
    color: #101012;
    justify-content: space-between;
    width: 30%;
}
.input-wrapper {
    display: flex;
    justify-content: space-between;
    width: 100%;
    height: 26px;
}
input {
    border: none;
    flex: 1;
    background: transparent
}
input:focus {
    /* Add specific styling for the focused state */
    /* For example, you can remove the outline */
    outline: none;
  }
  .divide {
    height: 12px;
    background: #f5f6f9;
    margin-left: -20px;
    margin-right: -20px;
    margin-top: 20px;
  }
  
</style>