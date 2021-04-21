<template>
  <v-app id="inspire">
    <!-- ■■■■■■■■ 主体内容 ■■■■■■■■ -->
    <v-content style="padding-bottom: 0;">
        <v-container
          fluid
          @click="PlotCurves()"
        >
          <!-- 标题 -->
          <v-layout
            row
            wrap
          >
            <v-flex xs12>
              <h1>Mathematica问答社区</h1>
              <h3>学习、交流、分享</h3>
            </v-flex>
          </v-layout>

          <br>
          <br>
          <v-divider />
          <br>
          <br>

          <!-- 画布 曲线 -->
          <canvas
            id="canvas"
            width="300"
            height="300"
          />

          <!-- 网站 列表 -->
          <v-layout
            flex-child
            align-center
            justify-center
            wrap
            class="xl-6 lg-6 md-6 sm-8 xs-12"
          >
            <!-- <v-flex md2></v-flex> -->
            <v-flex
              v-for="web in myWeb"
              :key="web.name"
              xs12
              sm12
              md4
              lg4
              xl3
            >
              <v-hover>
                <v-card
                  :href="web.href"
                  target="_blank"
                  slot-scope="{ hover }"
                  :class="`elevation-${hover ? 12 : 2}`"
                  class="mx-auto"
                  max-width="400"
                >
                  <v-img
                    :src="web.imgsrc"
                    :lazy-src="web.imgsrcLazy"
                    aspect-ratio="1.618"
                  >
                    <v-layout
                      slot="placeholder"
                      fill-height
                      align-center
                      justify-center
                      ma-0
                    >
                      <v-progress-circular
                        indeterminate
                        color="grey lighten-1"
                      />
                    </v-layout>
                  </v-img>
                  <v-card-title primary-title>
                    <v-layout
                      justify-space
                      row
                      fill-height
                    >
                      <v-flex>
                        <h4 class="title font-weight-bold">{{ web.name }}</h4>
                        <div class="body-2">{{ web.description_html }}</div>
                      </v-flex>
                    </v-layout>
                  </v-card-title>
                </v-card>
              </v-hover>
            </v-flex>
            <!-- <v-flex md2></v-flex> -->

          </v-layout>
        </v-container>
    </v-content>

    <x-footer />

  </v-app>
</template>

<script>

import { plotCurves as PlotCurves, resizeCanvas as ResizeCanvas } from '@/assets/js/PlotCurve';
import Footer from '@/components/Footer';


export default {
  name: 'PageHome',
  components: {
    'x-footer': Footer,
  },
  data() {
    return {
      myWeb: [
        {
          name: '博客',
          href: 'https://mmaqa.com/blog/',
          imgsrc: 'https://mmaqa.com/z-src/home-images/blog.jpg',
          imgsrcLazy: 'https://mmaqa.com/home-images/blog.lazy.jpg',
          description_html: '创办于2018-02-01',
          size: 3,
        },
        {
          name: '问答社区',
          href: 'http://mmaqa.com/qa/',
          imgsrc: 'https://mmaqa.com/z-src/home-images/mma.ooo.jpg',
          imgsrcLazy: 'https://mmaqa.com/z-src/home-images/mma.ooo.lazy.jpg',
          description_html: '创办于2016-04-01',
          size: 3,
        },
        {
          name: '笔记',
          href: 'https://lixuan.xyz/notes/mathematica/',
          imgsrc: 'https://mmaqa.com/z-src/home-images/note.jpg',
          imgsrcLazy: 'https://mmaqa.com/z-src/home-images/note.lazy.jpg',
          description_html: '创办于2017-04-01',
          size: 3,
        },
],
    };
  },
  methods: {
    PlotCurves() {},
  },
  mounted() {
    // 绘制背景曲线
    PlotCurves();
    this.PlotCurves = PlotCurves;
    window.onresize = () => {
      ResizeCanvas();
    };
  },
};
</script>

<style media="screen">
  /* 网站背景颜色 */
  body,.application--wrap,.v-content{
    background-color: #dedcd4;
    text-align: center;
  }

  /*  页脚 */
  .v-footer{
    background-color: #dedcd4;
    text-align: center;
  }
  canvas {
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
  }

  .v-card {
    border-radius: 10px;
    border: 2px double  rgba(0,0,32,0.3);
  }
  .v-img {
    border-bottom: 1px solid #333;
  }

.v-card > *:last-child:not(.v-btn):not(.v-chip){
  background-color: #dedcd4;
  padding-top: 18px;
  border-top: 1px dashed rgba(0,0,0,0.3);
}

</style>
