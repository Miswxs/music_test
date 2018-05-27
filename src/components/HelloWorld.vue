<template>
  <div class="container">
    {{msg}}
    <!--专辑展示模块-->
    <div class="album-cover-wrapper">
      <div class="album-cover"></div>
    </div>
    <!--控制面板-->
    <div class="control-panel">
      <div class="song-info">
        <h1 class="song-title"></h1>
        <p class="singer"></p>
      </div>
      <div class="sub-control-bar">
        <div class="sub-control-wrapper">
          <div class="time-volume-wrapper">
              <span class="time-info">
                <i class="current-time"></i>
                <i class="total-time"></i>
              </span>
              <span class="volume-btn">
                <i id="icon-yinliang" class="icon iconfont icon-yinliang"></i>
                <div class="volume-bar-wrapper">
                  <div class="volume-bar"></div>
                </div>
              </span>
          </div>
          <div class="sub-function-wrapper">
            <span>
              <i class="icon iconfont icon-ci"></i>
            </span>
            <span>
              <i class="icon iconfont icon-xiazai"></i>
            </span>
            <span>
              <i class="icon iconfont icon-jiahao"></i>
            </span>
            <span>
              <i class="icon iconfont icon-fenxiang"></i>
            </span>
          </div>
        </div>
        <div id="progress-bar">
          <div class="past-progress-bar"></div>
        </div>
        <div class="audio-wrapper">
          <audio src="" autoplay="autoplay" preload="metadata"></audio>
        </div>
      </div>
      <div class="main-control-wrapper">
        <div class="like-discard-wrapper">
          <i id="icon-aixin" class="icon iconfont icon-aixin">
            <span class="like-icon">
              <div class="heart-animation-1"></div>
              <div class="heart-animation-2"></div>
            </span>
          </i>
          <i id="icon-laji2" class="icon iconfont icon-laji2"></i>
        </div>
        <div class="play-control-wrapper">
          <i id="icon-play-and-pause" class="icon iconfont icon-icon-play"></i>
          <i id="icon-next" class="icon iconfont icon-icon-next"></i>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'HelloWorld',
  data () {
    return {
      msg: '欢迎来到网易云音乐'
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
  /*主界面：定义边框大小*/
.container{
  width: 92%;
  height: 100%;
  margin: 0 auto;
  padding: 0 4%;
}
  /*图片转动样式*/
  .album-cover-wrapper{
    display: flex;
    justify-content: center;
    padding: 2.5% 0;
    overflow: hidden;
  }
  .album-cover{
    width: 298px;
    height: 298px;
  }
  .control-panel{
    width: 100%;
  }
  .song-info{
    text-align: center;
    margin: 10px 0;
  }
  .song-title{
    font-size: 24px;
    line-height: 28px;
  }
  .singer{
    font-size: 14px;
    line-height: 18px;
  }
  .sub-control-bar{
    color: #929292;
    user-select: none;
  }
  .sub-control-wrapper{
    display: flex;
    flex-direction: column;
    align-items: center;
  }
  .time-volume-wrapper,.sub-function-wrapper{
    margin-bottom: 20px;
    width:50%;
    display: flex;
    justify-content: space-around;
  }
  .time-volume-wrapper i{
    font-style: normal;
  }
  .volume-btn{
    position: relative;
  }
  .icon{
    cursor: pointer;
  }
  .iconfont{
    font-family: "Adobe Arabic"!important;
    font-size: 16px;
    -webkit-font-smoothing: antialiased;
  }
  .volume-bar-wrapper {
    cursor: pointer;
    opacity: 0;
    position: absolute;
    top: 5px;
    left: 24px;
    width: 0;
    height:5px;
    background-color: #929292;
    transition: all .2s linear;
  }
  .volume-bar {
    width:0;
    height:100%;
    background-color: #424242;
    transition: all .3s linear;
  }
  #progress-bar {
    cursor: pointer;
    width:100%;
    background-color: #ddd;
    margin: 10px 0;
  }
  #past-progress-bar {
    width:0%;
    height:5px;
    background-color: green;
  }
  .audio-wrapper {
    display: none;
    position: absolute;
    left:-999em;
  }
  .main-control-wrapper {
    margin-top: 8%;
    user-select: none;
    display: flex;
    justify-content: space-between;
  }
  .like-discard-wrapper, .play-control-wrapper {
    display: flex;
    justify-content: space-between;
  }
  .like-icon {
    display: inline-block;
    margin-right: .25em;
    font-size: 1.5rem;
    background: url("../assets/images/heart-colored.svg") no-repeat center;
    background-size: 100%;
    animation: heartUnlike 0.25s cubic-bezier(0.175, 0.885, 0.32, 1.275) both;
  }
  .like-icon {
    position: absolute;
    top: 5px;
    left: 0;
  }

  .icon-jiahao:before { content: "\3466"; }

  .icon-xiazai:before { content: "\e62a"; }

  .icon-fenxiang:before { content: "\e618"; }

  .icon-ci:before { content: "\e637"; }

  .icon-aixin:before { content: "\e614"; }

  .icon-yinliang:before { content: "\e62f"; }

  .icon-laji2:before { content: "\e651"; }

  .icon-icon-pause:before { content: "\e62c"; }

  .icon-icon-play:before { content: "\e62d"; }

  .icon-icon-next:before { content: "\e62e"; }
</style>
