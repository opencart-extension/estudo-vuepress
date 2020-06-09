<template>
  <div>
      <div class="pix_section pix_nav_menu pix_scroll_header normal pix-padding-v-10" data-scroll-bg="#fff">
      <div class="container" id="header-container">
        <div class="row">
          <div class="col-md-10 col-xs-12 pix-inner-col col-sm-10 column ui-droppable">
            <div class="pix-content">
              <nav class="navbar navbar-default pix-no-margin-bottom pix-navbar-default">
                <div class="container-fluid">
                  <div class="navbar-header">
                    <button type="button" class="navbar-toggle collapsed" data-toggle="collapse" data-target="#pix-navbar-collapse" aria-expanded="false">
                      <span class="sr-only">Toggle navigation</span>
                      <span class="icon-bar"></span>
                      <span class="icon-bar"></span>
                      <span class="icon-bar"></span>
                    </button>
                    <a class="navbar-brand logo-img logo-img-a pix-adjust-height" href="#">
                      <img :src="$themeConfig.logo" alt="" class="img-responsive pix-logo-img">
                    </a>
                  </div>
                  <div class="collapse navbar-collapse" id="pix-navbar-collapse">
                    <ul class="nav navbar-nav navbar-right media-middle pix-header-nav pix-adjust-height" id="pix-header-nav" style="margin-top: 5px;">
                      <li class="dropdown" v-for="nav in $themeConfig.nav" :key="`menu-${nav.text}`">
                        <a :href="nav.link" class="pix-slight-white">
                          {{ nav.text }}
                        </a>
                      </li>
                    </ul>
                  </div>
                </div>
              </nav>
            </div>
          </div>
          <div class="col-md-2 col-xs-12 pix-inner-col col-sm-2">
            <div class="pix-content pix-adjust-height text-right" style="margin-top: 1px;">

              <div class="pix-header-item">
                <SocialNetwork />
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>

    <div class="pix_section pix-padding-v-40">
      <component :is="layout" />
    </div>

    <div class="pix_section pix-padding-v-20 gray-light-black">
      <div class="container">
        <div class="row">
          <div class="col-md-3 col-xs-12 col-sm-3">
            <div class="pix-content">
              <h5 class="pix-white"><span class="pix_edit_text"><strong>Meet PixFort</strong></span></h5>
              <div class="pix-padding-v-10">
                <a href="#" class="pix-gray"><span class="pix_edit_text">About PixFort</span></a>
              </div>
              <div class="pix-padding-v-10">
                <a href="#" class="pix-gray"><span class="pix_edit_text">Explore our Ecosystem</span></a>
              </div>
              <div class="pix-padding-v-10">
                <a href="#" class="pix-gray"><span class="pix_edit_text">Careers</span></a>
              </div>
            </div>
          </div>
          <div class="col-md-3 col-xs-12">
            <h5 class="pix-white"><span class="pix_edit_text"><strong>Our Community</strong></span></h5>
            <div class="pix-padding-v-10">
              <a href="#" class="pix-gray"><span class="pix_edit_text">Purchase MEGAPACK</span></a>
            </div>
            <div class="pix-padding-v-10">
              <a href="#" class="pix-gray"><span class="pix_edit_text">PixBuilder Demo</span></a>
            </div>
            <div class="pix-padding-v-10">
              <a href="#" class="pix-gray"><span class="pix_edit_text">View Portfolio</span></a>
            </div>
          </div>
          <div class="col-md-3 col-xs-12">
            <h5 class="pix-white"><span class="pix_edit_text"><strong>Helpdesk</strong></span></h5>
            <div class="pix-padding-v-10">
              <a href="#" class="pix-gray"><span class="pix_edit_text">Contact Support</span></a>
            </div>
            <div class="pix-padding-v-10">
              <a href="#" class="pix-gray"><span class="pix_edit_text">Open a Ticket</span></a>
            </div>
            <div class="pix-padding-v-10">
              <a href="#" class="pix-gray"><span class="pix_edit_text">View Knowledge base</span></a>
            </div>
          </div>
          <div class="col-md-3 col-xs-12">
            <h5 class="pix-white"><span class="pix_edit_text"><strong>Get in Touch</strong></span></h5>
            <div class="pix-padding-v-10">
              <p class="pix-gray">
                <span class="pix_edit_text">
                  We provides you with a full user that results in faster.
                </span>
              </p>
            </div>
          </div>
          <div class="col-md-12 col-xs-12">
          </div>
          <div class="col-md-7 col-xs-12">
            <div class="pix-content pix-padding-v-30">
              <a class="pix-inline-block" href="#"><img src="images/main/logo-md-light.png" alt="" class="img-responsive"></a>
            </div>
          </div>
          <div class="col-md-5 col-xs-12">
            <div class="pix-content pix-padding-v-30 text-right">
              <span class="pix-black-gray-light pix-padding-v-10 pix-inline-block pix-margin-fix-top"><span class="pix_edit_text">MEGAPACK Copyright © 2017 PixFort All Rights Reserved</span></span>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import SocialNetwork from '../components/SocialNetwork'

export default {
  name: 'GlobalLayout',

  components: {
    SocialNetwork
  },

  data: () => ({
    socialNetwork: null
  }),

  computed: {
    layout() {
      if (this.$page.path) {
        if (this.$frontmatter.layout) {
          return this.$frontmatter.layout
        }
        return 'Layout'
      }

      return 'NotFound'
    }
  }
}
</script>

<style>
@import url('/css/bootstrap.css');
@import url('/css/font-awesome.min.css');
@import url('/css/main.css');
@import url('/css/font-style.css');

#header-container {
  width: 90%
}

h1 {
  margin-top: 0.54em;
  font-size: 34px;
  font-weight: 600;
  letter-spacing: -0.022em;
  line-height: 1.12;
  font-style: normal;
}

h1 a {
  color: #bbb;
  transition: all 0.4s ease-out;
}

h1:hover a {
  color: #000;
}
</style>