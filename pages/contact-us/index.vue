<template>
  <div>
    <layout-container no-back>
      <diV>
        <img src="../../assets/images/iklan.jpg" class="w-full" />
        <div>
          <h1 class="font-serif text-center text-xl font-bold mt-20">
            Keep in touch with us
          </h1>
        </div>
        <div>
          <p class="text-center mt-3 text-gray-500">
            We,re talking about clean beauty gift sets, of course - and we've
            got a bouquet of
          </p>
        </div>
        <div>
          <p class="text-center mt-2 text-gray-500">
            beauties for yourself or someone you love
          </p>
        </div>

        <div class="flex justify-center ...">
          <div>
            <img src="../../assets/images/dekorline.png" class="mt-10" />
          </div>
        </div>

        <div class=" mt-10 grid-cols-3 flex justify-center ">
          <div>
            <img src="../../assets/images/lokasi.png" class="w-40	"/>
            <h1 class="font-serif  font-semibold text-xs text-center">Store Location</h1>
            <h1 class=" text-gray-500 text-xs	">
              Address: 25 West 21th Street
            </h1>
          </div>
          <div >
            <img src="../../assets/images/telepon.png" class="w-30	"/>
            <h1 class="font-serif font-semibold text-center">
              Contact
            </h1>
            <h1 class="text-gray-500 text-xs">Hotline: 1900 26886</h1>
            <h1 class="text-gray-500 text-xs">E-mail: info@harashop.com</h1>
          </div>
          <div >
            <img src="../../assets/images/waktu.png" class="w-30	"/>
            <h1 class="font-serif font-semibold text-center">Open Hours</h1>
            <h1 class="text-gray-500 text-xs">Monday - Saturday: 8:00 am - 4:-00pm</h1>
            <h1 class="text-gray-500 text-xs">Sunday: Close</h1>
          </div>
        </div>
      </diV>

      <div class="ml0 mt-20 flex justify-center ...">
        <iframe
          src="https://www.google.com/maps/embed?pb=!1m18!1m12!1m3!1d990.0711638738159!2d110.30176333328582!3d-6.975703329768679!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x2e705fdc0235654d%3A0x97b3afe1b2104e70!2sSMK%20Bina%20Nusantara%20Semarang!5e0!3m2!1sid!2sid!4v1655524938913!5m2!1sid!2sid"
          width="1140"
          height="400"
          style="border: 0"
          allowfullscreen=""
          loading="lazy"
          referrerpolicy="no-referrer-when-downgrade"
        ></iframe>
      </div>
      <div >
        <h1 class="font-serif text-xl font-semibold mt-20  flex justify-center ...  ">
          Send Message
        </h1>
      </div>
      <div>
        <h1 class="text-gray-500  mt-3 flex justify-center ...">
          Fill out this form and our specialists will contact you shortly for
          detailed consultation.
        </h1>
      </div>
      <div class="  flex justify-center ...">
        <div class=" ml-2 mt-10 w-96">
          <b-field>
            <input class="bg-gray-200 w-96 p-3 flex justify-center ... w-11/12	" placeholder="Your Name *" />
          </b-field>
        </div>
        <div class="  mt-10 w-96">
          <b-field>
            <input class="bg-gray-200 w-96 p-3 flex justify-center ... w-11/12	" placeholder="Your Email *" />
          </b-field>
        </div>
      </div>
      <div class=" mt-10 flex justify-center ... ">
        <b-field class="w-9/12">
          <b-input
          
            placeholder="Comment"
            maxlength="200"
            type="textarea"
          ></b-input>
        </b-field>
      </div>

      <div class="grid grid-flow-row auto-rows-max">
        <div class="justify-self-center">
          <b-button type="is-success" class="bg-teal-800">Submit</b-button>
        </div>
      </div>
    </layout-container>
  </div>
</template>