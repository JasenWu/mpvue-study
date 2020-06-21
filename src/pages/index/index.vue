<template>
  <div>
        <mp-button type="primary" size="large" btnClass="mb15"  @click="clickHandle">默认按钮</mp-button>
     

          <view>
              <mpCheckbox :list="checkboxAnimalsList" v-model="valueAnimals" @change="checkboxChange"></mpCheckbox>


          </view>
       <mp-badge>
  <text>详细信息</text>
</mp-badge>

<!-- 默认状态 -->
<mp-rate rateValue=3 @rateClick="rateClick"></mp-rate>

<mp-loading :showLoading="isShowLoading" loadingText="加载中..." :mask="isShowMask"></mp-loading>
<mp-toast :type="toastType" v-model="showToast" :content="content" :duration="duration"></mp-toast>
<mp-actionsheet ref="actionsheet" :itemList="itemList" @confirm="confirm" @cancel="cancel"></mp-actionsheet>
<mp-modal ref="mpModal" :title="title" :content="content" :showCancel="true" @confirm="confirm" @cancel="cancel"></mp-modal>
  
  <mp-navbar :tabs="tabs" activeIndex=0 @tabClick="tabClick"></mp-navbar>

  <mp-searchbar :isFocus=true :inputValue="inputValue" :placeholder="placeholder" @input="input" @blur="blur" @focus="focus" @confirm="confirm"></mp-searchbar>

  </div>
</template>

<script>
import mpSearchbar from 'mpvue-weui/src/searchbar';
import mpNavbar from 'mpvue-weui/src/navbar';
import mpModal from 'mpvue-weui/src/modal';
import mpActionsheet from 'mpvue-weui/src/actionsheet';
import mpLoading from 'mpvue-weui/src/loading';
import mpRate from "mpvue-weui/src/rate";
import card from "@/components/card";
import mpButton from "mpvue-weui/src/button";
import mpSwitch from "mpvue-weui/src/switch";
import mpGrid from "mpvue-weui/src/grid";
import mpUploader from "mpvue-weui/src/uploader";
import mpCheckbox from "mpvue-weui/src/checkbox";
import mpBadge from "mpvue-weui/src/badge";
import mpToast from 'mpvue-weui/src/toast';
import mpPicker from 'mpvue-weui/src/picker';
export default {
  data() {
    return {
      mode: 'multiLinkageSelector',
      pickerValueArray: [
        {
          label: '飞机票',
          value: 100,
          children: [
            {
              label: '经济舱',
              value: 101
            },
            {
              label: '商务舱',
              value: 102
            }
          ]
        },
        {
          label: '火车票',
          value: 200,
          children: [
            {
              label: '卧铺',
              value: 210
            },
            {
              label: '坐票',
              value: 202
            },
            {
              label: '站票',
              value: 203
            }
          ]
        },
        {
          label: '汽车票',
          value: 300,
          children: [
            {
              label: '快班',
              value: 301
            },
            {
              label: '普通',
              value: 302
            }
          ]
        }
      ],
      tabs:["Hello miniprograme","Hello miniprograme"],
      pickerValueDefault: [1, 0],
      toastType:"warn",
      title:"warn",
      inputValue:"warn",
      placeholder:"warn",
      content:"success",
      duration:3000,
      isShowLoading:false,
      switchValue: false,
      showToast: false,
      motto: "Hello miniprograme",
      itemList:["Hello miniprograme","Hello miniprograme"],
      checkboxAnimalsList: [
        { value: "cat" },
        { value: "dog" },
        { value: "rabbit", disabled: true }
      ],
      valueAnimals: ["dog"],

      gridData: [
        {
          src: "/static/images/user.png",
          name: "Button",
          url: "pages/logs/main"
        },
        {
          src: "/static/images/user.png",
          name: "Cell",
          url: "pages/logs/main"
        }
      ],

      userInfo: {
        nickName: "mpvue",
        avatarUrl: "http://mpvue.com/assets/logo.png"
      }
    };
  },

  components: {
    mpSearchbar,
    mpNavbar,
     mpModal,
     mpActionsheet,
     mpPicker,
    mpToast,
    mpLoading,
    mpCheckbox,
    mpGrid,
    mpSwitch,
    card,
    mpButton,
    mpUploader,
    mpBadge,
    mpRate
  },

  methods: {
    showMulLinkageTwoPicker() {
      this.$refs.mpPicker.show();
    },
    confirm(e) {
      console.log(e);
    },
    cancel(e) {
      console.log(e);
    },
    onCancel(e) {
      console.log(e);
    },
    rateClick() {},
    input() {},
    blur() {},
    focus() {},
 
    activeIndex() {},
    showMulLinkageTwoPicker() {},
    upLoadFail() {},
    uploadDelete() {},
    switchChange(e) {
      console.log("er", e);
    },
    checkboxChange(e) {
      console.log("er", e);
    },
    bindViewTap() {
      const url = "../logs/main";
      if (mpvuePlatform === "wx") {
        mpvue.switchTab({ url });
      } else {
        mpvue.navigateTo({ url });
      }
    },
    clickHandle(ev) {
      console.log("clickHandle:", ev);
      // throw {message: 'custom test'}
    }
  },

  created() {
    // let app = getApp()
  },
  mounted(){
    //this.$refs.actionsheet.show();
   // this.$refs.mpModal.show();
  }
};
</script>

<style scoped>
.userinfo {
  display: flex;
  flex-direction: column;
  align-items: center;
}

.userinfo-avatar {
  width: 128rpx;
  height: 128rpx;
  margin: 20rpx;
  border-radius: 50%;
}

.userinfo-nickname {
  color: #aaa;
}

.usermotto {
  margin-top: 150px;
}

.form-control {
  display: block;
  padding: 0 12px;
  margin-bottom: 5px;
  border: 1px solid #ccc;
}
.all {
  width: 7.5rem;
  height: 1rem;
  background-color: blue;
}
.all:after {
  display: block;
  content: "";
  clear: both;
}
.left {
  float: left;
  width: 3rem;
  height: 1rem;
  background-color: red;
}

.right {
  float: left;
  width: 4.5rem;
  height: 1rem;
  background-color: green;
}
</style>
