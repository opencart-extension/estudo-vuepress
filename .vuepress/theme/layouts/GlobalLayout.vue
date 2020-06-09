<template>
  <div>
      <div class="pix_section pix_nav_menu pix_scroll_header normal pix-padding-v-10" data-scroll-bg="#fff">
      <div class="container">
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
                <a href="#" class="small-social">
                  <i class="pixicon-facebook3 big-icon-50 pix-slight-white"></i>
                </a>
                <a href="#" class="small-social">
                  <i class="pixicon-twitter4 big-icon-50 pix-slight-white"></i>
                </a>
                <a href="#" class="small-social">
                  <i class="pixicon-instagram4 big-icon-50 pix-slight-white"></i>
                </a>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>

    <div class="pix_section pix-padding-v-40">
      <component :is="layout" />
    </div>
  </div>
</template>

<script>
export default {
  name: 'GlobalLayout',

  computed: {
    layout() {
      if (this.$page.path) {
        if (this.$frontmatter.layout) {
          console.log(this.$frontmatter.layout)
          return this.$frontmatter.layout
        }
        return 'Layout'
      }

      return 'NotFound'
    }
  },

  mounted() {
    console.log(this)
  }
}
</script>

<style>
@import url('/css/bootstrap.css');
@import url('/css/font-awesome.min.css');
@import url('/css/main.css');
@import url('/css/font-style.css');

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