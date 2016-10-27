

#これはなに    

d3.jsのV4練習してます。  
グラフ作成してます。  
知ってる人は教えてください！  


##ブックマーク  
<http://qiita.com/mojaie/items/be0a3eaf84273e2d42e7>  
<http://qiita.com/shoki_kitajima/items/34ad6e2209fde5b4dedc>  
<https://bl.ocks.org/mbostock/3310323>  
<https://bl.ocks.org/d3noob/402dd382a51a4f6eea487f9a35566de0>  
<http://dataisfun.org/2014/05/12/?p=206>  


##わかったこと  

```javascript:index.html

var xAxis = xScale
                .tickSize(6, -height)
                .tickFormat(function(d){ return d+"年"; });
 
var yAxis = yScale
                .ticks(5)
                .tickSize(6, -width);

var xLiner = d3.scaleLinear()　←　d3.scale.linearみたいなのは大体.を取ってローワーキャメルケースにする
                .domain([2006,2014])　←　このパラメータは配列形式にする？
                .range([0,width]);　←　このパラメータは配列形式にする？

var yLiner = d3.scaleLinear()
                .domain([480,530])
                .range([height,0]);

var xScale = d3.axisBottom(xLiner)　←　ここも変わっている。
         								前はaxis().***().***()だった。***().***()の部分はscaleLinerに書いてる
var yScale = d3.axisLeft(yLiner)



なぜかループしてデータを取得してくれる
svg.selectAll("circle")
                .data(gdp)
                .enter()
                .append("circle")
                .attr("r",5)
                .attr("fill", function(d){ return colorCategoryScale(d["updown"]); })
                .attr("cx", function(d){ return xLiner(d["year"]);}) ←　なんか知らないけどよきに計らってくれる
                .attr("cy", function(d){ return yLiner(d["gdp"]);})


```

##現在の惨状  
https://wasipo.github.io/d3test/  


