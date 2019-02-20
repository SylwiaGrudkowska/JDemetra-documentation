---
layout: post
title: Rotating Panels
author: David De Antonio Liedo
tags: [rotating panels, R, states space models]
---
 
#### Examples 

The autocorrelated wage specific errors are driven by a proportion of individuals that do not update their responses on the basis of new information, so 
in principle it is possible that first wave individuals' responses persist until the last wave $$W$$. However, it is typically assumed that 
the error in the first response is correlated to the error in the second response, but uncorrelated to the error in the third response. 

<!--more-->

A representation of all possible correlation patterns in a panel defined by $ W=5 $ and $ nlags=3 $ follows in this table:


<br/>
<style type="text/css">
.tg  {border-collapse:collapse;border-spacing:0;border-color:#ccc;margin:0px auto;}
.tg td{font-family:Arial, sans-serif;font-size:14px;padding:10px 5px;border-style:solid;border-width:1px;overflow:hidden;word-break:normal;border-color:#ccc;color:#333;background-color:#fff;}
.tg th{font-family:Arial, sans-serif;font-size:14px;font-weight:normal;padding:10px 5px;border-style:solid;border-width:1px;overflow:hidden;word-break:normal;border-color:#ccc;color:#333;background-color:#f0f0f0;}
.tg .tg-zhlz{background-color:#9aff99;color:#fe0000;border-color:#000000;text-align:left;vertical-align:top}
.tg .tg-4fps{background-color:#efefef;color:#000000;border-color:#000000;text-align:left;vertical-align:top}
.tg .tg-64au{background-color:#ffffff;color:#3531ff;border-color:#c0c0c0;text-align:left;vertical-align:top}
.tg .tg-vq2r{background-color:#ffccc9;color:#000000;border-color:#000000;text-align:left;vertical-align:top}
.tg .tg-2iub{background-color:#efefef;color:#000000;border-color:#000000;text-align:left;vertical-align:top}
.tg .tg-ephz{background-color:#ffffff;color:#32cb00;border-color:#c0c0c0;text-align:left;vertical-align:top}
.tg .tg-msbt{background-color:#cbcefb;color:#fe0000;border-color:#000000;text-align:left;vertical-align:top}
.tg .tg-h7fs{background-color:#9aff99;color:#000000;border-color:#000000;text-align:left;vertical-align:top}
.tg .tg-ajer{background-color:#ffccc9;color:#3531ff;border-color:#000000;text-align:left;vertical-align:top}
.tg .tg-hc6b{background-color:#efefef;color:#3531ff;border-color:#000000;text-align:left;vertical-align:top}
.tg .tg-ns90{background-color:#ffccc9;color:#036400;border-color:#000000;text-align:left;vertical-align:top}
.tg .tg-dn45{background-color:#ffffff;color:#fe0000;border-color:#c0c0c0;text-align:left;vertical-align:top}
.tg .tg-iks7{background-color:#ffffff;border-color:#000000;text-align:left;vertical-align:top}
.tg .tg-f6zi{background-color:#efefef;color:#fe0000;border-color:#000000;text-align:left;vertical-align:top}
.tg .tg-9gyk{background-color:#efefef;color:#036400;border-color:#000000;text-align:left;vertical-align:top}
.tg .tg-alwn{background-color:#ffffff;color:#000000;border-color:#c0c0c0;text-align:left;vertical-align:top}
.tg .tg-lzr2{background-color:#ffccc9;color:#fe0000;border-color:#000000;text-align:left;vertical-align:top}
.tg .tg-usd3{background-color:#9aff99;color:#036400;border-color:#000000;text-align:left;vertical-align:top}
.tg .tg-817c{background-color:#9aff99;color:#3531ff;border-color:#000000;text-align:left;vertical-align:top}
.tg .tg-zjti{background-color:#cbcefb;color:#000000;border-color:#000000;text-align:left;vertical-align:top}
.tg .tg-7hn9{background-color:#cbcefb;color:#036400;border-color:#000000;text-align:left;vertical-align:top}
.tg .tg-kqhi{background-color:#cbcefb;color:#3531ff;border-color:#000000;text-align:left;vertical-align:top}
.tg-sort-header::-moz-selection{background:0 0}.tg-sort-header::selection{background:0 0}.tg-sort-header{cursor:pointer}.tg-sort-header:after{content:'';float:right;margin-top:7px;border-width:0 5px 5px;border-style:solid;border-color:#404040 transparent;visibility:hidden}.tg-sort-header:hover:after{visibility:visible}.tg-sort-asc:after,.tg-sort-asc:hover:after,.tg-sort-desc:after{visibility:visible;opacity:.4}.tg-sort-desc:after{border-bottom:none;border-width:5px 5px 0}@media screen and (max-width: 767px) {.tg {width: auto !important;}.tg col {width: auto !important;}.tg-wrap {overflow-x: auto;-webkit-overflow-scrolling: touch;margin: auto 0px;}}</style>
<div class="tg-wrap"><table id="tg-qig81" class="tg">
  <tr>
    <th class="tg-iks7" colspan="4">Input Correlation Matrix with $ W=5 $ and $ nlags=3 $</th>
    <th class="tg-4fps">$\varepsilon^{(1)}_{t}$</th>
    <th class="tg-4fps">$\varepsilon^{(2)}_{t}$</th>
    <th class="tg-4fps">$\varepsilon^{(3)}_{t}$</th>
    <th class="tg-4fps">$\varepsilon^{(4)}_{t}$</th>
    <th class="tg-4fps">$\varepsilon^{(5)}_{t}$</th>
  </tr>
  <tr>
    <td class="tg-2iub">$\varepsilon^{(1)}_{t-3}$</td>
    <td class="tg-2iub">$\varepsilon^{(2)}_{t-3}$ </td>
    <td class="tg-2iub">$\varepsilon^{(3)}_{t-3}$</td>
    <td class="tg-2iub">$\varepsilon^{(4)}_{t-3}$</td>
    <td class="tg-wltw">0</td>
    <td class="tg-alwn">$\phi^{2}_{1}$</td>
    <td class="tg-alwn">$\phi^{3}_{1}$</td>
    <td class="tg-alwn">$\phi^{4}_{1}$</td>
    <td class="tg-alwn">$\phi^{5}_{1}$</td>
  </tr>
  <tr>
    <td class="tg-lzr2"></td>
    <td class="tg-lzr2">$\varepsilon^{(1)}_{t-3\times 2}$</td>
    <td class="tg-lzr2">$\varepsilon^{(2)}_{t-3\times 2}$</td>
    <td class="tg-lzr2">$\varepsilon^{(3)}_{t-3\times 2}$</td>
    <td class="tg-dn45">0</td>
    <td class="tg-dn45">0</td>
    <td class="tg-dn45">$\phi^{3}_{2}$</td>
    <td class="tg-dn45">$\phi^{4}_{2}$</td>
    <td class="tg-dn45">$\phi^{5}_{2}$</td>
  </tr>
  <tr>
    <td class="tg-usd3"></td>
    <td class="tg-usd3"></td>
    <td class="tg-usd3">$\varepsilon^{(1)}_{t-3\times 3}$</td>
    <td class="tg-usd3">$\varepsilon^{(2)}_{t-3\times 3}$</td>
    <td class="tg-ephz">0</td>
    <td class="tg-ephz">0</td>
    <td class="tg-ephz">0</td>
    <td class="tg-ephz">$\phi^{4}_{3}$</td>
    <td class="tg-ephz">$\phi^{5}_{3}$</td>
  </tr>
  <tr>
    <td class="tg-zjti"></td>
    <td class="tg-msbt"></td>
    <td class="tg-7hn9"></td>
    <td class="tg-kqhi">$\varepsilon^{(1)}_{t-3\times 4}$</td>
    <td class="tg-64au">0</td>
    <td class="tg-64au">0</td>
    <td class="tg-64au">0</td>
    <td class="tg-64au">0</td>
    <td class="tg-64au">$\phi^{5}_{1}$</td>
  </tr>
</table></div>
<script charset="utf-8">var TGSort=window.TGSort||function(n){"use strict";function r(n){return n.length}function t(n,t){if(n)for(var e=0,a=r(n);a>e;++e)t(n[e],e)}function e(n){return n.split("").reverse().join("")}function a(n){var e=n[0];return t(n,function(n){for(;!n.startsWith(e);)e=e.substring(0,r(e)-1)}),r(e)}function o(n,r){return-1!=n.map(r).indexOf(!0)}function u(n,r){return function(t){var e="";return t.replace(n,function(n,t,a){return e=t.replace(r,"")+"."+(a||"").substring(1)}),l(e)}}function i(n){var t=l(n);return!isNaN(t)&&r(""+t)+1>=r(n)?t:NaN}function s(n){var e=[];return t([i,m,g],function(t){var a;r(e)||o(a=n.map(t),isNaN)||(e=a)}),e}function c(n){var t=s(n);if(!r(t)){var o=a(n),u=a(n.map(e)),i=n.map(function(n){return n.substring(o,r(n)-u)});t=s(i)}return t}function f(n){var r=n.map(Date.parse);return o(r,isNaN)?[]:r}function v(n,r){r(n),t(n.childNodes,function(n){v(n,r)})}function d(n){var r,t=[],e=[];return v(n,function(n){var a=n.nodeName;"TR"==a?(r=[],t.push(r),e.push(n)):("TD"==a||"TH"==a)&&r.push(n)}),[t,e]}function p(n){if("TABLE"==n.nodeName){for(var e=d(n),a=e[0],o=e[1],u=r(a),i=u>1&&r(a[0])<r(a[1])?1:0,s=i+1,v=a[i],p=r(v),l=[],m=[],g=[],h=s;u>h;++h){for(var N=0;p>N;++N){r(m)<p&&m.push([]);var T=a[h][N],C=T.textContent||T.innerText||"";m[N].push(C.trim())}g.push(h-s)}var L="tg-sort-asc",E="tg-sort-desc",b=function(){for(var n=0;p>n;++n){var r=v[n].classList;r.remove(L),r.remove(E),l[n]=0}};t(v,function(n,t){l[t]=0;var e=n.classList;e.add("tg-sort-header"),n.addEventListener("click",function(){function n(n,r){var t=d[n],e=d[r];return t>e?a:e>t?-a:a*(n-r)}var a=l[t];b(),a=1==a?-1:+!a,a&&e.add(a>0?L:E),l[t]=a;var i=m[t],v=function(n,r){return a*i[n].localeCompare(i[r])||a*(n-r)},d=c(i);(r(d)||r(d=f(i)))&&(v=n);var p=g.slice();p.sort(v);for(var h=null,N=s;u>N;++N)h=o[N].parentNode,h.removeChild(o[N]);for(var N=s;u>N;++N)h.appendChild(o[s+p[N-s]])})})}}var l=parseFloat,m=u(/^(?:\s*)([+-]?(?:\d+)(?:,\d{3})*)(\.\d*)?$/g,/,/g),g=u(/^(?:\s*)([+-]?(?:\d+)(?:\.\d{3})*)(,\d*)?$/g,/\./g);n.addEventListener("DOMContentLoaded",function(){for(var t=n.getElementsByClassName("tg"),e=0;e<r(t);++e)try{p(t[e])}catch(a){}})}(document);</script>
	
<br/>

- Let's use a dataset with errors that have been generated using the following parameterization:[add all parameters]. We will 
check whether we recover the parameters we used to generate the data:
```R
# Let's load an excel file with simulated data 
data<-read_excel("../Data/simulWaves.xlsx")
# Convert it into a matrix named "errors"
#(time in the rows and errors corresponding to 5 waves in the columns)
errors<-as.matrix(data[,1:5])
```

- Specify the bias components:
```R
model<-jd3_ssf_model()
# bias
add(model, jd3_ssf_locallevel("b2"))
add(model, jd3_ssf_locallevel("b3"))
add(model, jd3_ssf_locallevel("b4"))
add(model, jd3_ssf_locallevel("b5"))
```

- Specify the autocorrelated components:
```R
# correlation:
ar=0.5
mar<-matrix(ar, nrow = 1, ncol=4)
add(david, jd3_ssf_msae("sae", nwaves=5, ar=mar, fixedar = FALSE, lag=3))
```


- Specify the measurement equations:
```R
# error of wave 1
eq1<-jd3_ssf_equation("eq1")
add(eq1, "b2", -1)
add(eq1, "b3", -1)
add(eq1, "b4", -1)
add(eq1, "b5", -1)
add(eq1, "sae", coef=1,fixed=F,loading=jd3_ssf_loading(0))
add(model, eq1)
# error of wave 2
eq2<-jd3_ssf_equation("eq2")
add(eq2, "b2")
add(eq2, "sae",coef=1,fixed=F, loading=jd3_ssf_loading(1))
add(model, eq2)
# error of wave 3
eq3<-jd3_ssf_equation("eq3")
add(eq3, "b3")
add(eq3, "sae", coef=1,fixed=F,loading=jd3_ssf_loading(2))
add(model, eq3)
# error of wave 4
eq4<-jd3_ssf_equation("eq4")
add(eq4, "b4")
add(eq4, "sae", coef=1,fixed=F,loading=jd3_ssf_loading(3))
add(model, eq4)
# error of wave 5
eq5<-jd3_ssf_equation("eq5")
add(eq5, "b5")
add(eq5, "sae", coef=1,fixed=F,loading=jd3_ssf_loading(4))
add(model, eq5)
```

- Estimate model
```R
# estimate
modelResults<-estimate(david, errors, marginal=T, concentrated=F)
# plot results
result(modelResults,"parameters") 
result(modelResults,"parametersname")
```