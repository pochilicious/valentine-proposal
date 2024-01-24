<template>
  <div class="min-w-screen h-screen  bg-pink-300">
    <ProposalModel></ProposalModel>
  </div>
  <svg v-for="heart in 200" :key="heart" :style="randomizeHeartStyle()" viewBox="0 0 33 32">
    <g>
      <path d="M0.256 12.16q0.544 2.080 2.080 3.616l13.664 14.144 13.664-14.144q1.536-1.536 2.080-3.616t0-4.128-2.080-3.584-3.584-2.080-4.16 0-3.584 2.080l-2.336 2.816-2.336-2.816q-1.536-1.536-3.584-2.080t-4.128 0-3.616 2.080-2.080 3.584 0 4.128z"/>
    </g>
  </svg>
</template>

<script setup>
  import ProposalModel from './components/ProposalModel.vue';

  const getRandomColor = () => {
    const colors = ['#FF6B6B', '#F06292', '#EC407A', '#D81B60', '#BA68C8'];
    return colors[Math.floor(Math.random() * colors.length)];
  };

  const randomizeHeartStyle = () => {
    return {
      position: 'absolute',
      bottom: '-10%',
      width: '20%',
      fill: `${getRandomColor()}`,
      left: `calc(${Math.random()} * 105% - 5%)`,
      'animation-duration': `${Math.random()*7 + 3}s`
    }
  };

</script>

<style scoped>
  svg {
    animation: riseHeart linear infinite
  }

  @keyframes riseHeart {
    from {
      bottom: -10%;
      width: 100px;
    }
    to {
      bottom: 40%;
      width: 0px;
    }
  }
</style>