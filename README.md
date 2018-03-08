## The font becomes larger and smaller
#### HTML code
```html
<div class="con7_center">
    <span>《Had I not seen the Sun》</span>
    <span>Had I not seen the Sun</span>
    <span>I could have borne the shade</span>
    <span>But Light a newer Wilderness</span>
    <span>My Wilderness has made</span>
</div>
```
#### JS code
```javascript
var n = 0;
var timer = setInterval(function(){			
    if(n == 0){
        $(".con7_center").find("span").eq($(".con7_center").find("span").size()-1).animate({"font-size": "16px"}, 700, "swing");	
        $(".con7_center").find("span").eq(n).animate({"font-size": "30px"}, 700, "swing", function(){
            n++;
        });
    }else if(n >0 && n < $(".con7_center").find("span").size()){
	$(".con7_center").find("span").eq(n-1).animate({"font-size": "16px"}, 700, "swing");
	$(".con7_center").find("span").eq(n).animate({"font-size": "30px"}, 700, "swing", function(){
	    if(n >= $(".con7_center").find("span").size()-1){
	        n=0;
	    }else{
		n++;
	    }
	});
    }
},1500);
