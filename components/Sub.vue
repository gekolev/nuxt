<template lang="">
    <div>
    <!-- <div class="rel">
        <div class="abs">
            <img src="https://images.ctfassets.net/dspndasjlk8q/6698D2LSgbLy2NfLdqi6tL/0c0400d244d586eaedd6535071be602a/img_6-min.png" alt="">
        </div>
        <img src="https://images.ctfassets.net/dspndasjlk8q/CeC2Q4CkggzrpkSU0MzKV/fdd5e6666ba93bf891fa37c33b74dfac/24.png" alt="">
    </div> -->

    <div>
    <svg class="svg" width="100px" height="100px" xmlns="http://www.w3.org/2000/svg" xmlns:xlink="http://www.w3.org/1999/xlink">
        <rect width="100px" height="100px"/>
        <image xmlns:xlink="http://www.w3.org/1999/xlink" xlink:href="https://images.ctfassets.net/dspndasjlk8q/CeC2Q4CkggzrpkSU0MzKV/fdd5e6666ba93bf891fa37c33b74dfac/24.png" width="100px" height="100px" />
    </svg>
    </div>
      <svg class="abs svg" xmlns="http://www.w3.org/2000/svg" xmlns:xlink="http://www.w3.org/1999/xlink">
        <g clip-path="url(#mask)">
          <rect width="100px" height="100px"/>
          <image class="big-img" v-bind:style="{ top: top  + newTop + 'px' }" :class="'image' + index++" xmlns:xlink="http://www.w3.org/1999/xlink" xlink:href="https://images.ctfassets.net/dspndasjlk8q/6698D2LSgbLy2NfLdqi6tL/0c0400d244d586eaedd6535071be602a/img_6-min.png" width="500px" height="500px" />
        </g>
      </svg>
    </div>
</template>
<script>
export default {
    data(){
        return{
            index: 1,
            newTop: "",
            top: "top"
            }
        },
    mounted(){ function increment() {
                let number = 5
                for (let i = 0; i < 5; i++) {
                    number++
                }
                return number
                }           
                increment();
}
    // mounted(){
    //      var svgElement = document.querySelector('.svg');
    //     var maskedElement = document.querySelector('#mask-circle');
    //     var svgPoint = svgElement.createSVGPoint();
        
    //     function cursorPoint(e, svg) {
    //         let delay = 10;
    //         svgPoint.x += (e.clientX - svgPoint.x) / delay;
    //         svgPoint.y += (e.clientY - svgPoint.y) / delay;
    //         return svgPoint.matrixTransform(svg.getScreenCTM().inverse());
    //     }
        
    //     function update(svgCoords) {
    //         maskedElement.setAttribute('cx', svgCoords.x);
    //         maskedElement.setAttribute('cy', svgCoords.y);
    //     }
        
    //     window.addEventListener('mousemove', function(e) {
    //       update(cursorPoint(e, svgElement));
    //     }, false);
    // }
       

}
</script>
<style lang="scss">
    .rel{
        position: relative;
    }
    .abs{
        top: -5px;
        z-index: 2;
        position: absolute;
        width: 100px;
        height: 100px;
    }
</style>