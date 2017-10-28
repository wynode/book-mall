<template>
    <div>
      <nav-header></nav-header>
      <div class="container">
        <div class="page-title-normal">
          <h2 class="page-title-h2"><span>check out</span></h2>
        </div>
        <!-- 进度条 -->
        <div class="check-step">
          <ul>
            <li class="cur"><span>地址</span> 确认</li>
            <li class="cur"><span>订单</span> 确认</li>
            <li class="cur"><span>支付</span> </li>
            <li class="cur"><span>订单</span> 成功</li>
          </ul>
        </div>

        <div class="order-create">
          <div class="order-create-pic"><img src="/static/ok-2.png" alt=""></div>
          <div class="order-create-main">
            <h3>恭喜! <br>你的订单正在配送中!</h3>
            <p>
              <span>订单编号: {{orderId}}</span>
              <span>支付总额：{{orderTotal | currency('￥')}}</span>
            </p>
            <div class="order-create-btn-wrap">
              <div class="btn-l-wrap">
                <router-link class="btn btn--m" to="/cart">返回购物车</router-link>
              </div>
              <div class="btn-r-wrap">
                <router-link class="btn btn--m" to="/">继续购物</router-link>
              </div>
            </div>
          </div>
        </div>
      </div>
      <nav-footer></nav-footer>
    </div>
</template>
<script>
    import NavHeader from './../components/NavHeader.vue'
    import NavFooter from './../components/NavFooter.vue'
    import NavBread from './../components/NavBread.vue'
    import axios from 'axios'
    import {currency} from './../util/currency' 
    export default{
        data(){
            return{
              orderId:'',
              orderTotal: 0
            }
        },
        components:{
          NavHeader,
          NavFooter
        },
        filters:{
          currency:currency
        },
        mounted(){
          var orderId = this.$route.query.orderId;
          console.log("orderId:"+orderId)
          if(!orderId){
            return;
          }
          axios.get("/users/orderDetail",{
            params:{
              orderId:orderId
            }
          }).then((response)=>{
            let res = response.data;
            if(res.status == '0'){
              this.orderId = orderId;
              this.orderTotal = res.result.orderTotal;
            }
          })
        }
    }
</script>
