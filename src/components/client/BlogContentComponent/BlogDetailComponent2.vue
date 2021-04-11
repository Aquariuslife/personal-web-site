<template>
<div>
<header-com></header-com>
  <div class="card-container">
    <img id="topImageComtainer" src="../../../assets/BlogImage/BlogTop.jpeg"/>
    <img id="imageComtainer" src="../../../assets/BlogImage/02_01.png"/>
    <img id="imageComtainer" src="../../../assets/BlogImage/02_02.png"/>
    <img id="imageComtainer" src="../../../assets/BlogImage/02_03.png"/>
    <img id="imageComtainer" src="../../../assets/BlogImage/02_04.png"/>
    <img id="imageComtainer" src="../../../assets/BlogImage/02_05.png"/>
    <img id="imageComtainer" src="../../../assets/BlogImage/02_06.png"/>
    <img id="imageComtainer" src="../../../assets/BlogImage/02_07.png"/>
    <img id="imageComtainer" src="../../../assets/BlogImage/02_08.png"/>
    <img id="imageComtainer" src="../../../assets/BlogImage/02_09.png"/>
    <img id="imageComtainer" src="../../../assets/BlogImage/02_10.png"/>
    <img id="imageComtainer" src="../../../assets/BlogImage/02_10.png"/>
    <img id="imageComtainer" src="../../../assets/BlogImage/02_11.png"/>
    <img id="imageComtainer" src="../../../assets/BlogImage/02_12.png"/>
    <img id="imageComtainer" src="../../../assets/BlogImage/02_13.png"/>
    <img id="imageComtainer" src="../../../assets/BlogImage/02_14.png"/>
    <img id="imageComtainer" src="../../../assets/BlogImage/02_15.png"/>
    <img id="imageComtainer" src="../../../assets/BlogImage/02_16.png"/>
    <img id="imageComtainer" src="../../../assets/BlogImage/02_17.png"/>
    <img id="imageComtainer" src="../../../assets/BlogImage/02_18.png"/>
    <img id="imageComtainer" src="../../../assets/BlogImage/02_19.png"/>
    <img id="imageComtainer" src="../../../assets/BlogImage/02_20.png"/>
    
    
  </div>
  <footer-com></footer-com>
</div>
</template>
<script>
import Header from "../public/Header";
import Footer from "../public/Footer";
export default ({
  
  components: {
    "header-com": Header,
    "footer-com": Footer
  },
})
</script>

<style lang="less" scoped>
.card-container {
    background: linear-gradient(180deg, rgba(255, 255, 255, 0.45) 5%, rgba(255, 255, 255, 0.75) 30%, #ffffff 60%);
    // border-radius: 15px;
}
#topImageComtainer{
  text-align: center;
  margin-left: 27%;
}
#imageComtainer{
  margin-left: 20%;
  width: 65%;
}
</style>