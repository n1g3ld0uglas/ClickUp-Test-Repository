# ClickUp Test Repository
Documenting the GitHub Integration with ClickUp

# Sample JavaScript code to animate text
Changes I make to this code should be reflected in the ClickUp Audit trail
```
text="JavaScript Resources"

//set the fontsize you want:
	var fontsize=36

//The color of the text
	var color="brown"
	
//the alignment of the text, you can choose center, right or left.
	var align="left"

//Set the speed you want it to write in (in milliseconds between each letter)
	var Wspeed=100

//Set font
	var font='Arial,Helvetica, sans-serif'
  
//Set the time you want it to wait before it starts after pageload:
	var timetowait=1000
        
/*You can remove this if you don't wan't it to start right away.
You can have it start if someone clicks a link (make a link like this:
<a href="#" onclick="writeInit()">Click to writetext</a>)*/
	onload=writeInit;

/*You shouldn't really have to set anything below this point
****************************************************************************
****************************************************************************
*****************************************************************************/
/*Browsercheck and settings vars
****************************************************************************/
var ie, n;
if (document.all) {
	n=0; ie=1
	writeText='document.all.divZoom.innerHTML=\'<p align=\"\'+align+\'\" style=\"font-family:\'+font+\'; font-size:\'+fontsize+\'px; color:\'+color+\'">\'+text+\'</p>\''
	closeIt=""
}
if (document.layers) {
	n=1;ie=0
	writeText="document.divZoom.document.write('<p align=\"'+align+'\" style=\"font-family:'+font+'; font-size:'+fontsize+'px; color:'+color+'\">'+text+'</p>')"
	closeIt="document.divZoom.document.close()"
}

/*The functions for writing text.
****************************************************************************/
function writeIt(){
	if(text.length>0){
		text=text.slice(0,text.length-1)
		eval(writeText)
		eval(closeIt)
		setTimeout("writeIt()",Wspeed)
	}
}
/*This is the functions that calls the right function...or something :}
****************************************************************************/
function writeInit(){
	eval(writeText)
	eval(closeIt)
	if(ie || n) setTimeout("writeIt(0)",timetowait)       
}
//***************************************************************************
</script>
</head>
<body bgcolor="#ffe4c4" text="#000000" link="#0000FF" vlink="#800080" alink="#FF0000">
<div align="center"><h1>Disappearing Text</h1></div>
<div id="divZoom" style="position:absolute; top:100; left:10"></div>
<div id="footer+text" style="position: absolute; left: 10; top: 150"><layer name="footer+text" left=10 top=230>
<p>Here's another neat DHTML trick, causing the title to disappear letter by letter. This would be ideal on an entry page to a site.</p>
```
