<template>
  <section id="contact" class="w-full">
    <div class="max-w-7xl mx-auto px-4 md:px-16 py-14">
      <div class="flex flex-col md:flex-row items-center space-y-10 md:space-y-0">
        <!-- Contact info -->
        <div class="w-full md:w-1/2 space-y-2">
          <div class="text-4xl md:text-5xl font-black">Биз билан боғланиш
          </div>
          <div class="text-lg font-semibold text-dark-l-6">Биз билан оссон, тез ва иҳтиёрий вақтда боғланинг</div>
          <div class="space-y-1 pt-5">
            <a :href="`tel:${number}`" class="group">
              <div class="flex items-center">
                <AppIcon left name="phone-alt" color="primary" />
                <span class="text-dark-l-6 font-semibold group-hover:text-primary">{{ number }}</span>
              </div>
            </a>
            <a :href="`mailto:${email}`" class="group">
              <div class="flex items-center">
                <AppIcon left name="envelope" color="primary" />
                <span class="text-dark-l-6 font-semibold group-hover:text-primary">{{ email }}</span>
              </div>
            </a>
          </div>
        </div>
        <!-- Contact form -->
        <div class="w-screen md:w-1/2 z-0">
          <div class=" md:rounded-xl md:ml-10 ml-0 relative w-full border-gray-500">


              <div class=" w-full  rounded-md border-gray-700 px-4 ">
                <iframe class=" w-full rounded-md h-96"
                  src="https://maps.google.com/maps?height=600&amp;&amp;hl=en&amp;q=NEXT&amp;t=k&amp;z=14&amp;ie=UTF8&amp;iwloc=B&amp;output=embed">
                </iframe>
              </div>




            <!--
            <div class="invisible md:visible absolute -z-1 border-2 border-primary rounded-lg h-full w-full transform -rotate-3">
            </div>

            <form>
              <div class="h-full md:px-10 md:py-16 mx-4 py-10 space-y-6">
                <AppTextInput dark label="Name" placeholder="What's your full name?" />
                <AppTextInput dark label="Email" type="email" placeholder="me@company.com" />
                <AppTextInput dark label="Subject" placeholder="How can we help you?" />
                <AppTextInput dark form="textarea" label="Message" placeholder="Write your message" />
                <div class="pt-2">
                  <AppButton type="submit" large block>Send</AppButton>
                </div>
              </div>
            </form> -->
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  name: 'Contact',

  data: () => ({
    number: '+1 (520) 555-3894',
    email: 'support@example.com'
  })
}
</script>

<style scoped >
/* .mapouter {
  position: relative;
  text-align: right;

}

.gmap_canvas {
  overflow: hidden;
  background: none !important;

}

.gmap_iframe {

} */
</style>
