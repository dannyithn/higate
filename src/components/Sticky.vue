<template>
  <div class="blog-sticky" v-for="blog in blogSticky" v-bind:key="blog.sys.id">
    <div class="bg-[#0B1992] text-secondary font-bold">
      <div
        class="px-4 md:px-[30px] max-w-[1062px] xl:max-w-[1128px] lg:px-0 m-auto pt-[41px] pb-[58px] lg:pt-[70px] lg:pb-[342px] text-center lg:text-left"
      >
        <h1 class="text-[36px] leading-[120%] xl:text-[64px] Open Sans mb-4">
          Blog
        </h1>
        <p>See what’s going on at HiGate and in the technology world.</p>
      </div>
    </div>
    <div
      class="px-4 md:px-[30px] max-w-[1062px] xl:max-w-[1128px] lg:px-0 mx-auto lg:mt-[-260px] text-secondary"
    >
      <div class="md:relative">
        <img
          class="m-auto w-[100%] aspect-[1127/520]"
          :src="blog.blogImage.url"
          :alt="blog.blogImage.title"
          :width="blog.blogImage.width"
          :height="blog.blogImage.height"
        />
        <div
          class="md:absolute top-[50%] lg:left-[100px] translate-y-[-50%] lg:max-w-[495px]"
        >
          <h3
            class="my-0 text-[28px] leading-[120%] lg:text-[36px] font-bold Open Sans"
          >
          <router-link :to="'/post/' + blog.sys.id">
              {{ blog.blogTitle }}
            </router-link>
          </h3>
          <p class="text-4 leading-[143%] mt-6 mb-6 lg:mt-6 lg:mb-4"></p>
          <p class="">{{ getFormatDate(blog.createdDate) }}</p>
          <div
            class="border border-secondary py-2 px-[22px] rounded-lg w-fit truncate mt-10"
          >
          <router-link :to="'/post/' + blog.sys.id">See More</router-link>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import moment from "moment";
// @ is an alias to /src
export default {
  name: "Sticky",
  components: {},
  data() {
    return {
      blogSticky: [],
    };
  },
  async created() {
    this.blogSticky = await this.getBlogSticky();
  },
  methods: {
    getBlogSticky: async () => {
      const query = `{
            blogStickyCollection{
              items {
                sys {
                  id
                }
                blogTitle
                blogImage {
                  title
                  description
                  contentType
                  fileName
                  size
                  url
                  width
                  height
                }
                blogSummary
                createdDate
                blogAuthor
                blogTags
                public
                blogContent {
                  json
                }
              }
            }
          }`;
      const fetchUrl = `https://graphql.contentful.com/content/v1/spaces/${process.env.VUE_APP_CONTENTFUL_SPACE_ID}`;
      const fetchOptions = {
        method: "POST",
        headers: {
          Authorization: `Bearer ${process.env.VUE_APP_CONTENTFUL_ACCESS_TOKEN}`,
          "Content-Type": "application/json",
        },
        body: JSON.stringify({ query }),
      };

      try {
        const response = await fetch(fetchUrl, fetchOptions).then((response) =>
          response.json()
        );
        return response.data.blogStickyCollection.items;
      } catch (error) {
        throw new Error("Could not receive the data from Contentful!");
      }
    },
    getFormatDate: function (date) {
      return moment(date, "YYYY-MM-DD").format("DD/MM/YYYY");
    },
  },
  mounted() {
    document.body.classList.add("font-body");
  },
  destroyed() {
    document.body.classList.remove("font-body");
  },
};
</script>
