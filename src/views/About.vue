<template>
  <div class="about">
    <transition
     appear 
     name="fade"
     @before-enter="beforeEnter"
     @enter="enter"
     >
      <h1 >About</h1>
    </transition>
    <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Cum aperiam officia possimus delectus inventore quod quisquam culpa voluptas iusto, quae maiores quo dolorum, corporis laboriosam a dolore consequatur assumenda nam!</p>
    <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Cum aperiam officia possimus delectus inventore quod quisquam culpa voluptas iusto, quae maiores quo dolorum, corporis laboriosam a dolore consequatur assumenda nam!</p>
    <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Cum aperiam officia possimus delectus inventore quod quisquam culpa voluptas iusto, quae maiores quo dolorum, corporis laboriosam a dolore consequatur assumenda nam!</p>
  </div>
  <div class="content" ref="content">
    <h1>Headling Goes Here </h1>
    <p>
      Lorem ipsum dolor sit amet consectetur adipisicing elit. Totam delectus officia dolorem obcaecati voluptate accusamus sed id omnis asperiores voluptatibus. Corrupti excepturi fuga iusto quis iste sint nulla vel rem.
    </p>
  </div>
</template>

<script>
import { ref,onMounted } from 'vue'
import gsap from 'gsap'

export default {

  setup() {
    const content = ref(null)
    const beforeEnter = (el)=>{
      
    }

    onMounted(() => {
      gsap.from(content.value,{
        delay:0.5,
        duration:1,
        y:"+100",
        autoAlpha:0,
        ease:"back.out(1.7)"
      })
    });

    const enter = (el,done)=>{
      
    }
    return {beforeEnter,enter,content}
  }
}
</script>

<style>
  
  .about {
    max-width: 600px;
    margin: 20px auto;
  }
</style>