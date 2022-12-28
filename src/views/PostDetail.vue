<template>
  <div class="post">
    <div class="bg-bg-blue">
      <div
        class="px-4 768:px-[30px] max-w-[1062px] xl:max-w-[1128px] lg:px-0 m-auto pt-[41px] pb-[58px] lg:pt-[70px] lg:pb-[98px] text-center lg:text-left text-secondary"
      >
        <h1
          class="text-[36px] leading-[120%] xl:text-[64px] font-bold Open Sans mb-4"
        >
          Blog
        </h1>
        <p>See what’s going on at HiGate and in the technology world.</p>
      </div>
    </div>
    <div v-for="post in posts" v-bind:key="$route.params.id">
      <div v-if="post.sys.id === $route.params.id">
        <div
          class="px-4 md:px-[30px] max-w-[1062px] xl:max-w-[1128px] lg:px-0 m-auto py-12 lg:py-[96px]"
        >
          <div class="lg:flex justify-between">
            <div class="w-[100%] lg:w-[17%] hidden lg:block">
              <p class="dark:text-body-text text-[14px] leading-[20px]">
                written by
                <span class="text-title-text ml-2">{{ post.blogAuthor }}</span>
              </p>
              <p class="dark:text-body-text text-[14px] leading-[20px] mt-2">
                <span>{{ getFormatDate(post.createdDate) }}</span>
              </p>
              <ul
                class="list-none flex align-center flex-wrap gap-y-2 gap-x-2 mt-[16px] lg:mt-6"
              ></ul>
            </div>
            <div class="w-[100%] lg:w-[83%] dark:text-title-text">
              <h2
                class="text-[28px] leading-[120%] lg:text-[36px] font-bold Open Sans"
              >
                {{ post.blogTitle }}
              </h2>
                    {{ convertContent(post.blogContent.json.content) }}
              <!-- <div v-html=post.blogContent.json.content></div> -->
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import moment from "moment";
import Sticky from "@/components/Sticky.vue";
export default {
  name: "PostDetail",
  components: {},
  data() {
    return {
      posts: [],
    };
  },
  async created() {
    this.posts = await this.getPosts();
  },
  methods: {
    getPosts: async () => {
      const query = `{
          blogCollection{
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
        return response.data.blogCollection.items;
      } catch (error) {
        throw new Error("Could not receive the data from Contentful!");
      }
    },
    getFormatDate: function (date) {
      return moment(date, "YYYY-MM-DD").format("DD/MM/YYYY");
    },
    convertContent(data) {
        var html = "";
      for (var i = 0; i < data.length; i++) {
        for (var j = 0; j < data[i].content.length; j++) {
          html += data[i].content[j].value;
        }
      }
      return html;
    }
  },
  mounted() {
    document.body.classList.add("font-body");
  },
  destroyed() {
    document.body.classList.remove("font-body");
  },
};
</script>
<style>
.bg-border-active {
  background-color: #0f23d014;
}
</style>
