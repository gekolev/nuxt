<template>
<div class="container">
  <svg class="mouse">
    <defs>
      <clipPath id="mask">
        <circle id="mask-circle" cx="50%" cy="50%" r="10%" style="fill: #ffffff"/>
      </clipPath>
    </defs>
  </svg>
    <div class="sub-holder">
      <Sub v-for="i in 25" :key="i"  />
    </div>
</div>
</template>

<script>
import Main from "../components/Main.vue";
import Sub from "../components/Sub.vue";

export default {
    name: "IndexPage",
    components: { Main, Sub },
    mounted(){
        
        var svgElement = document.querySelector('.svg');
        var maskedElement = document.querySelector('#mask-circle');
        var svgPoint = svgElement.createSVGPoint();
        
        function cursorPoint(e, svg) {
            let delay = 10;
            svgPoint.x += (e.clientX - svgPoint.x) / delay;
            svgPoint.y += (e.clientY - svgPoint.y) / delay;
            return svgPoint.matrixTransform(svg.getScreenCTM().inverse());
        }
        
        function update(svgCoords) {
            maskedElement.setAttribute('cx', svgCoords.x);
            maskedElement.setAttribute('cy', svgCoords.y);
        }
        
        window.addEventListener('mousemove', function(e) {
          update(cursorPoint(e, svgElement));
        }, false);
        
        
        }
}
</script>

<style lang="scss">
  .sub-holder{
    display: grid;
    grid-template-columns: repeat( 5,1fr );
    gap: 15px;
    position: relative;
  }
  .container{
    max-width: 600px;
    position: relative;
  }
</style>