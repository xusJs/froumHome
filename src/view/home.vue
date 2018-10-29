<template>
  <div class="view">
    <header class="header">
      <div class="container">
        <div class="logo">
          <a href="javascript:void (0)">
            <img src="../assets/logo.png" alt="">
          </a>
        </div>
        <ul class="header_list">
          <li class="header_item">
            <a href="https://github.com/intervalue" target="_blank">
              GitHub
            </a>
          </li>
          <li class="header_item">
            <a href="https://github.com/intervalue" target="_blank">
              技术文档
            </a>
          </li>
          <li class="header_item">
            <a href="https://github.com/intervalue" target="_blank">
              开发论坛
            </a>
          </li>
          <!--    <li class="header_item">
                <el-dropdown>
                  <span class="el-dropdown-link">
                    下拉选项<i class="el-icon-arrow-down el-icon&#45;&#45;right"></i>
                  </span>
                  <el-dropdown-menu slot="dropdown">
                    <el-dropdown-item>下拉1</el-dropdown-item>
                    <el-dropdown-item>下拉2</el-dropdown-item>
                    <el-dropdown-item>下拉3</el-dropdown-item>
                    <el-dropdown-item>下拉4</el-dropdown-item>
                  </el-dropdown-menu>
                </el-dropdown>
              </li>-->
        </ul>
      </div>
    </header>
    <div class="box">
      <!--   <div class="title">
           <div class="container">
             <h4>开发者中心</h4>
             &lt;!&ndash;<h4>hello world</h4>&ndash;&gt;
           </div>
         </div>-->
      <div class="content">
        <div class="container">
          <div class="content_title">
            <!--  <span>
                Events
              </span>-->
            <!--<span></span>-->
          </div>
          <ul class="content_list">
            <li class="content_item" v-for="item in projectList"
                :style="{background: '#a1a2a9 url('+item.bj+') no-repeat 50% 50%'}">
              <!--  <div class="Img">
                  <a href="http://www.baidu.com" target="_blank">
                    <img src="../assets/1.jpg" alt="">
                  </a>
                </div>
                <div class="item_title">
                  title title title title
                </div>
                <div class="item_content">
                  Join us to learn how Firebase helps mobile app teams of all sizes across the entire development
                  lifecycle.
                </div>
                &lt;!&ndash;      <div class="item_more">
                        LEARN MORE
                      </div>&ndash;&gt;
                <div></div>-->
              <h4 class="item_title" :style="{color:item.color,}">{{item.name}}</h4>
              <a :href="item.url" target="_blank">
                <div class="item_box"
                     :style="{border:' 2px solid'+item.color,color:item.color}"
                     @mouseover="item.color = '#e4e4e4' "
                     @mouseout="hoverOut(item)"
                >
                  访问链接
                </div>
              </a>
            </li>
          </ul>
        </div>
      </div>
      <footer class="footer">
        <div class="footer_content">
          <div class="container">
            <div class="footer_share">
              <a v-for="item in footerShareList" :href="item.url" target="_blank" @mouseover="item.isHover = true"
                 @mouseout="item.isHover = false">
                <img :src="item.img" alt="" class="share_img">
                <img :src="item.imgqr" alt="" :class=" item.isHover ? 'isdef'  :  ''" class="qrcode">
              </a>
            </div>
          </div>
        </div>
        <div class="footer_footer">
          <div class="container">
            <!--<div class="footer_logo"></div>-->
            <div class="footer_text">Copyright 2017-2018 inve.one All rights reserved</div>
          </div>
        </div>
      </footer>
    </div>
  </div>
</template>

<script>

  /*  图标*/
  import gitgub from "../assets/g.png"
  import a from "../assets/a.png"
  import t from "../assets/t.png"
  import f from "../assets/f.png"
  import tele from "../assets/telegram.png"
  import wechat from "../assets/wechat.png"
  import biyong from "../assets/biyong.png"
  import qq from "../assets/qq.png"
  import weibo from "../assets/weibo.png"

  /*二维码*/
  import biyongqr from "../assets/biyong2.png"
  import qqqr from "../assets/qq2.png"
  import wechatqr from "../assets/wechat2.jpg"
  import weiboqr from "../assets/weibo2.png"
  import teleqr from "../assets/telegram2.jpg"

  /**
   * 背景
   * */
  import bj from "../assets/bj.jpg"


  export default {
    name: "home",
    data() {
      return {
        footerShareList: [
          {
            img: gitgub,
            imgqr: "",
            url: "https://github.com/intervalue",
            isHover: false
          },
          {
            img: a,
            imgqr: "",
            url: "https://www.reddit.com/user/intervalue/",
            isHover: false
          },
          {
            img: t,
            imgqr: "",
            url: "https://twitter.com/intervaluepro",
            isHover: false
          },
          {
            img: f,
            imgqr: "",
            url: "https://www.facebook.com/InterValueofficial/",
            isHover: false
          },
          {
            img: tele,
            imgqr: teleqr,
            url: "javascript:void(0)",
            isHover: false
          },
          {
            img: wechat,
            imgqr: wechatqr,
            url: "javascript:void(0)",
            isHover: false
          },
          {
            img: biyong,
            imgqr: biyongqr,
            url: "javascript:void(0)",
            isHover: false
          },
          {
            img: qq,
            imgqr: qqqr,
            url: "javascript:void(0)",
            isHover: false
          },
          {
            img: weibo,
            imgqr: weiboqr,
            url: "javascript:void(0)",
            isHover: false
          },
        ],
        projectList: [
          {
            name: "GitHub",
            bj: bj,
            url: "https://github.com/intervalue",
            color: "#86e991",
          },
          {
            name: "技术文档",
            bj: bj,
            url: "https://github.com/intervalue",
            color: "#007bff",
          },
          {
            name: "开发论坛",
            bj: bj,
            url: "https://github.com/intervalue",
            color: "#beeb00",
          },
        ]
      }
    },
    methods: {
      hoverOut(item) {
        if (item.name === 'GitHub') {
          item.color = "#86e991"
        } else if (item.name === '技术文档') {
          item.color = "#007bff"
        } else if (item.name === '开发论坛') {
          item.color = "#beeb00"
        }
      }
    }
  }
