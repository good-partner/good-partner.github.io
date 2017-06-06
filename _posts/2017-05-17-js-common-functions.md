---
layout: post
title:  "JavaScript 常用函数"
date:   2017-05-17 12:00:10 +0800
categories: javascript
tags: javascript函数
---

#### html_encode  转义字符串

```javascript
function html_encode(str)   
{   
  var s = "";   
  if (str.length == 0) return "";   
  s = str.replace(/&/g, "&gt;");   
  s = s.replace(/</g, "&lt;");   
  s = s.replace(/>/g, "&gt;");   
  s = s.replace(/ /g, "&nbsp;");   
  s = s.replace(/\'/g, "&#39;");   
  s = s.replace(/\"/g, "&quot;");   
  s = s.replace(/\n/g, "<br>");   
  return s;   
}   
```

#### html_decode 转义字符串解析


```javascript
function html_decode(str)   
{   
  var s = "";   
  if (str.length == 0) return "";   
  s = str.replace(/&gt;/g, "&");   
  s = s.replace(/&lt;/g, "<");   
  s = s.replace(/&gt;/g, ">");   
  s = s.replace(/&nbsp;/g, " ");   
  s = s.replace(/&#39;/g, "\'");   
  s = s.replace(/&quot;/g, "\"");   
  s = s.replace(/<br>/g, "\n");   
  return s;   
}
```

#### 采集页面时获取页面中的js变量


```javascript
//正常情况只需要以分号结尾，
//但是如果变量中出现了英文分号，需要找到唯一结尾结束符，例如 ‘};’
//也就是需要多向前匹配一个字符或者两个字符
$patten="'var cinemasJson =(.*?)};'is";
echo getVarInjs($txt,$patten, true);

//正常情况只需要以分号结尾
$patten="'var districtJson =(.*?);'is";
echo getVarInjs($txt,$patten);


function getVarInjs($str,$patten,$withType = true)
{
    $patten_js  = $withType?"'<\s*script[^>]*[^/]>(.*?)<\s*/\s*script\s*>'is":"'<\s*script\s*>(.*?)<\s*/\s*script\s*>'is";
    preg_match_all($patten_js, $str, $matches);

    foreach($matches[1] as $m)
    {
        //过滤取值
        preg_match($patten,$m,$result);
        if(!empty($result[1]))
            return $result[1];
    }
    return false;
}

```

#### 复制到粘贴板

```javascript
function copy_text(id){
    document.getElementById(id).select();
    document.execCommand("copy",false,null);
}
```
