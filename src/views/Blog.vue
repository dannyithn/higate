<template>
  <div class="blog">
    <Sticky />
    <div class="px-4 md:px-[30px] max-w-[1062px] xl:max-w-[1128px] lg:px-0 mx-auto py-12 lg:py-[96px]">
      <div class="md:grid md:grid-cols-2 lg:grid-cols-3 gap-6">
        <div class="mb-6 lg:mb-0" 
          v-for="blog in blogs"
          v-bind:key="blog.sys.id"
        >
          <a href="/blogDetail/66cZ5rDdg6n90a2OfjNmSi">
            <img class="m-auto w-[100%]" src="https:////images.ctfassets.net/zml4qel2k312/1CJm5KhOmwnU0DE598uPaY/ac938c10880b8c4a879d98537f04949a/cloud.svg" width="360" height="260" /></a>
            <img :src="blog.blogImage.url" :alt="blog.blogTitle.title" :width="blog.blogImage.width" :height="blog.blogImage.height"  />
            <div class="flex gap-2 items-center mt-6">
            <div class="py-1 text-[#23262F] uppercase px-[10px] bg-border-active">{{ blog.blogTitle}}</div>
            <p class="text-[14px] leading-[20px] text-[#888C95]"><span>>{{ blog.createdDate}}</span></p>
          </div>
          <a href="/blogDetail/66cZ5rDdg6n90a2OfjNmSi"><p class="text-5 leading-[120%] text-title-text hover:text-primary-1 cursor-pointer font-bold Open Sans mt-2 mb-[18px]">Cloud native - a driving trend in the industry</p></a>
          <div class="text-[14px] dark:text-primary-1 leading-[150%] font-semibold"><a href="/blogDetail/66cZ5rDdg6n90a2OfjNmSi" class="text-[#0F23D0]">See More</a></div>
        </div>
      </div>
    </div>  
  </div>
</template>

<script>
import Sticky from '@/components/Sticky.vue'
// @ is an alias to /src
export default {
  name: 'Blog',
  components: {
    Sticky
  },
  data() {
      return {
        blogs: []
      };
    },
  async created() {
      this.blogs = await this.getBlogs();
    },
  methods: {
      getBlogs: async () => {
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
            "Content-Type": "application/json"
          },
          body: JSON.stringify({ query })
        };

        try {
          const response = await fetch(fetchUrl, fetchOptions).then(response =>
            response.json()
          );
          return response.data.blogCollection.items;
        } catch (error) {
          throw new Error("Could not receive the data from Contentful!");
        }
      }
    },
  mounted () {
    document.body.classList.add('font-body')
  },
  destroyed () {
    document.body.classList.remove('font-body')
  }
}
</script>