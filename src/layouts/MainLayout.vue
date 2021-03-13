<template>
  <q-layout view="lHh Lpr lFf">
    <q-page-container>
      <router-view />
    </q-page-container>
  </q-layout>
</template>

<script>
import EssentialLink from 'components/EssentialLink.vue'

const linksData = [
  {
    title: 'Docs',
    caption: 'quasar.dev',
    icon: 'school',
    link: 'https://quasar.dev'
  },
  {
    title: 'Github',
    caption: 'github.com/quasarframework',
    icon: 'code',
    link: 'https://github.com/quasarframework'
  },
  {
    title: 'Discord Chat Channel',
    caption: 'chat.quasar.dev',
    icon: 'chat',
    link: 'https://chat.quasar.dev'
  },
  {
    title: 'Forum',
    caption: 'forum.quasar.dev',
    icon: 'record_voice_over',
    link: 'https://forum.quasar.dev'
  },
  {
    title: 'Twitter',
    caption: '@quasarframework',
    icon: 'rss_feed',
    link: 'https://twitter.quasar.dev'
  },
  {
    title: 'Facebook',
    caption: '@QuasarFramework',
    icon: 'public',
    link: 'https://facebook.quasar.dev'
  },
  {
    title: 'Quasar Awesome',
    caption: 'Community Quasar projects',
    icon: 'favorite',
    link: 'https://awesome.quasar.dev'
  }
];

export default {
  name: 'MainLayout',
  components: { EssentialLink },
  data () {
    return {
      leftDrawerOpen: false,
      essentialLinks: linksData
    }
  },
  mounted(){
    const root = document.querySelector('#q-app')
    const shot = document.querySelector('.shot')
    const follower = document.querySelector('.follower')
    const lulu = document.querySelector('.lulu')
    root.addEventListener('mousemove', (e) => {
      setPosition( e)
    });
    root.addEventListener('touchmove', (e) => {
      setPosition( e)
    });
    root.addEventListener('touchstart', (e) => {
      setPosition( e)
    });
    root.addEventListener('click', (e) => {
      shotting( e)
    });
    TweenMax.set(follower, {rotationY: -180, y: 10})
    TweenMax.to(follower, 1, {
      rotationY: -180,
      y:-10,
      repeat:-1,
      ease: Power2.easeInOut
    })
    TweenMax.set(lulu, {rotationY: -180, y: 10})
    TweenMax.to(lulu, 10, {
        duration: 1,
        left: 0,
        rotation: 0
      },
    );

    function setPosition( e) {
      let x = e.clientX;
      let y = e.clientY;

      if(e.touches&&e.touches[0]){
        x = e.touches[0].clientX;
        y = e.touches[0].clientY;
      }
      TweenMax.to(
        follower,
        1,
        {
          left:x-follower.width/2+"px",
          top:y-follower.height/2+"px",
          ease: "sine.out"
        },
      );
      TweenMax.to(
        shot,
        1,
        {
          left:x+"px",
          top:y+"px"
        },
      );
      // element.style.transform = `translate3d(${e.clientX}px, ${e.clientY}px, 0)`
    }
    function shotting( e) {
      console.log(e);
        let x = e.clientX;
        let y = e.clientY;

        if(e.touches&&e.touches[0]){
          x = e.touches[0].clientX;
          y = e.touches[0].clientY;
        }
        console.log(shot);
        TweenMax.to(
          shot,
          1,
          {
            duration: 1,
            left: window.innerWidth,
            rotation: 0
          },
        );
    }
  }
}
</script>
