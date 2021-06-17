<template>
  <section class="index">
    <div class="hello">
      <i class="iconfont icon-xihuan"></i><span>   您好,{{user.userName}}。</span>
    </div>
    <div class="msg">
      <p class="title">教务公告：</p>
      <ul>
        <li @click="openMsg1()"><i class="iconfont icon-flag"></i>放假通知</li>
        <li @click="openMsg2()"><i class="iconfont icon-flag"></i>下周例行工作报告会</li>
        <li @click="openMsg3()"><i class="iconfont icon-flag"></i>关于毕业生答辩具体流程</li>
      </ul>
    </div>
  </section>
</template>

<script>
export default {
  data() {
    return {
      user: { //用户信息
        userName: null,
        userId: null
      }
    }
  },
  created() {
    this.getUserInfo()
  },
  methods: {
    getUserInfo() { //获取用户信息
      let userName = this.$cookies.get("cname")
      let userId = this.$cookies.get("cid")
      this.user.userName = userName
      this.user.userId = userId
    },
    openMsg1() {
      this.$alert('根据国务院办公厅通知精神，现将2021年端午节放假安排通知如下：6月12日（星期六）至14日（星期一）放假，共3天。请广大市民提前安排好工作生活，节日期间注意安全，减少人员聚集，加强个人防护，度过一个平安、祥和的节日假期。','放假通知',{
        confirmButtonText: '确定'
      })
    },
    openMsg2() {
      this.$alert('下周开会库啵','下周例行工作报告会',{
        confirmButtonText: '确定'
      })
    },
    openMsg3() {
      this.$alert('毕业生答辩全过了','关于毕业生答辩具体流程',{
        confirmButtonText: '确定'
      })
    }
  }
}
</script>


<style lang="scss" scoped>
.index {
  margin-left: 70px;
  .hello {
    font-size: 20px;
    color: #726f70;
    .icon-xihuan {
      font-size: 30px;
      color: #dd6572;
    }
  }
  .msg {
    .title {
      font-size: 16px;
      color: #000;
      margin-top: 20px;
      margin-left: 10px;
    }
    ul {
      display: flex;
      flex-direction: column;
      width: 200px;
      overflow: hidden;
    }
    li {
      margin-top: 10px;
      font-size: 14px;
      color: lightcoral;
      cursor: pointer;
      display: inline-block;
    }
  }
}
</style>

