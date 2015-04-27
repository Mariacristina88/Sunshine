#How create a gradual animation with CSS using @keyframes.
**Name:** Maria Cristina Di Termine
**Category:** CSS3 Animations

**Date:** April 2014

The @keyframes technology lets us control all the steps of a CSS animation through the use of keyframes which we must assign. We get more control of the animation sequence by deciding when the animation has to start and when has to finish. 
We have to assign a name to the @keyframe rule which is then used by the “animation-name” property to connect the animation to its keyframe list.
In the keyframe list can specify the start/end points in percent (0% as start and 100% as end) or using the keywords “from” and “to”.
![Sky]()
----------------------------------------------------------------------

<pre lang="css">
@keyframes myname {
  0% { }
  100% { }
}

@keyframes myname {
  from { }
  to { }
}
</pre>

Is always good to define both the selectors, to get a better browser result.
It’s important to specify at least the begin and the end of the animation because if these time offsets aren’t defined, the animation won’t work.
If the starting point is the same of the ending point we can write the syntax using a comma.

<pre lang="css">
@keyframes myname {
  0%, 100% {top:10px;}
  50% {top:30px;}
}
</pre>

We can have many Keyframe selectors in one animation but when a keyframe is defined multiple times only the latest keyframe will be considered.

<pre lang="css">
@keyframes myname {
  0% {top:10px;}
  50% {top:20px;}
  50% {top:30px;}    /*This keyframe will be considered/*
  100% {top:40px;}
}
</pre>

In general the CSS syntax is:
@keyframe animation-name {keyframe selector {CSS-style;}}

Here an example of animation:

**HTML**
<pre lang="html">
<div id="animated-example" class="red"></div>
<div id="animated-example" class="flipInY blue"></div>
<div id="animated-example" class="yellow"></div>
</pre>

**CSS**
<pre lang="css">
#animated-example {
    width: 100px;
    height: 100px;
    float: left;
}

.blue {
    background-color: blue;
}

.red {
    background-color: red;
}

.yellow {
    background-color: yellow;
}

.flipInY { 
    animation: flipInY 3s infinite;  /* Standard syntax */
    -webkit-animation: flipInY 3s infinite;  /* Chrome, Safari, Opera */
}

/* Chrome, Safari, Opera */

@-webkit-keyframes flipInY { 
    0%, from { 
        -webkit-transform: perspective(200px) rotateY(180deg);
    } 
    40% { 
        -webkit-transform: perspective(200px) rotateY(-10deg);
    } 
    70% { 
        -webkit-transform: perspective(200px) rotateY(10deg);
    } 
    100%, to { 
        -webkit-transform: perspective(200px) rotateY(0deg);
    } 
} 


/* Standard Syntax */

@keyframes flipInY { 
    0%, from { 
        transform: perspective(200px) rotateY(180deg);
    } 
    40% { 
        transform: perspective(200px) rotateY(-10deg);
    } 
    70% { 
        transform: perspective(200px) rotateY(10deg);
    } 
    100%, to { 
        transform: perspective(200px) rotateY(0deg);
    } 
} 
</pre>

Let’s make something more fancy:
	
<pre lang="html">
<!DOCTYPE html>
<html>
<head>
</head>

<style>

	.container {
	    width: 400px;
	    height: 600px;
	}

	.sky {
	    background-color: #FFD1A3;
	    width:100%;
	    height:400px;
	    z-index:1;
	    animation: sky 8s ease running infinite;
	    -webkit-animation: sky 8s ease running infinite;
	}

	.earth {
	    background-color: green;
	    width: 400px;
	    height: 200px;
	    z-index:3;
	    position:absolute;
	    animation: earth 8s ease running infinite;
	    -webkit-animation: earth 8s ease running infinite;
	}

	.sun {
	    z-index:2;
	    width:100px;
	    height:100px;
	    border-radius: 70px;
	    background-color:orange;
	    position:absolute;
	    top:400px;
	    left:250px;
	    animation: sun 8s ease running infinite;
	    -webkit-animation: sun 8s ease running infinite;
	}

	.moon {
	    z-index:2;
	    width:100px;
	    height:100px;
	    border-radius: 70px;
	    background-color:white;
	    position:absolute;
	    top:20px;
	    left:200px;
	    animation: moon 8s ease running infinite;
	    -webkit-animation: moon 8s ease running infinite;
	}

	.cloud {
	    width: 100px;
	    height: 50px;
	    border-radius:100px;
	    position:absolute;
	    opacity:0.5;
	    background-color:white;
	    z-index:2;
	    top: 20px;
	    animation: cloud 8s ease running infinite;
	    -webkit-animation: cloud 8s ease running infinite;

	}
	.cloud2 {
	    width: 100px;
	    height: 50px;
	    border-radius:100px;
	    position:absolute;
	    opacity:0.5;
	    background-color:white;
	    z-index:2;
	    top: 35px;
	    left: 35px;
	    animation: cloud2 8s ease running infinite;
	    -webkit-animation: cloud2 8s ease running infinite;
	}

	/* Standard Syntax */

	@keyframes sky {
	    0% {background-color:#FFD1A3;}
	    50% {background-color:#94DBFF;}
	    100% {background-color:#00527A;}
	}

	@keyframes sun {
	    0% {top:400px;
	        left:250px;}
	    50% {top:20px;}
	    100% {top:430px;
	          left:20px;}
	}

	@keyframes cloud {
		0% {top: 35px;
	        left: 500px;}
	  
	    100% {top: 35px;
	          left: 35px;}
	}

	@keyframes cloud2 {
		0% {top: 50px;
	        left: 500px;}
	  
	    100% {top: 50px;
	        left: 60px;}
	}

	@keyframes moon {
		0% {top:-200px;
	        left:200px;}
	    80% {top:-100px;}
	    100% {top:30px;
	          left:250px;}
	}

	@keyframes earth {
		0% {background-color:green;}
		80% {background-color:green;}
	    100% {background-color:#472400;}
	}

	/* Chrome, Safari, Opera */

	@-webkit-keyframes earth {
	    0% {background-color:green;}
	    80% {background-color:green;}
	    100% {background-color:#472400;}
	}

	@-webkit-keyframes sky {
	    0% {background-color:#FFD1A3;}
	    50% {background-color:#94DBFF;}
	    100% {background-color:#00527A;}
	}


	@-webkit-keyframes sun {
	    0% {top:400px;
	        left:250px;}
	    50% {top:20px;
	        left:150px}
	    100% {top:430px;
	          left:20px;}
	}

	@-webkit-keyframes cloud {
	    0% {top: 35px;
	        left: 500px;}
	  
	    100% {top: 35px;
	          left: 35px;}
	}

	@-webkit-keyframes cloud2 {
	    0% {top: 50px;
	        left: 500px;}
	  
	    100% {top: 50px;
	        left: 60px;}
	}

	@-webkit-keyframes moon {
	    0% {top:-200px;
	        left:200px;}
	    80% {top:-100px;}
	    100% {top:30px;
	          left:250px;}
	}

</style>

<body>
	<div class="container">
	    <div class="sky"></div>
	    <div class="earth"></div>
	    <div class="sun"></div>
	    <div class="cloud"></div>
	    <div class="cloud2"></div>
	    <div class="moon"></div>
	</div>
</body>
</pre>
