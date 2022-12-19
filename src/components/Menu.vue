<template>
  <div class="bg-white dark:bg-white border-b border-b-body-text/[0.1] sticky top-0 z-50 duration-300">
   <div class="flex justify-between items-center px-[16px] md:px-[30px] xl2:px-0 max-w-[1128px] mx-auto">
      <div class="flex items-center">
         <div class="block w-[93.60px] pt-[22px] pb-[23px] lg:w-[142.75px] cursor-pointer">
            <div><img src="data:image/png;base64,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" alt="logo"></div>
         </div>
         <ul class="hidden lg:flex lg:ml-[49.25px]">
            <li class="group relative flex ml-[32px] items-center text-title-text text-body-text2 pt-[30px] pb-[31px] font-OpenSans font-semibold leading-[20.02px]">
               <div class="flex cursor-pointer">
                  <p>For Agencies</p>
                  <svg stroke="currentColor" fill="currentColor" stroke-width="0" viewBox="0 0 24 24" class="ml-[5px]" height="20" width="20" xmlns="http://www.w3.org/2000/svg">
                     <path fill="none" d="M0 0h24v24H0V0z"></path>
                     <path d="M7.41 8.59L12 13.17l4.59-4.58L18 10l-6 6-6-6 1.41-1.41z"></path>
                  </svg>
               </div>
               <div class="hidden group-hover:block top-[101%] border-t-[1px] border-t-body-text/[0.1] absolute z-10 bg-white shadow-xl w-[255px] rounded-b-2xl px-4">
                  <div class="inline-block w-full py-2 cursor-pointer">
                     <div class="flex">
                        <div>
                           <svg stroke="currentColor" fill="currentColor" stroke-width="0" viewBox="0 0 16 16" height="16" width="16" xmlns="http://www.w3.org/2000/svg" style="color: rgb(15, 35, 208); margin-right: 18px; margin-top: 2px;">
                              <path d="M6.5 1A1.5 1.5 0 0 0 5 2.5V3H1.5A1.5 1.5 0 0 0 0 4.5v8A1.5 1.5 0 0 0 1.5 14h13a1.5 1.5 0 0 0 1.5-1.5v-8A1.5 1.5 0 0 0 14.5 3H11v-.5A1.5 1.5 0 0 0 9.5 1h-3zm0 1h3a.5.5 0 0 1 .5.5V3H6v-.5a.5.5 0 0 1 .5-.5zm1.886 6.914L15 7.151V12.5a.5.5 0 0 1-.5.5h-13a.5.5 0 0 1-.5-.5V7.15l6.614 1.764a1.5 1.5 0 0 0 .772 0zM1.5 4h13a.5.5 0 0 1 .5.5v1.616L8.129 7.948a.5.5 0 0 1-.258 0L1 6.116V4.5a.5.5 0 0 1 .5-.5z"></path>
                           </svg>
                        </div>
                        <div class="flex text-body-text2 leading-[22.88px] text-title-text font-OpenSans font-normal">
                           <p class="mr-2">On-demand Remote Jobs</p>
                        </div>
                     </div>
                  </div>
                  <div class="inline-block w-full py-2 cursor-pointer">
                     <div class="flex">
                        <img src="data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAABAAAAARCAYAAADUryzEAAAACXBIWXMAAAsTAAALEwEAmpwYAAAAAXNSR0IArs4c6QAAAARnQU1BAACxjwv8YQUAAAFlSURBVHgBzVPLTcNAEJ1ZnDMuwVLgjLcCkgoIFWBXgOiADqADTAWYCuIObG5IECl0sOKEhO1hZv3BbBykKJfMZXdm33z3DcIW8YPcBw8iq3iQmle9HsOhBZ/kMz5mDEwEyM4BHeGSADIFhAR4jhVps9bGxWIHRqRHIrziM2ZAWBOefa7C2CaY5gmnKqCE1MUqKVMM5l3fymmjbxZKbSsbWJSSONpDH3VCc/gCw5nypgUAEqDYSwhcLLYDC9qBZRw9G9gWNnPJ/XL/Y1jsh9KUmEiW8TbsyFP4BtP/DutKSureZapD3RWqcSmwP/rxtKAhyNX/exNdwZ5yGAGy9id2EmZnxAQp0D/NQ57mkyVNRTfABGLixR0feocWxzsxB09dE9ECFV0q86YLMSqkF5gwB4RlNd7Zbeyc+U5Vw8DGUn/Y5RLfLeXd8wZeIGIqOmeLEOjZrHTkYkcD2CC/DBXiFG5LnfwAXIfP0IqO+eQAAAAASUVORK5CYII=" class="w-[16px] h-[16px] mr-[18px] mt-[2px]" alt="">
                        <div class="flex text-body-text2 leading-[22.88px] text-title-text font-OpenSans font-normal">
                           <p class="mr-2">Collaboration Process</p>
                        </div>
                     </div>
                  </div>
                  <div class="inline-block w-full py-2 cursor-pointer">
                     <div class="flex">
                        <svg stroke="currentColor" fill="currentColor" stroke-width="0" viewBox="0 0 16 16" height="16" width="16" xmlns="http://www.w3.org/2000/svg" style="color: rgb(15, 35, 208); margin-right: 18px; margin-top: 2px;">
                           <path fill-rule="evenodd" d="M5 11.5a.5.5 0 0 1 .5-.5h9a.5.5 0 0 1 0 1h-9a.5.5 0 0 1-.5-.5zm0-4a.5.5 0 0 1 .5-.5h9a.5.5 0 0 1 0 1h-9a.5.5 0 0 1-.5-.5zm0-4a.5.5 0 0 1 .5-.5h9a.5.5 0 0 1 0 1h-9a.5.5 0 0 1-.5-.5zM3.854 2.146a.5.5 0 0 1 0 .708l-1.5 1.5a.5.5 0 0 1-.708 0l-.5-.5a.5.5 0 1 1 .708-.708L2 3.293l1.146-1.147a.5.5 0 0 1 .708 0zm0 4a.5.5 0 0 1 0 .708l-1.5 1.5a.5.5 0 0 1-.708 0l-.5-.5a.5.5 0 1 1 .708-.708L2 7.293l1.146-1.147a.5.5 0 0 1 .708 0zm0 4a.5.5 0 0 1 0 .708l-1.5 1.5a.5.5 0 0 1-.708 0l-.5-.5a.5.5 0 0 1 .708-.708l.146.147 1.146-1.147a.5.5 0 0 1 .708 0z"></path>
                        </svg>
                        <div class="flex text-body-text2 leading-[22.88px] text-title-text font-OpenSans font-normal">
                           <p class="mr-2">Get Listed</p>
                        </div>
                     </div>
                  </div>
               </div>
            </li>
            <li class="group relative flex ml-[32px] items-center text-title-text text-body-text2 pt-[30px] pb-[31px] font-OpenSans font-semibold leading-[20.02px]">
               <div class="flex cursor-pointer">
                  <a href="/developer/for-developers"> For Developers</a>
                  <svg stroke="currentColor" fill="currentColor" stroke-width="0" viewBox="0 0 24 24" class="ml-[5px]" height="20" width="20" xmlns="http://www.w3.org/2000/svg">
                     <path fill="none" d="M0 0h24v24H0V0z"></path>
                     <path d="M7.41 8.59L12 13.17l4.59-4.58L18 10l-6 6-6-6 1.41-1.41z"></path>
                  </svg>
               </div>
               <div class="hidden group-hover:block top-[101%] border-t-[1px] border-t-body-text/[0.1] absolute bg-white shadow-xl w-[255px] rounded-b-2xl px-4">
                  <div class="inline-block w-full py-2 cursor-pointer">
                     <div class="flex">
                        <div>
                           <svg stroke="currentColor" fill="currentColor" stroke-width="0" viewBox="0 0 16 16" height="16" width="16" xmlns="http://www.w3.org/2000/svg" style="color: rgb(15, 35, 208); margin-right: 18px; margin-top: 2px;">
                              <path d="M6.5 1A1.5 1.5 0 0 0 5 2.5V3H1.5A1.5 1.5 0 0 0 0 4.5v8A1.5 1.5 0 0 0 1.5 14h13a1.5 1.5 0 0 0 1.5-1.5v-8A1.5 1.5 0 0 0 14.5 3H11v-.5A1.5 1.5 0 0 0 9.5 1h-3zm0 1h3a.5.5 0 0 1 .5.5V3H6v-.5a.5.5 0 0 1 .5-.5zm1.886 6.914L15 7.151V12.5a.5.5 0 0 1-.5.5h-13a.5.5 0 0 1-.5-.5V7.15l6.614 1.764a1.5 1.5 0 0 0 .772 0zM1.5 4h13a.5.5 0 0 1 .5.5v1.616L8.129 7.948a.5.5 0 0 1-.258 0L1 6.116V4.5a.5.5 0 0 1 .5-.5z"></path>
                           </svg>
                        </div>
                        <div class="flex text-body-text2 leading-[22.88px] text-title-text font-OpenSans font-normal">
                           <p class="mr-2">On-demand Remote Jobs</p>
                        </div>
                     </div>
                  </div>
                  <div class="inline-block w-full py-2 cursor-pointer">
                     <div class="flex">
                        <img src="data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAABAAAAAQCAYAAAAf8/9hAAAACXBIWXMAAAsTAAALEwEAmpwYAAAAAXNSR0IArs4c6QAAAARnQU1BAACxjwv8YQUAAAGISURBVHgBpZLdUcJQEIV3b3wVUkIG9NmkAkMF0gF0oFaAVKBUgB2IFQQrSHj2h9hB8D13PXtNQoYBncGducn933O+vUT/DNaP30+HQjzSbjVfWJJnr6RlkUf5bxeY6puLyCfaizY3JTwRj9edfjb3gzSgY8I/S+NuP3tCk05vNaFjAxfdHLqkZjAGgyuqGIhwZqydtf3752kolhNYnH59RA/1vGNghYI2A2YJd/0Xr1GG+Skz37eZ8EHZ2CSGE93BpURQU+g8rCT637yHg0bBvlD5bCUigSWP501GqMAvRgJ/ywADa8w1FmM9i4y3tX+tBJgkWBsUb9HSqehlayGZKQunAFJTbBg7BiQb9a/QnJKfQ0traVircG+F+UL7J6d4hZpIfW6qrPDZxYE7dIfVgRW0BrQll0P6pWPAqAB85u2S6QEm7raR7IybMMZQhhtD9VrzwOYR2OWtfb5a23uBelSyCkpLpP4VrSkd7SoL5YD12Iw9WlTV2L4DVQDfsYE/KmlR1/2v+AbJxNnll+uUvgAAAABJRU5ErkJggg==" class="w-[16px] h-[16px] mr-[18px] mt-[2px]" alt="">
                        <div class="flex text-body-text2 leading-[22.88px] text-title-text font-OpenSans font-normal">
                           <p class="mr-2">Remote Developer Jobs</p>
                        </div>
                     </div>
                  </div>
                  <div class="inline-block w-full py-2 cursor-pointer">
                     <div class="flex">
                        <img src="data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAABIAAAASCAYAAABWzo5XAAAACXBIWXMAAAsTAAALEwEAmpwYAAAAAXNSR0IArs4c6QAAAARnQU1BAACxjwv8YQUAAAEcSURBVHgBrZTdbYMwEMf/51CpL209AlUWgAmqjNAN2hE6UbNB2CDtBPBeIXkEq33pA3A550Ph44hAyV8CG9/5x/nONqElG+f2Xxoouge8d6nHiKgFidnQRkbGnBMyvPI/aaEZo1OnAmJDKH7L5L3vtP/JgnJuaCP9lUTm+j4G0+UlotcQdQBfA0JYlsA+JLptHzYHZB+W+VvNiKVfHGF2LsgzkBHoJTzS95CXZDg5OUSTKIeyd4rw+JyvqfU9K0eXdDOQujQrSW0kF5qNwd9/ZbqeBEKNLxOxU20VLu/sju5g62Zf5oEWgAOGx0gHCYRYB8mMMO6Gw4p8mWbSZJih21ctCtue8fm0LLaTZrLcW9W5INS3ayd7RJ2LbgdbpGEAfK0H7QAAAABJRU5ErkJggg==" class="w-[16px] h-[16px] mr-[18px] mt-[2px]" alt="">
                        <div class="flex text-body-text2 leading-[22.88px] text-title-text font-OpenSans font-normal">
                           <p class="mr-2">Resume Guides</p>
                        </div>
                     </div>
                  </div>
                  <div class="inline-block w-full py-2 cursor-pointer">
                     <div class="flex">
                        <img src="data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAABAAAAAQCAYAAAAf8/9hAAAACXBIWXMAAAsTAAALEwEAmpwYAAAAAXNSR0IArs4c6QAAAARnQU1BAACxjwv8YQUAAADCSURBVHgB7ZPBDcIwDEX/bzlwgoxQYABgA5gARmAE2IANEBMUNmAENmg3oCOEAVpjV0VCVXpAHODAlyzZz7GTww/QUj/JEosQd0nm2pwGqwgbkiutZzUVeBBOhCetPCnbJ2vm8gpyjktcexLzpuBCyBEKfDH3dsLZK2Kk9YJSRi/cKV8QWOvsAcNJLujQYJztLbr6NhvhQ/0X/OSCt61sZlDtQlbWzDd5ErJyBKY9bRQgpyErm1X1H9yVL0NWri/4uh5E7lld7pKAXgAAAABJRU5ErkJggg==" class="w-[16px] h-[16px] mr-[18px] mt-[2px]" alt="">
                        <div class="flex text-body-text2 leading-[22.88px] text-title-text font-OpenSans font-normal">
                           <p class="mr-2">Developer Knowledge Hub</p>
                        </div>
                     </div>
                  </div>
               </div>
            </li>
            <li class="flex group relative items-center ml-[32px] text-title-text text-body-text2 pt-[30px] pb-[31px] font-OpenSans font-semibold leading-[20.02px]">
               <div class="flex cursor-pointer">
                  <a href="/company/for-companies">For Firms</a>
                  <svg stroke="currentColor" fill="currentColor" stroke-width="0" viewBox="0 0 24 24" class="ml-[5px]" height="20" width="20" xmlns="http://www.w3.org/2000/svg">
                     <path fill="none" d="M0 0h24v24H0V0z"></path>
                     <path d="M7.41 8.59L12 13.17l4.59-4.58L18 10l-6 6-6-6 1.41-1.41z"></path>
                  </svg>
               </div>
               <div class="hidden group-hover:block top-[101%] border-t-[1px] border-t-body-text/[0.1] absolute bg-white shadow-xl w-[255px] rounded-b-2xl px-4">
                  <div class="inline-block w-full py-2 cursor-pointer">
                     <div class="flex">
                        <img src="data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAABAAAAAQCAYAAAAf8/9hAAAACXBIWXMAAAsTAAALEwEAmpwYAAAAAXNSR0IArs4c6QAAAARnQU1BAACxjwv8YQUAAADoSURBVHgBjVPdDYIwEL6rviqMUCG+ywiOwATO4AaO4AhuwAiMAD4bY0foAnC2SkmBHumXQHr0vp/+gDBglz8vAuhuhiksobCjs1aFAg5J1n5S2cjQ3D5rbkkenhfjCEGuOgBI2mA9FxEQAYGgOJFtjIB+F480b6An+BONiHkfJk1mjQSR8HvZBOmxOU1SvIo21Cc4MnVYuZp6rOaCrIAj44ZK62ofFFRyIuFTwMA3ZocWe2AdjZNzLH9cL1FUAhd7DMSQgwl8EYhA1E2MFdDcz+Rj6FGuHpeAQFcSWJtbJtcEzGFo2+vqL5eNZ6v7zQ0WAAAAAElFTkSuQmCC" class="w-[16px] h-[16px] mr-[18px] mt-[2px]" alt="">
                        <div class="flex text-body-text2 leading-[22.88px] text-title-text font-OpenSans font-normal">
                           <p class="mr-2">Hire Verified Developers</p>
                        </div>
                     </div>
                  </div>
                  <div class="inline-block w-full py-2 cursor-pointer">
                     <div class="flex">
                        <img src="data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAABAAAAAQCAYAAAAf8/9hAAAACXBIWXMAAAsTAAALEwEAmpwYAAAAAXNSR0IArs4c6QAAAARnQU1BAACxjwv8YQUAAAGKSURBVHgBpVLRUcJAEN29Q+EDISUE8B/SQTpAO4AKSAcMFQgVgBWIFYgVXPg3mFRgAD/CjLl1I8lMGA91xszc3WZv793bdw/gnx8WQd1WLkqwf6xOId6HzvIbQKO9vgMkC4iiX66zeaJd0Bue5Jsd/w3++DXbvrJsZRX/lXyNs6l+rVypcW46qJEm+8BZMIs4wWqzOFMpF72/OCteWtkNCYBV3ktCJzQBV8CcHVQJ++VUraNmceAsiWhdo8M2yfNfIrIGr9ug1yofyFikEm5M+DKFVZwzEqaC7ElJokIC2zRI4FOjrbyzLUiJI6Y6222cqWn/ylY+e2bA4dSsAXeAiP1Gx++KlCYF3awtLcQYgVzIX0GcAYCDvhwIoGem+8BGG/MYcayE0BFqui3qCgZh1pPW4HMipDzJqi/41hVJ8gSy4B/gxBsn5px9AoApDUmAJyR2AeiRNEU1eWjxU0U5fe+E3gV7RB9DNArAjiTCOQt5b9pnMn125ixzphEgF8wGCS6YEcL46Fr4BO+IpyeXKYFdAAAAAElFTkSuQmCC" class="w-[16px] h-[16px] mr-[18px] mt-[2px]" alt="">
                        <div class="flex text-body-text2 leading-[22.88px] text-title-text font-OpenSans font-normal">
                           <p class="mr-2">Job Description Template</p>
                        </div>
                     </div>
                  </div>
                  <div class="inline-block w-full py-2 cursor-pointer">
                     <div class="flex">
                        <img src="data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAABAAAAAQCAYAAAAf8/9hAAAACXBIWXMAAAsTAAALEwEAmpwYAAAAAXNSR0IArs4c6QAAAARnQU1BAACxjwv8YQUAAAGdSURBVHgBxZPdTeNAEMfnP47Ew4nDJVige8buIFfBpQOOCgIVABUkVEBSAVAB6cDhnQ9TAQZeEEp2+M9iBxBEPCFGsr07s/Obr7XITwvaRZqVaUgwoKLnezOM7q82d78CdNpF49yF2Lbz+Oz9Xi/v7q+K/SZAFlT7gOVBbPxwWYwWAI9uIv8xt6KuiqnrVjfKWgVHXEaAKc4Ir83sVIEB4SnhQ20r8NcjVm7bjGwudav36Cw2Q7Btz4iQMfddt0UAo1b8TFb0aeiHf2VlniiOmNWo4TmsDipdzxbAJtt3uwDEbs5Zu0luCa47CUpGqHRuB02AmrUf0HFAuztmre2DpH/KPKb8mY3R3f5Wh7a7Aks/JZrdaJDhrCO5GrZe9ag1hENtutuVJQLBFtM+7sxk+k7PcZqXurYxtdWs7C0DcFw7a+vT8qP+vE/fa78HEyT4x+/Jkgz6BpksSpVw9zIF68XGelMs4IwTqALskPOv3FFVck+fhJQT+hvLTuLF4lFOCDauL4pJ/BciPZF9GMmQly4TCOWFmcnQxyjfJc+gsbWUC/eH8QAAAABJRU5ErkJggg==" class="w-[16px] h-[16px] mr-[18px] mt-[2px]" alt="">
                        <div class="flex text-body-text2 leading-[22.88px] text-title-text font-OpenSans font-normal">
                           <p class="mr-2">Recruitment Resources</p>
                        </div>
                     </div>
                  </div>
                  <div class="inline-block w-full py-2 cursor-pointer">
                     <div class="flex">
                        <img src="data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAABAAAAAQCAYAAAAf8/9hAAAACXBIWXMAAAsTAAALEwEAmpwYAAAAAXNSR0IArs4c6QAAAARnQU1BAACxjwv8YQUAAACpSURBVHgB7ZLBEQFBEEV/zziqJQPKJmAyIIINQcmACEhBBFsyIQIjAGpEYARg2i6zZbE1c3Ddd+o+/Nd9+ARPMjquiHgBhkUEAm/tWa1fs6eX6ivdWbGkPBS+ncbTT9lbwAVL56ARoQMYa5Txc81GlEmJLJhm9B09j8x/BN/vNdEdHiZC0qzaBf6kFbSCknoTd0mqczBfggmiQeMHZY0FeI8YxQEheFOtD5aWMr0PC9ubAAAAAElFTkSuQmCC" class="w-[16px] h-[16px] mr-[18px] mt-[2px]">
                        <div class="flex text-body-text2 leading-[22.88px] text-title-text font-OpenSans font-normal">
                           <p class="mr-2">Hiring Process</p>
                        </div>
                     </div>
                  </div>
               </div>
            </li>
         </ul>
      </div>
      <div class="flex items-center xl2:mt-[22px] xl2:mb-[23px]">
         <div class="flex mr-[13px] md:mr-0 xl:hidden">
            <div>
               <button class="MuiButtonBase-root MuiButton-root MuiButton-text MuiButton-textPrimary MuiButton-sizeMedium MuiButton-textSizeMedium MuiExample_Component-menu_bar css-1ujsas3" tabindex="0" type="button">
                  <svg stroke="currentColor" fill="none" stroke-width="2" viewBox="0 0 24 24" stroke-linecap="round" stroke-linejoin="round" height="18" width="18" xmlns="http://www.w3.org/2000/svg">
                     <line x1="3" y1="12" x2="21" y2="12"></line>
                     <line x1="3" y1="6" x2="21" y2="6"></line>
                     <line x1="3" y1="18" x2="21" y2="18"></line>
                  </svg>
                  <span class="MuiTouchRipple-root css-w0pj6f"></span>
               </button>
               <div class="PrivateSwipeArea-root css-x15wq9" style="width:20px;"></div>
            </div>
         </div>
         <div class="text-primary-1 text-center relative group overflow-hidden px-4 py-2 text-body-text1 mr-[13px] cursor-pointer hover:bg-[#0f23d00a] font-OpenSans font-semibold items-center justify-center rounded hidden md:flex"><a href="https://higate.io/remote-developer-jobs">Find Jobs<span class="absolute w-0 h-0 transition-all duration-500 ease-in-out bg-[#0f23d04d] rounded-full group-active:w-40 group-active:h-40 opacity-10"></span></a></div>
         <div class="w-[155px] h-[40px] relative group overflow-hidden text-center cursor-pointer text-secondary hover:bg-[#0B1992] active:bg-primary-1 text-body-text1 font-OpenSans font-semibold bg-primary-1 items-center justify-center rounded hidden md:flex"><a href="https://console.higate.io/f/your-post-p">Hire Candidates<span class="absolute w-0 h-0 transition-all duration-500 ease-in-out bg-white rounded-full group-active:w-40 group-active:h-40 opacity-10"></span></a></div>
      </div>
   </div>
</div>
</template>
  
<script>
export default {
    name: 'Menu'
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.bg-primary-1 {
    --tw-bg-opacity: 1;
    background-color: rgb(15 35 208/var(--tw-bg-opacity));
}
.text-button-secondary, 
.text-secondary {
    --tw-text-opacity: 1;
    color: rgb(255 255 255/var(--tw-text-opacity));
}
.hover\:bg-\[\#0B1992\]:hover {
    --tw-bg-opacity: 1;
    background-color: rgb(11 25 146/var(--tw-bg-opacity));
}
</style>
