#How create a gradual animation with CSS using @keyframes.
**Name:** Maria Cristina Di Termine
**Category:** CSS3 Animations

**Date:** April 2014

The @keyframes technology lets us control all the steps of a CSS animation through the use of keyframes which we must assign. We get more control of the animation sequence by deciding when the animation has to start and when has to finish. 
We have to assign a name to the @keyframe rule which is then used by the “animation-name” property to connect the animation to its keyframe list.
In the keyframe list can specify the start/end points in percent (0% as start and 100% as end) or using the keywords “from” and “to”.

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
  50% {top:30px;}    /*This keyframe will be considered*/
  100% {top:40px;}
}
</pre>

In general the CSS syntax is:
@keyframe animation-name {keyframe selector {CSS-style;}}

***Personal tip***
If your project requests many animations and movements, could be useful to make a little sketch or scheme to have a clearer view of the sequence you will create!
![Sunshine](https://github.com/Mariacristina88/Sunshine/blob/master/sun.jpg)
