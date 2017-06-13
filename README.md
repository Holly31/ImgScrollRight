# ImgScrollRight
图片无缝循环滚动
<div id="case" class="case_wrap">
			<div class="inCase">
				<ul id="caseBox1">
					<li><a href=""><img src="case.jpg?v=08786f8b88"><p>深圳中海锦城项目</p></a></li>
					<li><a href=""><img src="case.jpg?v=08786f8b88"><p>深圳中海锦城项目</p></a></li>
					<li><a href=""><img src="case.jpg?v=08786f8b88"><p>深圳中海锦城项目</p></a></li>
					<li><a href=""><img src="case.jpg?v=08786f8b88"><p>深圳中海锦城项目</p></a></li>
					<li><a href=""><img src="case.jpg?v=08786f8b88"><p>深圳中海锦城项目</p></a></li>
				</ul>
			<div id="caseBox2"></div>
		</div>
	</div>


css样式：
<style>
			.case_wrap {
			  overflow: hidden;
			  width: 1200px;
			  height: 200px;
			  margin: 0 auto;
			  border: 1px solid #ccc;
			}
			
			.inCase {
			  width: 800%;
			  float: left;
			}
			.inCase #caseBox1 {
			  float: left;
			}
			.inCase #caseBox1 li {
			  float: left;
			  width: 280px;
			  height: 193px;
			  overflow: hidden;
			  margin-right: 25px;
			  border: 1px solid transparent;
			}
			.inCase #caseBox1 li:hover {
			  border: 1px solid #ce3235;
			}
			.inCase #caseBox1 li p {
			  font-size: 14px;
			  color: #666;
			  text-align: center;
			  line-height: 2em;
			}
			.inCase #caseBox1 img {
			  width: 280px;
			  height: 158px;
			  overflow: hidden;
			  transition: all, 0.5s, ease-out;
			  -webkit-transition: all, 0.5s, ease-out;
			  -moz-transition: all, 0.5s, ease-out;
			  -o-transition: all, 0.5s, ease-out;
			}
			.inCase #caseBox1 img:hover {
			  transform: matrix(1.04, 0, 0, 1.04, 0, 0);
			  -webkit-transform: matrix(1.04, 0, 0, 1.04, 0, 0);
			  -moz-transform: matrix(1.04, 0, 0, 1.04, 0, 0);
			  -o-transform: matrix(1.04, 0, 0, 1.04, 0, 0);
			}
			.inCase #caseBox2 {
			  float: left;
			}

		</style>
主要js代码：
<script>
//图片无缝轮播
var speed=40; 
	var tab=document.getElementById("case"); 
	var tab1=document.getElementById("caseBox1"); 
	var tab2=document.getElementById("caseBox2"); 
	tab2.innerHTML=tab1.innerHTML; 
	function Marquee(){ 
	if(tab2.offsetWidth-tab.scrollLeft<=0) 
	tab.scrollLeft-=tab1.offsetWidth; 
	else{ 
	tab.scrollLeft++; 
	} 
	} 
	var MyMar=setInterval(Marquee,speed); 
	tab.onmouseover=function() {clearInterval(MyMar)}; 
	tab.onmouseout=function() {MyMar=setInterval(Marquee,speed)}; 
</script>
