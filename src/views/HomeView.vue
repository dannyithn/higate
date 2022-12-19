<template>
  <div class="home" 
      v-for="show in shows"
       v-bind:key="show.sys.id"
  >
    <div class='  bg-[radial-gradient(at_center_bottom,_#5567ff29,_#5567ff00,_#ffffff00)]'>
      <div class='max-w-[1128px] mx-auto flex flex-col px-4 768:px-[30px] items-center justify-center'>
        <div class='pt-8 pb-[43px] order-last 1440:order-first 1440:pt-[96px] 1440:pb-[26px]'>
          <img :src="show.bannerImage.url" :alt="show.bannerImage.title" :width="show.bannerImage.width" :height="show.bannerImage.height"  />
        </div>
        <div class='max-w-[825px] pt-[48px] 1440:pt-0'>
          <h1 
          class="text-title-text text-[36px] leading-[43.2px] text-center xl2:text-[64px] xl2:leading-[76.8px] font-OpenSans font-bold" 
          v-html="show.bannerTitle.json.content[0].content[0].value" />
        </div>
        <div class="max-w-[552px] pt-4 text-body-text2 leading-body-text2 xl2:pt-4 xl2:pb-[96px] md:text-body-text1 text-center text-body-text font-OpenSans font-normal md:leading-[22.88px]">
            {{ show.bannerDescription.json.content[0].content[0].value }}
        </div>
      </div>
    </div>
    <!--end block-1 -->
    <div class="px-4 md:px-[30px]">
      <div class="max-w-[888px] mx-auto grid grid-cols-1 py-[42px] gap-y-10 md:gap-y-0 md:grid-cols-3 md:gap-x-[42px] xl2:py-10">
      <div class="flex justify-center items-center cursor-pointer md:max-w-[264px] rounded-lg px-4">
         <div class="flex self-start md:ml-4 lg:ml-0">
            <svg stroke="currentColor" fill="currentColor" stroke-width="0" viewBox="0 0 24 24" height="24" width="24" xmlns="http://www.w3.org/2000/svg" style="color: rgb(15, 35, 208); margin-right: 12px;">
               <path fill="none" d="M0 0h24v24H0z"></path>
               <path d="M12 2C8.13 2 5 5.13 5 9c0 5.25 7 13 7 13s7-7.75 7-13c0-3.87-3.13-7-7-7zm0 9.5a2.5 2.5 0 010-5 2.5 2.5 0 010 5z"></path>
            </svg>
            <div class="text-body-text1 text-body-text font-OpenSans font-normal leading-body-text1 w-[275px] md:w-[196px]"> {{ show.bodyTopContent[0]}} </div>
         </div>
      </div>
      <div class="flex justify-center cursor-pointer md:max-w-[264px] rounded-lg md:mt-0">
         <div class="flex self-start">
            <svg stroke="currentColor" fill="currentColor" stroke-width="0" viewBox="0 0 24 24" height="24" width="24" xmlns="http://www.w3.org/2000/svg" style="color: rgb(15, 35, 208); margin-right: 12px;">
               <path fill="none" d="M0 0h24v24H0z"></path>
               <path d="M12 2C6.48 2 2 6.48 2 12s4.48 10 10 10 10-4.48 10-10S17.52 2 12 2zm-2 15l-5-5 1.41-1.41L10 14.17l7.59-7.59L19 8l-9 9z"></path>
            </svg>
            <div class="text-body-text1 text-body-text font-OpenSans font-normal leading-body-text1 w-[275px] md:w-[196px]"> {{ show.bodyTopContent[1]}} </div>
         </div>
      </div>
      <div class="flex justify-center cursor-pointer md:max-w-[264px] rounded-lg">
         <div class="flex self-start">
            <svg stroke="currentColor" fill="currentColor" stroke-width="0" viewBox="0 0 24 24" height="24" width="24" xmlns="http://www.w3.org/2000/svg" style="color: rgb(15, 35, 208); margin-right: 12px;">
               <path fill="none" d="M0 0h24v24H0V0z"></path>
               <path d="M12 1L3 5v6c0 5.55 3.84 10.74 9 12 5.16-1.26 9-6.45 9-12V5l-9-4zm0 10.99h7c-.53 4.12-3.28 7.79-7 8.94V12H5V6.3l7-3.11v8.8z"></path>
            </svg>
            <div class="text-body-text1 text-body-text font-OpenSans font-normal leading-body-text1 w-[275px] md:w-[196px]"> {{ show.bodyTopContent[2]}} </div>
         </div>
      </div>
    </div>
    </div>
    <!--end block-2 -->
    <div class="bg-[#FAFAFA]">
      <div class="max-w-[1128px] mx-auto px-4 md:px-[30px] xl2:px-0">
        <div class="grid grid-cols-1 md:grid-cols-2 md:gap-x-[24px] py-12 xl2:pt-[96px] xl2:pb-[96px]">
          <div class="w-full xl2:w-[480px] md:self-center">
            <div class="text-title-text text-[28px] leading-[33.6px] mb-[20px] lg:text-[42px] lg:leading-[50.4px] xl2:mb-8 font-OpenSans font-bold">
              <div :innerHTML="show.hiringTitle.json.content[0].content[0].value"></div>
            </div>
            <div class="text-body-text1 text-body-text font-OpenSans leading-body-text1">
              <div class="hire-para-1">
                  <p :innerHTML="show.hiringTopPara1.json.content[0].content[0].value"></p>
              </div>
              <div class="hire-para-2 mt-[26px] md:mt-[32px] max-w-[450px]">
                <p :innerHTML="show.hiringTopPara2.json.content[0].content[0].value"></p>
              </div>
              <div class="flex flex-col md:items-center mt-9 lg:mt-12 xl2:items-start md:flex-row xl2:mt-8">
                <div class="w-full mb-4 md:mb-0 md:w-[168px] relative group h-[40px] cursor-pointer text-secondary hover:bg-[#0B1992] active:bg-primary-1 text-body-text1 font-OpenSans font-semibold bg-primary-1 flex items-center justify-center rounded md:mr-6">
                  <a href=""> Hire Developers</a>
                </div>
                <div class="w-full md:mb-0 md:w-[151px] overflow-hidden relative group h-[40px] cursor-pointer mb-3 text-primary-1 text-body-text1 font-OpenSans font-semibold border-primary-1 border-[1px] hover:bg-[#0f23d00a] active:bg-secondary flex items-center justify-center rounded">
                  <a href=""> Apply for Jobs</a> 
                </div>
              </div>
            </div>
          </div>
          <div class="flex md:justify-start w-[343px] h-[297px] md:max-w-[552px] md:max-h-[478px] xl2:w-[552px] xl2:h-[478px] relative">
            <img :src="show.hiringImage.url" alt="{{ show.hiringImage.title }}" :width="show.hiringImage.width" :height="show.hiringImage.height"/>
          </div>
        </div>
        <div class="grid grid-cols-1 md:grid-cols-2 md:gap-x-14 pb-[48px] xl2:grid-cols-4 xl2:gap-x-6 md:pb-[69px] px-4 md:px-0">
         <div class="overflow-hidden h-[92px] xl2:h-[131px] mb-6 xl2:mb-0 relative text-body-text1 text-body-text leading-[22.88px] flex items-center">
            <span class="block h-6 border-l-2 border-l-primary-1 absolute z-10 top-0"></span><span class="block h-full border-l-[1px] border-l-primary-1/10 absolute top-0 pr-4"></span>
            <div class="pl-4 w-[279px] md:w-full xl2:w-[232px] font-OpenSans aos-init" data-aos="fade-right" data-aos-delay="50" data-aos-duration="1000" data-aos-easing="ease-in-out" data-aos-offset="-150"> <p v-bind:innerHTML="show.hiringBottomPara[0]"></p></div>
         </div>
         <div class="overflow-hidden h-[92px] xl2:h-[131px] mb-6 xl2:mb-0 relative text-body-text1 text-body-text leading-[22.88px] flex items-center">
            <span class="block h-6 border-l-2 border-l-primary-1 absolute z-10 top-0"></span><span class="block h-full border-l-[1px] border-l-primary-1/10 absolute top-0 pr-4"></span>
            <div class="pl-4 w-[279px] md:w-full xl2:w-[232px] font-OpenSans aos-init" data-aos="fade-right" data-aos-delay="50" data-aos-duration="1000" data-aos-easing="ease-in-out" data-aos-offset="-150"> <p v-bind:innerHTML="show.hiringBottomPara[1]"></p></div>
         </div>
         <div class="overflow-hidden h-[92px] xl2:h-[131px] mb-6 xl2:mb-0 relative text-body-text1 text-body-text leading-[22.88px] flex items-start md:items-center">
            <span class="block h-6 border-l-2 border-l-primary-1 absolute z-10 top-0"></span><span class="block h-full border-l-[1px] border-l-primary-1/10 absolute top-0 pr-4"></span>
            <div class="pl-4 w-[279px] md:w-full xl2:w-[232px] font-OpenSans aos-init" data-aos="fade-right" data-aos-delay="50" data-aos-duration="1000" data-aos-easing="ease-in-out" data-aos-offset="-150"> <p v-bind:innerHTML="show.hiringBottomPara[2]"></p></div>
         </div>
         <div class="overflow-hidden h-[92px] xl2:h-[131px] relative text-body-text1 text-body-text leading-[22.88px] flex items-start md:items-center">
            <span class="block h-6 border-l-2 border-l-primary-1 absolute z-10 top-0"></span><span class="block h-full border-l-[1px] border-l-primary-1/10 absolute top-0 pr-4"></span>
            <div class="pl-4 w-[279px] md:w-full xl2:w-[232px] font-OpenSans aos-init" data-aos="fade-right" data-aos-delay="50" data-aos-duration="1000" data-aos-easing="ease-in-out" data-aos-offset="-150"> <p v-bind:innerHTML="show.hiringBottomPara[3]"></p></div>
         </div>
      </div>
      </div>
    </div>
    <!-- end-block-3 -->
    <div class="max-w-[1128px] mx-auto grid grid-cols-1 px-4 pt-[48px] pb-[43px] md:px-[30px] md:grid-cols-2 md:gap-x-[24px] items-cente xl2:px-0 xl2:pt-[96px] xl2:pb-[100px] 1920:pb-[90px]">
      <div class="order-last justify-self-center md:justify-self-start md:order-first xl2:max-w-[512px] 1920:max-w-[543px] self-center">
        <img :src="show.developerImage.url" alt="{{ show.developerImage.title }}"  :width="show.developerImage.width" :height="show.developerImage.height" />
      </div>
      <div class="md:max-w-[560px] flex flex-col ml-0 1920:pl-[30px]">
          <div class="mb-8">
            <div class="text-[28px] xl2:text-[42px] xl2:leading-[50.4px] mb-[20px] md:mb-[32px] text-title-text dark:text-title-text font-OpenSans font-bold">
              {{ show.developerTitle.json.content[0].content[0].value }}<span class="text-primary-1" v-bind:innerHTML="show.developerTitle.json.content[0].content[1].value"></span><span v-bind:innerHTML="show.developerTitle.json.content[0].content[2].value"></span>
            </div>
            <div class="text-body-text1 text-body-text leading-[22.88px] font-OpenSans xl2:w-[552px]">
                <p v-html="show.developerDescription.json.content[0].content[0].value"></p>
            </div>
          </div>
          <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 md:gap-y-[20px] md:gap-x-[24px] md:mt-6 xl2:mt-0 1920:gap-x-[50px]">
            <div class="overflow-hidden h-[62px] px-1 max-w-[321px] md:px-0 md:max-w-[156px] md:h-[104px] mb-6 xl2:mb-0 relative text-body-text1 text-body-text leading-[22.88px] flex items-start md:items-center">
                <span class="block h-6 border-l-2 border-l-primary-1 absolute z-10 top-0"></span><span class="block h-full border-l-[1px] border-l-primary-1/10 absolute top-0 pr-4"></span>
                <div class="pl-4 font-OpenSans w-full aos-init aos-animate" data-aos="fade-right" data-aos-delay="50" data-aos-duration="1000" data-aos-easing="ease-in-out" data-aos-offset="-150"> {{ show.developerPara[0] }} </div>
            </div>
            <div class="overflow-hidden h-[62px] w-[321px] px-1 mb-6 md:px-0 md:max-w-[149px] md:h-[104px] lg:w-[168px] xl2:mb-0 relative text-body-text1 text-body-text leading-[22.88px] flex items-start md:items-center">
                <span class="block h-6 border-l-2 border-l-primary-1 absolute z-10 top-0"></span><span class="block h-full border-l-[1px] border-l-primary-1/10 absolute top-0 pr-4"></span>
                <div class="pl-4 font-OpenSans w-full aos-init aos-animate" data-aos="fade-right" data-aos-delay="50" data-aos-duration="1000" data-aos-easing="ease-in-out" data-aos-offset="-150"> {{ show.developerPara[1] }} </div>
            </div>
            <div class="overflow-hidden h-[62px] mb-[46px] w-[321px] px-1 md:px-0 md:max-w-[156px] md:h-[104px] lg:w-[168px] relative text-body-text1 text-body-text leading-[22.88px] flex items-start md:items-center xl2:mb-0">
                <span class="block h-6 border-l-2 border-l-primary-1 absolute z-10 top-0"></span><span class="block h-full border-l-[1px] border-l-primary-1/10 absolute top-0 pr-4"></span>
                <div class="pl-4 font-OpenSans w-full aos-init aos-animate" data-aos="fade-right" data-aos-delay="50" data-aos-duration="1000" data-aos-easing="ease-in-out" data-aos-offset="-150"> {{ show.developerPara[2] }} </div>
            </div>
          </div>
      </div>
    </div>
    <!-- end-block-4 -->
    <div class="banner-counter bg-body-text bg-bg-blue flex justify-center items-center">
      <div class="bg-no-repeat bg-center w-full max-w-6xl py-[48px] xl2:py-[71px]">
          <div class="max-w-[1128px] mx-auto px-4 md:px-[30px] flex justify-center">
            <div class="flex flex-col justify-around items-center font-bold max-w-[744px] text-button-secondary text-subtitle3">
                <div class="md:mb-16">
                  <div class="text-center text-[20px] leading-[24px] md:text-[36px] font-OpenSans md:leading-[43.2px] font-bold">
                      <p> {{ show.bodyBottomTitle.json.content[0].content[0].value }} </p>
                  </div>
                </div>
                <div class="flex flex-col justify-center items-center my-8 md:w-[552px] md:flex-row md:mt-0 md:justify-between md:mb-[64px] 1920:mb-16">
                  <div class="w-[168px] mb-6 md:mb-0 flex flex-col items-center justify-center">
                      <div class="flex text-center text-[42px] font-bold leading-[50.4px] mb-2 font-OpenSans">
                        <div>
                            <p class="font-OpenSans">20</p>
                        </div>
                        + 
                      </div>
                      <p class="text-body-text1 font-normal leading-[22.88px] opacity-70 font-OpenSans"> Job types </p>
                  </div>
                  <div class="w-[168px] mb-6 md:mb-0 flex flex-col items-center justify-center">
                      <div class="flex text-center text-[42px] font-bold leading-[50.4px] mb-2 font-OpenSans">
                        <div>
                            <p class="font-OpenSans">100</p>
                        </div>
                        + 
                      </div>
                      <p class="text-body-text1 font-normal leading-[22.88px] opacity-70"> Technologies </p>
                  </div>
                  <div class="w-[168px] flex flex-col items-center justify-center">
                      <div class="flex justify-center text-center text-[42px] font-bold leading-[50.4px] mb-2 font-OpenSans">
                        <div>
                            <p class="font-OpenSans">5</p>
                        </div>
                        + 
                      </div>
                      <p class="text-body-text1 font-normal leading-[22.88px] opacity-70"> Seniority Levels </p>
                  </div>
                </div>
                <div class="text-body-text1 font-normal w-full md:w-[343px] flex flex-col md:flex-row justify-evenly">
                  <div class="w-full md:mb-0 md:w-[168px] bg-button-secondary hover:bg-primary-1 hover:text-secondary overflow-hidden relative group h-[40px] cursor-pointer mb-3 text-primary-1 text-body-text1 font-OpenSans font-semibold border-primary-1 border-[1px] active:bg-primary-1 flex items-center justify-center rounded"> Hire Developers<span class="absolute w-0 h-0 transition-all duration-500 ease-out bg-secondary rounded-full group-active:w-48 group-active:h-48 opacity-10"></span></div>
                  <div class="w-full md:w-[151px] md:ml-6 relative group overflow-hidden h-10 cursor-pointer text-secondary hover:bg-secondary hover:text-primary-1 active:bg-secondary text-body-text1 font-OpenSans font-semibold bg-transparent border border-secondary flex items-center justify-center rounded"> Apply for jobs<span class="absolute w-0 h-0 transition-all duration-500 ease-in-out bg-[#0f23d04d] rounded-full group-active:w-40 group-active:h-40 opacity-10"></span></div>
                </div>
            </div>
          </div>
      </div>
    </div>
  </div>
