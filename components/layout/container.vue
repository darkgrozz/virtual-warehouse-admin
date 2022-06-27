<template>
  <div class="flex overflow-hidden min-h-screen flex-row  ">
    <!-- <layout-sidebar :mobile-opened="sidebarMobileOpened" /> -->
    <div
      style="background-color: white "
      class="flex max-h-screen flex-col w-full"
    >
      <layout-appbar @onmenuclickedmobile="onmenuclickedmobile" />
      <div
        v-if="sidebarMobileOpened"
        @click="sidebarMobileOpened = false"
        style="z-index: 2; top: 60px"
        class="w-full fixed opacity-50 left-0 right-0 bottom-0 bg-black"
      ></div>
      <div class="flex flex-col overflow-auto">
        <div class="p-4">
          <div
            v-if="navTitle"
            class="w-full rounded-md flex flex-row items-center  py-3 px-4 "
          >
            <button @click="onNavBack" v-if="!noBack" class="rounded-full">
              <b-icon class="hover:text-black" icon="arrow-left"></b-icon>
            </button>
            <span class="ml-3 text-xl font-normal">{{ navTitle }}</span>
          </div>
          <div class="flex-col mt-2 p-2 flex rounded-lg bg-white ">

          <slot />
        </div>
        </div>
        <div>
        <footer class="bg-[#004338] text-white">
          <div class="p-20">
            <div class="grid lg:grid-cols-4 md:grid-cols-2  gap-4">
              <div class="row-pertama">
                <div class="judul-footer1 font-semibold text-lg font-serif">
                  Contact Us
                </div>
                <div class="isi-footer1 mt-5">
                  <ul>
                    <li>
                      <span class="text-sm font-thin opacity-70">if you have any question, please contact us at <a class="text-white hover:text-white" href="#"><u>support@example.com</u></a></span>
                    </li>
                    <li class="mt-5">
                      <span class="text-sm font-semibold">CALL US FREE</span>
                      <div class="text-2xl">088-767-6555</div>
                    </li>
                    <li class="mt-5">
                      <span class="text-sm font-thin flex">
                      <div class="mr-5"><svg xmlns="http://www.w3.org/2000/svg" width="16" height="16" fill="currentColor" class="bi bi-facebook" viewBox="0 0 16 16">
                      <path d="M16 8.049c0-4.446-3.582-8.05-8-8.05C3.58 0-.002 3.603-.002 8.05c0 4.017 2.926 7.347 6.75 7.951v-5.625h-2.03V8.05H6.75V6.275c0-2.017 1.195-3.131 3.022-3.131.876 0 1.791.157 1.791.157v1.98h-1.009c-.993 0-1.303.621-1.303 1.258v1.51h2.218l-.354 2.326H9.25V16c3.824-.604 6.75-3.934 6.75-7.951z"/>
                      </svg></div>
                      <div class="mr-5"><svg xmlns="http://www.w3.org/2000/svg" width="16" height="16" fill="currentColor" class="bi bi-twitter" viewBox="0 0 16 16">
                      <path d="M5.026 15c6.038 0 9.341-5.003 9.341-9.334 0-.14 0-.282-.006-.422A6.685 6.685 0 0 0 16 3.542a6.658 6.658 0 0 1-1.889.518 3.301 3.301 0 0 0 1.447-1.817 6.533 6.533 0 0 1-2.087.793A3.286 3.286 0 0 0 7.875 6.03a9.325 9.325 0 0 1-6.767-3.429 3.289 3.289 0 0 0 1.018 4.382A3.323 3.323 0 0 1 .64 6.575v.045a3.288 3.288 0 0 0 2.632 3.218 3.203 3.203 0 0 1-.865.115 3.23 3.23 0 0 1-.614-.057 3.283 3.283 0 0 0 3.067 2.277A6.588 6.588 0 0 1 .78 13.58a6.32 6.32 0 0 1-.78-.045A9.344 9.344 0 0 0 5.026 15z"/>
                      </svg></div>
                      <div class="mr-5"><svg xmlns="http://www.w3.org/2000/svg" width="16" height="16" fill="currentColor" class="bi bi-instagram" viewBox="0 0 16 16">
                      <path d="M8 0C5.829 0 5.556.01 4.703.048 3.85.088 3.269.222 2.76.42a3.917 3.917 0 0 0-1.417.923A3.927 3.927 0 0 0 .42 2.76C.222 3.268.087 3.85.048 4.7.01 5.555 0 5.827 0 8.001c0 2.172.01 2.444.048 3.297.04.852.174 1.433.372 1.942.205.526.478.972.923 1.417.444.445.89.719 1.416.923.51.198 1.09.333 1.942.372C5.555 15.99 5.827 16 8 16s2.444-.01 3.298-.048c.851-.04 1.434-.174 1.943-.372a3.916 3.916 0 0 0 1.416-.923c.445-.445.718-.891.923-1.417.197-.509.332-1.09.372-1.942C15.99 10.445 16 10.173 16 8s-.01-2.445-.048-3.299c-.04-.851-.175-1.433-.372-1.941a3.926 3.926 0 0 0-.923-1.417A3.911 3.911 0 0 0 13.24.42c-.51-.198-1.092-.333-1.943-.372C10.443.01 10.172 0 7.998 0h.003zm-.717 1.442h.718c2.136 0 2.389.007 3.232.046.78.035 1.204.166 1.486.275.373.145.64.319.92.599.28.28.453.546.598.92.11.281.24.705.275 1.485.039.843.047 1.096.047 3.231s-.008 2.389-.047 3.232c-.035.78-.166 1.203-.275 1.485a2.47 2.47 0 0 1-.599.919c-.28.28-.546.453-.92.598-.28.11-.704.24-1.485.276-.843.038-1.096.047-3.232.047s-2.39-.009-3.233-.047c-.78-.036-1.203-.166-1.485-.276a2.478 2.478 0 0 1-.92-.598 2.48 2.48 0 0 1-.6-.92c-.109-.281-.24-.705-.275-1.485-.038-.843-.046-1.096-.046-3.233 0-2.136.008-2.388.046-3.231.036-.78.166-1.204.276-1.486.145-.373.319-.64.599-.92.28-.28.546-.453.92-.598.282-.11.705-.24 1.485-.276.738-.034 1.024-.044 2.515-.045v.002zm4.988 1.328a.96.96 0 1 0 0 1.92.96.96 0 0 0 0-1.92zm-4.27 1.122a4.109 4.109 0 1 0 0 8.217 4.109 4.109 0 0 0 0-8.217zm0 1.441a2.667 2.667 0 1 1 0 5.334 2.667 2.667 0 0 1 0-5.334z"/>
                      </svg></div>
                      <div class="mr-5"><svg xmlns="http://www.w3.org/2000/svg" width="16" height="16" fill="currentColor" class="bi bi-youtube" viewBox="0 0 16 16">
                      <path d="M8.051 1.999h.089c.822.003 4.987.033 6.11.335a2.01 2.01 0 0 1 1.415 1.42c.101.38.172.883.22 1.402l.01.104.022.26.008.104c.065.914.073 1.77.074 1.957v.075c-.001.194-.01 1.108-.082 2.06l-.008.105-.009.104c-.05.572-.124 1.14-.235 1.558a2.007 2.007 0 0 1-1.415 1.42c-1.16.312-5.569.334-6.18.335h-.142c-.309 0-1.587-.006-2.927-.052l-.17-.006-.087-.004-.171-.007-.171-.007c-1.11-.049-2.167-.128-2.654-.26a2.007 2.007 0 0 1-1.415-1.419c-.111-.417-.185-.986-.235-1.558L.09 9.82l-.008-.104A31.4 31.4 0 0 1 0 7.68v-.123c.002-.215.01-.958.064-1.778l.007-.103.003-.052.008-.104.022-.26.01-.104c.048-.519.119-1.023.22-1.402a2.007 2.007 0 0 1 1.415-1.42c.487-.13 1.544-.21 2.654-.26l.17-.007.172-.006.086-.003.171-.007A99.788 99.788 0 0 1 7.858 2h.193zM6.4 5.209v4.818l4.157-2.408L6.4 5.209z"/>
                      </svg></div></span>
                    </li>
                  </ul>
                </div>
              </div>
              <div class="row-kedua">
                <div class="judul-footer2 font-semibold text-lg font-serif">
                  Store Location
                </div>
                <div class="isi-footer2 mt-5">
                  <ul>
                    <li>
                      <span class="text-sm font-thin opacity-70">Addres: 25 West 21th Street, Miami FL, USA</span>
                    </li>
                    <li>
                      <div class="judul-footer2 font-semibold text-lg font-serif mt-5">
                      Open Hourse
                      </div>
                    </li>
                    <li>
                      <div class="text-sm font-thin opacity-70 mt-5">
                      Monday-Saturday: 8:00 am - 4:00 pm<br />
                      Sunday: Close
                      </div>
                    </li>
                  </ul>
                </div>
              </div>
              <div class="row-ketiga">
                <div class="judul-footer3 font-semibold text-lg font-serif">
                  Quick Links
                </div>
                <div class="isi-footer3 mt-5">
                  <ul>
                    <li>
                      <span class="text-sm font-thin opacity-70">Shipping & Retruns</span>
                    </li>
                    <li>
                      <span class="text-sm font-thin opacity-70">Privacy Policy</span>
                    </li>
                    <li>
                      <span class="text-sm font-thin opacity-70">Term  Of Use</span>
                    </li>
                    <li>
                      <span class="text-sm font-thin opacity-70">Wishlist</span>
                    </li>
                    <li>
                      <span class="text-sm font-thin opacity-70">Compare</span>
                    </li>
                    <li>
                      <span class="text-sm font-thin opacity-70">Subscribe</span>
                    </li>
                  </ul>
                </div>
              </div>
              <div class="row-keempat">
                <div class="judul-footer3 font-semibold text-lg font-serif">
                  Sign Up For Our Newsletter
                </div>
                <div class="isi-footer3 mt-5">
                  <ul>
                    <li>
                      <span class="text-sm font-thin opacity-70">Leave your email to get all hot deals & news which benefit you most!</span>
                    </li>
                    <li class="mt-5">
                      <span class="text-sm font-thin opacity-70"><b-field>
                      <b-input placeholder="Your email address..."
                       type="email"
                       icon="email">
                      </b-input>
                      </b-field></span>
                    </li>
                    <li class="mt-3">
                      <!-- <div class="flex">
                      <div class="ml-2"><img class="w-10" src="https://cdn.vox-cdn.com/thumbor/ODlqn8V2j0KyYyBhKek2UuaysOQ=/0x260:1000x760/fit-in/1200x600/cdn.vox-cdn.com/uploads/chorus_asset/file/13674554/Mastercard_logo.jpg" alt="Logo Master Card"></div>
                      <div class="ml-2"><img class="w-10" src="https://image.cermati.com/q_70/v1431504749/ogxuwgtitfwxavibahws.jpg" alt="Logo Visa"></div>
                      <div class="ml-2"><img class="w-10" src="https://images.fastcompany.net/image/upload/w_596,c_limit,q_auto:best,f_auto/wp-cms/uploads/2018/04/4-you-might-not-notice-amex-new-brand.jpg" alt="Logo Amex"></div>
                      <div class="ml-2"><img class="w-10" src="https://cdn.pixabay.com/photo/2018/05/08/21/29/paypal-3384015_1280.png" alt="Logo Paypal"></div>
                      <div class="ml-2"><img class="w-10" src="https://mma.prnewswire.com/media/1224083/Clearpay_Logo.jpg?w=200" alt="Logo Clear pay"></div>
                      </div> -->
                    </li>
                  </ul>
                </div>
              </div>
            </div>
          </div>
        </footer>
        <div class="footerkedua bg-[#005f54]">
          <div class="py-4">
            <div class="grid grid-cols-2 gap-4 text-center place-content-between">
              <div class="text-white text-sm">copyright c 2021 Hara. All Rights Reserved.</div>
              <div class="text-white text-sm">
                <ul>
                  <div class="inline-flex">
                  <li class="ml-5">About us</li>
                  <li class="ml-5">FAQs</li>
                  <li class="ml-5">Blod</li>
                  </div>
                </ul>
              </div>
            </div>
          </div>
        </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script lang="ts">
import Vue from "vue";
import Component from "vue-class-component";
import { Watch, Prop } from "vue-property-decorator";

@Component
export default class LayoutContainer extends Vue {
  @Prop({ type: [Boolean], default: false })
  noBack!: boolean;
  @Prop({ type: [String] })
  navTitle!: string;

  onNavBack() {
    this.$router.back();
  }

  sidebarMobileOpened = true;
  onmenuclickedmobile() {
    this.sidebarMobileOpened = !this.sidebarMobileOpened;
  }
  windowWidth = null as any;

  @Watch("windowWidth")
  resizeHandler(newVal: any) {
    if (newVal > 1140) {
      this.sidebarMobileOpened = false;
    }
  }

  onResize() {
    this.windowWidth = window.innerWidth;
  }

  mounted() {
    this.$nextTick(() => {
      this.windowWidth = this.windowWidth = window.innerWidth;
      window.addEventListener("resize", this.onResize);
    });
  }
}
</script>
