<template>
  <div class="hello">
    <div id="navbar">
    <button type="button" @click="zoomin()"> Zoom In</button>
    <button type="button" @click="zoomout()" > Zoom Out</button>
    </div>

    <div class="main" id="main">
    <div id="mape">
      <img id="map" src="../assets/img/privada15.png" />
    </div>
    </div>

    Drag the image: <br>


    <p>orem ipsum dolor sit amet consectetur adipisicing elit. Sapiente nesciunt corporis possimus fuga sit voluptatem, minima in vitae magnam tempore laboriosam doloremque. Quasi facere similique laborum ullam blanditiis nam quaerat.
    Debitis explicabo earum dolorum cupiditate, veniam ab praesentium facilis perspiciatis suscipit enim blanditiis! Molestias culpa facere maxime animi, quidem exercitationem nihil totam accusantium minus est autem. Molestias numquam asperiores itaque.
    Fugiat dolore facere iure exercitationem culpa minus cum, obcaecati dolor eligendi odit reprehenderit sint quibusdam non delectus in iste voluptates blanditiis, est tempora laborum quae ex? Tempore corporis perferendis ipsum.</p>
  </div>
</template>

<script>
//instalamos primero -> npm i gsap
//importamos
import gsap from "gsap";

//importamos el plugin
import Draggable from "gsap/Draggable";




// registramos el plugin
gsap.registerPlugin( Draggable); 


export default {
  name: 'HelloWorld',
  mounted(){
    //aqui lo declaramos
    Draggable.create("#mape img", {type:"x,y",bounds:"#main",edgeResistance:0.5
});
  },
  methods:{
    zoomin(){
        var myImg = document.getElementById("map");
        var currWidth = myImg.clientWidth;
        //if(currWidth == 2500) return false;
        // else{
        //    myImg.style.width = (currWidth + 100) + "px";
        //} 
        myImg.style.width = (currWidth + 100) + "px";
    },
    zoomout(){
        var myImg = document.getElementById("map");
        var currWidth = myImg.clientWidth;
        if(currWidth == 100) return false;
                 else{
            myImg.style.width = (currWidth - 100) + "px";
        }
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

#wrapper {
  width:150px; /* width of viewport in your case 100% */
  height:150px; /* height of viewport in your case 100% */
  overflow:hidden;
  margin:10px 0 0 0;
  border:1px solid #777;
  /*position:fixed;*/
}

#map {
  position:relative; /* what #map img is relative to */
}

#map img{
  position:absolute; /* need this to make dragging easy */
  top:0;
  left:0;
  border:0 none transparent;
}
*body {
  margin: 0;
}
#navbar {
        overflow: hidden;
        background-color: #099;
        position: fixed;
        top: 0;
        width: 100%;
        padding-top: 3px;
        padding-bottom: 3px;
        padding-left: 20px;
}
#navbar a {
  float: left;
  display: block;
  color: #666;
  text-align: center;
  padding-right: 20px;
  text-decoration: none;
  font-size: 17px;
}
#navbar a:hover {
  background-color: #ddd;
  color: black;
}
#navbar a.active {
  background-color: #4CAF50;
  color: white;
}
.main {
  padding: 16px;
  margin-top: 30px;
  width: 600px;
  height: 400px;
  overflow: clip;
}
.main img {
        /* max-width: 100%; */
        
        height: auto;
}
.button {
  width: 300px;
  height: 60px;
}


/*estilos para el plugin */
#mape {
  position:relative; 
}

#mape img{
  position:absolute; 
  top:0;
  left:0;
  border:0 none transparent;
}
</style>
