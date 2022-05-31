 <html lang="de">
 <head>
     <meta charset="UTF-8">
     <meta http-equiv="X-UA-Compatible" content="IE=edge">
     <meta name="viewport" content="width=device-width, initial-scale=1.0">
     <title>Julian Steiner</title>

 <script>"use strict";
    let H,W,san,{sin,cos,PI}=Math,dots=[],dts=600;
    class Dot{
        constructor(a){
        this.x=0,this.y=0,this.r=5,this.a=a,this.c=295;
        }
        draw(){
            this.x=W/2+cos(this.a)*(200-cos(this.a*50)*100);
            this.y=H/2+sin(this.a)*(200-cos(this.a*50)*100);
            this.r=2.6+sin(this.a*50)*2.5,this.a+=.0004
            san.fillStyle=`hsl(${this.c-this.r*20},100%,50%)`;
            san.beginPath();
            san.arc(this.x,this.y,this.r,0,PI*2);
            san.closePath();
            san.fill();
        }
    }
    const Loop=()=>{
    san.clearRect(0,0,W,H);
       dots.forEach(v=>v.draw());
    requestAnimationFrame(Loop);
    }
    const init=()=>{
    document.body.style.margin=0;
    let c=document.createElement("canvas");
    document.body.appendChild(c);
    c.style.position="fixed"
    c.style.background="black"
    c.style.width="100vw",c.style.height="100vh";
    H=innerHeight*2,W=innerWidth*2;
    c.height=H,c.width=W,san=c.getContext('2d');
    let dh=+getComputedStyle(c).height.slice(0,-2);
    let dw=+getComputedStyle(c).width.slice(0,-2);
    c.setAttribute('height',dh*2);
    c.setAttribute('width',dw*2);
    for(var i=0;i<dts;i++) dots.push(new Dot(i/0.77092));
    Loop();
    };
    onload=init;</script>
 <style>
     body { margin: 0;
        background-repeat:inherit;
        background-attachment: fixed;
    }
    script {text-align: center;}
    h1 {text-align: center;}
    html {margin-bottom: 50px;
    margin-top:3%;}
  html {color:white;}
     
 </style>
 </head>
 <body>
 <h1>Julian Steiner </h1>
     
  
 </body>
 </html>
