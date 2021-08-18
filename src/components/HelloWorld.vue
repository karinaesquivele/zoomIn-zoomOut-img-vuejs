<template>
  <div class="hello">
    <div id="navbar">
    <button type="button" @click="zoomin()"> Zoom In</button>
    <button type="button" @click="zoomout()" > Zoom Out</button>
    </div>

    <div class="main">
    <img id="map" src="../assets/img/privada15.png" />
    </div>

    <p>orem ipsum dolor sit amet consectetur adipisicing elit. Sapiente nesciunt corporis possimus fuga sit voluptatem, minima in vitae magnam tempore laboriosam doloremque. Quasi facere similique laborum ullam blanditiis nam quaerat.
    Debitis explicabo earum dolorum cupiditate, veniam ab praesentium facilis perspiciatis suscipit enim blanditiis! Molestias culpa facere maxime animi, quidem exercitationem nihil totam accusantium minus est autem. Molestias numquam asperiores itaque.
    Fugiat dolore facere iure exercitationem culpa minus cum, obcaecati dolor eligendi odit reprehenderit sint quibusdam non delectus in iste voluptates blanditiis, est tempora laborum quae ex? Tempore corporis perferendis ipsum.</p>
  </div>
</template>

<script>
export default {
  name: 'HelloWorld',
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
}
.main img {
        /* max-width: 100%; */
        width: 100%;
        height: auto;
}
.button {
  width: 300px;
  height: 60px;
}
</style>