</script>

<style scoped lang="scss">
  .view {
    display: flex;
    flex-direction: column;
    height: 100%;
    .header {
      border-bottom: 1px solid #ddd;
      .container {
        width: 1140px;
        margin: 0 auto;
        height: 80px;
        display: flex;
        align-items: center;
        .logo {
        }
        .header_list {
          display: flex;
          align-items: center;
          .header_item {
            line-height: 32px;
            margin-left: 40px;
            font-size: 16px;
            padding: 4px;
          }
        }
      }
    }
    .box {
      flex: 1;
      overflow: auto;
      display: flex;
      flex-direction: column;
      /*   .title {
           padding: 40px 0;
           text-align: center;
           box-shadow: 0 0 4px rgba(0, 0, 0, .14), 0 4px 8px rgba(0, 0, 0, .28);
           .container {
             width: 1140px;
             margin: 0 auto;
             h4 {
               margin: 20px 0;
               !*font-size: 24px;*!
               font: 400 44px/52px Microsoft YaHei, sans-serif;
               letter-spacing: 8px;
             }
           }
         }*/
      .content {
        min-height: 900px;
        background: #efefef;
        flex: 1;
        .content_title {
          display: flex;
          margin-bottom: 30px;
          padding-left: 30px;
          padding-top: 20px;
          span {
            flex: 1;
            font-size: 24px;
          }
        }
        .content_list {
          display: flex;
          flex-wrap: wrap;
          align-items: end;
          .content_item {
            width: 50%;
            margin: 10px;
            flex: 1;
            box-shadow: 0 0 4px rgba(0, 0, 0, .14), 0 4px 8px rgba(0, 0, 0, .28);
            /*  .Img {
                img {
                  vertical-align: middle;
                  width: 100%;
                  height: 366px;
                }
              }
              .item_title {
                color: cornflowerblue;
                font-size: 22px;
                margin: 10px 0;
                padding-left: 20px;
              }
              .item_content {
                padding: 16px;
                line-height: 28px;
              }
              .item_more {
              }*/

            padding: 50px 40px;
            text-align: center;
            background: #a1a2a9 url("../assets/bj.jpg") no-repeat 50% 50%;

            .item_title {
              margin-top: 80px;
              font-size: 48px;
              height: 64px;
              line-height: 64px;
              /*color: #86e991;*/
            }
            .item_box {
              display: inline-block;
              /*border: 2px solid #86e991;*/
              margin: 50px 0;
              line-height: 40px;
              font-size: 24px;
              width: 300px;
              /*color: #86e991;*/
            }
          }
          .github {
          }
          .word {
          }
          .forum {
          }
        }
      }
      .footer {
        .footer_content {
          text-align: center;
          padding: 60px 0;
          background: #2c2c2c;
          .container {
            .footer_share {
              a {
                position: relative;
                margin: 0 10px;
                /*background: #ddd;*/
                height: 40px;
                display: inline-block;
                .share_img {
                  width: 40px;
                  height: 40px;
                  border-radius: 50%;
                  /*background: #8c939d;*/
                }
                .qrcode {
                  position: absolute;
                  left: -120px;
                  bottom: -120px;
                  width: 120px;
                  height: 120px;
                  display: none;
                }
                .isdef {
                  display: block !important;
                }
              }
            }
          }
        }
        .footer_footer {
          padding: 20px 0;
          background: #1a1b1d;
          color: #8c939d;
          text-align: center;
          .container {
            display: flex;
            align-items: center;
            .footer_logo {
              width: 40px;
              height: 40px;
              background: url("../assets/logos.png") left center/auto 100% no-repeat;
              margin-right: 30px;
            }
            .footer_text {
              flex: 1;
              font-size: 14px;
            }
          }

        }
      }
    }
  }

  .container {
    width: 1140px;
    margin: 0 auto;
  }
</style>