</template>

<script>
// @ is an alias to /src
export default {
  name: 'HomeView',
  components: {
  },
  data() {
      return {
        shows: []
      };
    },
  async created() {
      this.shows = await this.getShows();
    },
  methods: {
      getShows: async () => {
        const query = `{
          homepageCollection{
            items {
              sys {
                id
              }
              bannerImage {
                title
                description
                contentType
                fileName
                size
                url
                width
                height
              }
              bannerTitle {
                json
              }
              bannerDescription {
                json
              }
              bodyTopContent
              hiringBottomPara
              hiringImage {
                title
                description
                contentType
                fileName
                size
                url
                width
                height
              }
              hiringTitle {
                json
              }
              hiringTopPara1 {
                json
              }
              hiringTopPara2{
                json
              }
              hiringImage {
                title
                description
                contentType
                fileName
                size
                url
                width
                height
              }
              hiringBottomPara
              developerTitle{
                json
              }
              developerDescription{
                json
              }
              developerPara
              developerImage {
                title
                description
                contentType
                fileName
                size
                url
                width
                height
              }
              bodyBottomTitle{
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
          return response.data.homepageCollection.items;
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
<style>

.text-primary-1 {
    --tw-text-opacity: 1;
    color: rgb(15 35 208/var(--tw-text-opacity));
}
.text-body-text {
    color: #00000099;
}
.text-button-secondary, 
.text-secondary {
    --tw-text-opacity: 1;
    color: rgb(255 255 255/var(--tw-text-opacity));
}

.bg-primary-1 {
    --tw-bg-opacity: 1;
    background-color: rgb(15 35 208/var(--tw-bg-opacity));
}
.border-primary-1 {
    --tw-border-opacity: 1;
    border-color: rgb(15 35 208/var(--tw-border-opacity));
}
.border-l-primary-1 {
    --tw-border-opacity: 1;
    border-left-color: rgb(15 35 208/var(--tw-border-opacity));
}
.border-l-2 {
    border-left-width: 2px;
}
.text-primary-1 {
    --tw-text-opacity: 1;
    color: rgb(15 35 208/var(--tw-text-opacity));
}
.banner-counter {
    background-image: url(../assets/Frame34.fe2b57d5.png);
}
.bg-bg-blue {
    --tw-bg-opacity: 1;
    background-color: rgb(11 25 146/var(--tw-bg-opacity));
}
.bg-button-secondary {
    --tw-bg-opacity: 1;
    background-color: rgb(255 255 255/var(--tw-bg-opacity));
}
</style>