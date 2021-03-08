<template>
  <div class="about">
    <!-- <transition
      appear
      name="fade"
      @before-enter="beforeEnter"
      @enter="enter"
      @after-enter="afterEnter"
      @before-leave="beforeLeave"
      @leave="leave"
      @afterLeave="afterLeave"
    >
      <h1 v-if="showTitle">About</h1>
    </transition> -->
    <transition
      appear
      @before-enter="beforeEnter"
      @enter="enter"
      @after-enter="afterEnter"
    >
      <h1>About</h1>
    </transition>
    <p>This to do list is made using Vue.js. it was made to make your list of to do's in day to day basis. You can input your to do's in your to do list and delete this once you accomplish and finish your to do's.</p>
    <p>Making to do list is reminding you to do something important and knowing your priorities to accomplish. Helps you make task and finish things thats important to make. Making to do list will gives you time to make things really matters first.</p>
    <p>Making your to do's more fun and easy. With the help of animation with good User Interface and will have good User Experience.</p>
  </div>
</template>

<script>
import { ref } from 'vue'
import gsap from 'gsap'

export default {
  setup() {
      const beforeEnter = (el) => {
        console.log('before enter - set initial state')
        el.style.transform = 'translateY(-60px)'
        el.style.opacity = 0
      }
      const enter = (el, done) => {
        console.log('starting to enter - make transition')
        gsap.to(el, {
          duration: 3,
          y: 0,
          opacity: 1,
          ease: 'bounce.out',
          onComplete: done
        }) 
      }
      const afterEnter = () => {
        console.log('after enter')
      }
      return { beforeEnter, enter, afterEnter }
    }
  //   const showTitle = ref(true)

  //   const beforeEnter = (el) => {
  //     console.log('before enter', el)
  //   }
  //   const enter = (el) => { 
  //     console.log('enter', el)
  //   }
  //   const afterEnter = (el) => {
  //     el.style.color = 'green'
  //     console.log('after enter', el)

  //     setTimeout(() => showTitle.value = false, 2000)
  //   }
  //   const beforeLeave = (el) => {
  //     el.style.color = 'pink'
  //     console.log('before leave', el)
  //   }
  //   const leave = (el) => { 
  //     console.log('leave', el)
  //   }
  //   const afterLeave = (el) => {
  //     console.log('after leave', el)
  //   }
  //   return { showTitle, beforeEnter, enter, afterEnter, beforeLeave, leave, afterLeave }

  // }
}
</script>

<style>
  .about {
    max-width: 600px;
    margin: 20px auto;
  }
  /* .fade-enter-from
  {
    opacity: 0;
  }
  .fade-enter-active
  {
    transition: opacity 3s ease;
  }
  .fade-leave-to
  {
    opacity: 0;
  }
  .fade-leave-active
  {
    transition: opacity 3s ease;
  } */
</style>