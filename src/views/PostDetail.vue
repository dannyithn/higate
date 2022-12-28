<template>
  <div class="post">
    <div class="bg-bg-blue">
      <div
        class="px-4 md:px-[30px] max-w-[1062px] xl:max-w-[1128px] lg:px-0 m-auto pt-[41px] pb-[58px] lg:pt-[70px] lg:pb-[98px] text-center lg:text-left text-secondary"
      >
        <h1
          class="text-[36px] leading-[120%] xl:text-[64px] font-bold Open Sans mb-4"
        >
          Blog
        </h1>
        <p>See what’s going on at HiGate and in the technology world.</p>
      </div>
    </div>
    <div>
      <div
        class="px-4 md:px-[30px] max-w-[1062px] xl:max-w-[1128px] lg:px-0 m-auto py-12 lg:py-[96px]"
      >
        <div class="lg:flex justify-between">
          <div class="w-[100%] lg:w-[17%] hidden lg:block">
            <p class="dark:text-body-text text-[14px] leading-[20px]">
              written by
              <span class="text-title-text ml-2">{{
                dataPost?.fields?.blogAuthor
              }}</span>
            </p>
            <p class="dark:text-body-text text-[14px] leading-[20px] mt-2">
              {{ getFormatDate(dataPost?.fields?.createdDate) }}
            </p>
            <ul
              class="list-none flex align-center flex-wrap gap-y-2 gap-x-2 mt-[16px] lg:mt-6"
            ></ul>
          </div>
          <div class="w-[100%] lg:w-[83%] dark:text-title-text">
            <h2
              class="text-[28px] leading-[120%] lg:text-[36px] font-bold Open Sans"
            >
              {{ dataPost?.fields?.blogTitle }}
            </h2>
            <div v-for="(items, index) in dataPost?.fields?.blogContent?.content" :key="index">
              <div v-for="(item, index) in items.content" :key="index">
                {{ item.value }}
              </div>
            </div>
            
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import moment from "moment";
const contentful = require("contentful");

export default {
  name: "PostDetail",
  props: ["id"],
  components: {},
  data() {
    return {
      dataPost: [],
    };
  },
  methods: {
    async getDataModel() {
      const client = contentful.createClient({
        space: process.env.VUE_APP_CONTENTFUL_SPACE_ID,
        accessToken: process.env.VUE_APP_CONTENTFUL_ACCESS_TOKEN,
      });
      try {
        await client.getEntry(this.$route.params.id).then((entries) => {
          console.log(entries);
          this.dataPost = entries;
        });
      } catch (error) {
        this.dataPost = undefined;
        console.log(error);
      }
    },
    getFormatDate: function (date) {
      return moment(date, "YYYY-MM-DD").format("DD/MM/YYYY");
    },
    convertContent(data) {
      console.log(data);
      var html = "";
      for (var i = 0; data < 10; i++) {
        for (var j = 0; j < data[i].content.length; j++) {
          html += data[i].content[j].value;
        }
      }
      return html;
    },
  },
  mounted() {
    this.getDataModel();
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
