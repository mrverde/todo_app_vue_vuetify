<template>
  <div class="about pa-16">
    <h1>About {{ appTitle }}</h1>
    <p>
      Lorem ipsum dolor sit amet, consectetur adipiscing elit. Proin posuere
      diam a augue bibendum gravida. Morbi eu est elit. Aliquam erat volutpat.
      Vestibulum pharetra sed elit non porta. Quisque sodales odio vitae tempus
      convallis. Pellentesque tristique blandit diam, in sagittis orci mattis
      at. Sed ac quam justo. Donec ultrices massa ac massa consequat dignissim
    </p>
    <p>
      Lorem ipsum dolor sit amet, consectetur adipiscing elit. Proin posuere
      diam a augue bibendum gravida. Morbi eu est elit. Aliquam erat volutpat.
      Vestibulum pharetra sed elit non porta. Quisque sodales odio vitae tempus
      convallis. Pellentesque tristique blandit diam, in sagittis orci mattis
      at. Sed ac quam justo. Donec ultrices massa ac massa consequat dignissim
    </p>
    <p>
      Lorem ipsum dolor sit amet, consectetur adipiscing elit. Proin posuere
      diam a augue bibendum gravida. Morbi eu est elit. Aliquam erat volutpat.
      Vestibulum pharetra sed elit non porta. Quisque sodales odio vitae tempus
      convallis. Pellentesque tristique blandit diam, in sagittis orci mattis
      at. Sed ac quam justo. Donec ultrices massa ac massa consequat dignissim
    </p>
    <p>
      Lorem ipsum dolor sit amet, consectetur adipiscing elit. Proin posuere
      diam a augue bibendum gravida. Morbi eu est elit. Aliquam erat volutpat.
      Vestibulum pharetra sed elit non porta. Quisque sodales odio vitae tempus
      convallis. Pellentesque tristique blandit diam, in sagittis orci mattis
      at. Sed ac quam justo. Donec ultrices massa ac massa consequat dignissim
    </p>
  </div>
</template>

<script>
export default {
  computed: {
    appTitle() {
      return process.env.VUE_APP_TITLE;
    },
  },
};
</script>
