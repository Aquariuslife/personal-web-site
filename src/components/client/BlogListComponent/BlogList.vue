<template>
  <div>
    <header-com></header-com>
    <div class="section-container">
      <div class="container">
        <div class="row">
          <div class="col-xs-12">
            <div class="section-container-spacer text-center">
              <h1 class="h2">{{ $t("navbar.Blogs") }}</h1>
            </div>
            <div class="blog_list row">
              <div class="shadow_outfit clearfix">
                <div
                  class="blog_list_item col-xs-12 col-md-6 col-md-offset-3"
                  v-for="(item, index) in blogList"
                  :key="index"
                >
                  <h3 class="blog_title" v-text="item.blogTitle"></h3>
                  <p class="blog_info">
                    <i class="fa fa-eye"></i>
                    {{ item.blogViewNum }} |
                    <i class="fa fa-comment-o"></i>
                    {{ item.blogComment }} |
                    <i class="fa fa-clock-o"></i>
                    {{ item.blogAddTime.slice(0, 10) }} |
                    <i class="fa fa-tag"></i>
                    {{ item.blogCategory }}
                  </p>
                  <h4 class="blog_intro" v-text="item.blogIntro"></h4>
                  <!-- :dataIndex="index==0?(sub_index+1):(sub_index+1+item.length)" -->
                  <!--
                                    <a href="defect-detection.html">
                                        <router-link :to="defect-detection.html">
                                      <router-link :to="{ name: 'logcontent'}" tag="li">
                                      -->
                  <router-link :to="{ name: 'logcontent' }">
                    <img
                      style="width:267px;height:175px"
                      :src="item.blogPic"
                      class="img-responsive img-responsive-auto-width blog_link"
                    />
                    <a href="" @click="goto(item.blogUrl)" class="blog_read_btn"
                      >阅读全文>></a
                    >
                  </router-link>

                  <el-divider></el-divider>
                </div>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
    <footer-com></footer-com>
  </div>
</template>

<script>
import Header from "../public/Header";
import Footer from "../public/Footer";
import LazyImg from "../public/LazyImg";
export default {
  data() {
    return {
      blogList: [
        {
          blogId: 1,
          blogTitle: "Learn",
          blogViewNum: 999,
          blogComment: 999,
          blogAddTime: "2020-01-09T09:39:52.435Z",
          blogIntro:
            "A hybrid recommendation algorithm–based intelligent business recommendation system",
          blogCategory: "Recommendation algorithms",
          blogPic: require("../../../assets/images/BlogView01.jpeg")
        },
        {
          blogId: 2,
          blogTitle: "Learn",
          blogViewNum: 888,
          blogComment: 888,
          blogAddTime: "2021-04-01T08:29:30.225Z",
          blogIntro:
            "Deep-Structured Machine Learning Model for the Recognition of Mixed-Defect Patterns in Semiconductor Fabrication Processes",
          blogCategory: "Defect Detection",
          blogPic: require("../../../assets/images/BlogView02.jpeg")
        }
      ]
    };
  },
  components: {
    "header-com": Header,
    "footer-com": Footer,
    "lazy-img": LazyImg
  },
  methods: {
    goto(id) {
      this.$router.push({ name: "logcontent", params: { contentid: id } });
    },
    getArticles() {
      this.$axios({
        url: "/index/getpage",
        method: "get"
      }).then(res => {
        if (res.status == 200) {
          sessionStorage.setItem("allArticles", JSON.stringify(res.data));
          res.data.forEach(v => {
            this.blogList.push({
              id: v._id,
              blogTitle: v.title,
              blogViewNum: v.num,
              blogComment: v.comment.length,
              blogAddTime: v.addtime,
              blogIntro: v.description || "",
              blogCategory: v.category.name,
              blogPic: v.minpic_url
            });
          });
        }
      });
    }
  },
  beforeMount() {
    this.getArticles();
  }
};
</script>

<style lang="less" scoped>
.blog_list {
  .shadow_outfit {
    box-shadow: 0 5px 10px rgba(0, 0, 0, 0.5);
    > .blog_list_item {
      h3.blog_title {
      }
      p.blog_info {
      }
      h4.blog_intro {
        margin: 15px 0;
      }
      img.blog_link {
        transition: transform 0.3s;
      }
      img.blog_link:hover {
        transform: scale(1.05);
      }
      a.blog_read_btn {
        display: inline-block;
        color: rgb(30, 30, 30);
        margin-top: 10px;
        position: relative;
        text-decoration: none;
        font-size: 12px;
        transition: font-size 0.3s;
      }
      a.blog_read_btn::after {
        content: "";
        width: 100%;
        height: 3px;
        background-color: #000;
        position: absolute;
        left: 0;
        bottom: -3px;
        transition: width 0.3s;
      }
      a.blog_read_btn:hover {
        font-size: 16px;
      }
      a.blog_read_btn:hover::after {
        width: 0%;
      }
    }
  }
}
</style>
