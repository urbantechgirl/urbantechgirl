### Hi there 👋


<div id="badges"  align="center">

[![Typing SVG](https://readme-typing-svg.herokuapp.com?color=63CF15&lines=My+Name+Is+Z+E+E)](https://git.io/typing-svg)
    
  </div>

<div id="badges"  align="center">
    
  </div>

<div id="header" align="center">
    <a href="yhttps://github.com/urbantechgirl/">
  <img src="https://developers.giphy.com/branch/master/static/api-512d36c09662682717108a38bbb5c57d.gif" width="480"/>
       </a>
</div>

<br>

     
<div align="center">
   
   [![Top Langs](https://github-readme-stats.vercel.app/api/top-langs/?username=urbantechgirl&layout=compact&hide=html,hack,css&theme=gotham)](https://github.com/urbantechgirl) 
  <img  height=' 165px' src="https://github-readme-stats.vercel.app/api?username=urbantechgirl&show_icons=true&theme=gotham&count_private=true">
</div>

<br>


<div align="center">
  <img src="https://github-profile-trophy.vercel.app/?username=urbantechgirl&column=7&theme=onedark" />
</div>
<br>

 <div id='badges' align="center">

| tools  | languages | 
|---|---|
|<div id='badges' align="center"><img src="https://github.com/devicons/devicon/blob/master/icons/vscode/vscode-original.svg" title="" alt="J" width="30" height="30"/>&nbsp;<img src="https://github.com/devicons/devicon/blob/master/icons/figma/figma-original.svg" title="" alt="J" width="30" height="30"/>&nbsp;<img src="https://github.com/devicons/devicon/blob/master/icons/xd/xd-plain.svg" title="" alt="J" width="30" height="30"/>&nbsp; </div>|<div id='badges' align="center"><img src="https://github.com/devicons/devicon/blob/master/icons/javascript/javascript-original.svg" title="" alt="J" width="30" height="30"/>&nbsp;<img src="https://github.com/devicons/devicon/blob/master/icons/html5/html5-original.svg" title="" alt="J" width="30" height="30"/>&nbsp;<img src="https://github.com/devicons/devicon/blob/master/icons/css3/css3-plain.svg" title="" alt="J" width="30" height="30"/>&nbsp; <img src="https://github.com/devicons/devicon/blob/master/icons/react/react-original.svg" title="" alt="J" width="30" height="30"/>&nbsp; <img src="https://github.com/devicons/devicon/blob/master/icons/git/git-original.svg" title="" alt="J" width="30" height="30"/><img src="https://github.com/devicons/devicon/blob/master/icons/npm/npm-original-wordmark.svg" title="" alt="J" width="30" height="30"/>&nbsp;<img src="https://github.com/devicons/devicon/blob/master/icons/wordpress/wordpress-plain.svg" title="" alt="J" width="30" height="30"/>&nbsp; </div></div>|   
  
  




<br>

<div id="badges"  align="center">

![GitHub Activity Graph](https://activity-graph.herokuapp.com/graph?username=urbantechgirl&bg_color=333333&color=00ffff&line=00ffff&point=ffffff&area=true&hide_border=false)

</div>

<br>

<h3>My articles</h2>

1) https://angelic.hashnode.dev/how-to-create-a-crypto-token-using-metamask-and-remix-ide

<br>

2) https://angelic.hashnode.dev/custodial-vs-non-custodial-wallets

<br>

 </div>
<div id="badges"  align="center">
  <a href="https://angelic.hashnode.dev/">
    <img src="https://img.shields.io/badge/Hashnode-2962FF?style=for-the-badge&logo=hashnode&logoColor=white" alt="Hashnode Badge"/>
  </a>

  <a href="https://medium.com/@urbantechgirl">
    <img src="https://img.shields.io/badge/Medium-12100E?style=for-the-badge&logo=medium&logoColor=white" alt="Medium Badge"/>
  </a>
   
  <a href="https://twitter.com/urbantechgirl">
    <img src="https://img.shields.io/badge/Twitter-blue?style=for-the-badge&logo=twitter&logoColor=white" alt="Twitter Badge"/>
  </a>
</div>

#pendulum
<!DOCTYPE html>
<html>
	<head>
		<title>Page Title</title>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1, minimum-scale=1, shrink-to-fit=no"/>
	</head>
	<body>
<style>
body {
 margin:0;
 padding:0;   
}
#canvas{
 position:absolute;
 background-color:#000;
}
</style>
	 <canvas id = "canvas"></canvas>
<script>

const nums = 70;
 const canvas = document.querySelector('canvas');
 const ctx = canvas.getContext('2d'); 
 
 let {PI,sin,cos,atan2,sqrt,pow,random} = Math;
 
 canvas.height = window.innerHeight;
 canvas.width = window.innerWidth;
 
 class Pendulum {
 
  constructor(params){
   this.px = params.px;
   this.py = params.py;
   this.prad = params.prad;
   this.pcol = params.pcol;
   this.len = params.len;
   this.theta = params.theta;
   this.bx = sin(this.theta)*this.len + this.px;
   this.by = cos(this.theta)*this.len + this.py;
   this.brad = params.brad;
   this.bcol = params.bcol;
   this.v = 0;
   this.draw();
  }
  
  draw(){
	ctx.beginPath();
	ctx.moveTo(this.px,this.py);
	ctx.lineTo(this.bx,this.by);
	ctx.lineWidth = 1.0;
	ctx.strokeStyle = `red`;
	ctx.stroke();
	ctx.beginPath();
	ctx.arc(this.px,this.py,this.prad,0,PI*2);
	ctx.fillStyle = this.pcol;
	ctx.fill();
	ctx.beginPath();
	ctx.arc(this.bx,this.by,this.brad,0,PI*2);
	ctx.fillStyle = this.bcol;
	ctx.fill();
  }
  
  update(){
  this.bx = sin(this.theta)*this.len + this.px;
  this.by = cos(this.theta)*this.len + this.py; 
  this.v += -(gravity * sin(this.theta)) /this.len;
   this.theta += this.v;
  //this.v /= resistance;
   this.draw();
  }  
}

 let params = {
	 px:canvas.width/2,
	 py:150,
	 prad:2,
	 pcol:`green`,
	 len:700,
	 brad:18,
	 bcol:`red`,
	 theta:PI/6
  };
  
  const pendulums = [];
  const gravity = 0.5;
  const resistance = 1.004;
  const lengths = [];
  const maxL = 500;
  const sync = 65;
  
  init();
  
  
  function init(){
  
  let hue = 160; 
  for(let i = sync;i<sync+nums;i++){
  let l = maxL*pow((sync/i),2);
  lengths.push(l); } 
  
  for(let i = 0;i<nums;i++){
 // params.brad += 0.4;
  params.len = lengths[i];
  params.bcol = `hsl(${hue+=-4},70%,50%)`;
  pendulums.push(new Pendulum(params));  }
  
  requestAnimationFrame(animate);
  }
  
  function animate(){
   ctx.clearRect(0,0,canvas.width,canvas.height);
   pendulums.forEach((pendulum)=>{
		pendulum.update();});
   
   requestAnimationFrame(animate);
  } 
</script>
	</body>
</html>
