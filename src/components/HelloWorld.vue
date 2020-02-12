<template>
  <div>
    <carousel :items="1" :auto-height="false" :dots="false" :nav="false">
      <div v-for="(s, index) in slides" :key="index">
        <div
          class="carousel-slide"
          :style="{
            'background-image': 'url(' + s.src + ')',
            'background-size': 'cover',
            'background-position': s.position,
            'background-color': 'rgba(0, 0, 0, 1)',
            height: 'calc(100vh - 3.5rem)',
            position: 'relative'
          }"
        >
          <div
            class="slide-overlay"
            style="z-index: 0; top: 0; left: 0; background-color: rgba(0, 0, 0, .3); width: 100%; height: 100%; position: absolute"
          >
            <b-container>
              <b-row>
                <b-col style="padding-top: 8rem">
                  <b-jumbotron
                    style="background-color: rgba(255,255,255,0.95)"
                    text-variant="primary"
                  >
                    <template v-slot:header>{{ s.title }}</template>

                    <p
                      class="lead text-dark py-3 px-5"
                      v-html="
                        s.hasOwnProperty('lead') ? s.lead : 'Non Specified'
                      "
                    ></p>

                    <b-button variant="primary" :href="s.linkUrl">{{
                      s.linkText
                    }}</b-button>
                  </b-jumbotron>
                </b-col>
              </b-row>
            </b-container>
          </div>
        </div>
      </div>
    </carousel>
  </div>
</template>

<script>
import carousel from "vue-owl-carousel";

/* eslint-disable no-unused-vars */
export default {
  components: { carousel },
  data() {
    return {
      slide: 0,
      sliding: null,
      slides: [
        {
          src: require("@/assets/images/cctv.jpeg"),
          position: "left top",
          title: "CCTV Installation",
          lead:
            "If you're looking at getting a bit more security, why not consider contacting <a href='#'>Backup Security</a> for a free quote on a CCTV installation.",
          linkUrl: "#",
          linkText: "Contact Us"
        },
        {
          src: require("@/assets/images/club-one.jpeg"),
          position: "right center",
          title: "Door Security",
          lead:
            "Have your own venue? Contact <a href='#'>Backup Security</a> to see what we can do to help make sure your events run without a hitch.",
          linkUrl: "#",
          linkText: "Contact Us"
        },
        {
          src: require("@/assets/images/site.jpeg"),
          position: "center center",
          title: "Site Security",
          lead: `<a class='text-primary' href='#'>Backup Security</a> can provide on-site security solutions to guarantee complete protection of your land & property.`,
          linkUrl: "#",
          linkText: "Contact Us"
        },
        {
          src: require("@/assets/images/patrol.jpeg"),
          position: "top left",
          title: "Regular Patrols",
          lead:
            "We can send a marked <a href='#'>Backup Security</a> patrol for regular visits to venues such as building sites, listed buildings, vacant houses and building that are only closed part-time such as colleges.",
          linkUrl: "#",
          linkText: "Contact Us"
        }
      ]
    };
  },
  methods: {
    onSlideStart(slide) {
      this.sliding = true;
    },
    onSlideEnd(slide) {
      this.sliding = false;
    }
  }
};
</script>
<style lang="scss" scoped>
.carousel-slide {
  height: 600px;
}
</style>
