# notes

1. 新增cookie
   $.cookie('cookieName', 'cookieValue');    
   注：如果没有设置cookie的有效期，则cookie默认在浏览器关闭前都有效，故被称为"会话cookie"。
   
2. // 创建一个cookie并设置有效时间为7天:  
   $.cookie('cookieName', 'cookieValue', { expires: 7 }); 

3. // 创建一个cookie并设置cookie的有效路径：  
   $.cookie('cookieName', 'cookieValue', { expires: 7, path: '/' }); 
   
4. 读取cookie：  
   $.cookie('cookieName'); // 若cookie存在则返回'cookieValue'；若cookie不存在则返回null 
   
5.  删除cookie：把the_cookie的值设为null即可  
    $.cookie('the_cookie', null);  

6. \b: 匹配单词边界
   \d: 匹配数字
   \w: 匹配字母、数字、下划线
   \s: 匹配空格
   . : 匹配除了换行符以外的任何字符
   [abc]: 字符组 匹配包含括号内元素的字符
   
   \W: 匹配 任意不是字母、数字、下划线的字符
   \S: 匹配任意不是空白符的字符
   \D: 匹配任意非数字的字符
   \B: 匹配不是单词开头或结束的位置
   [abc]: 匹配除了abc以外的任意字符
   
   '*?': 重复任意次，丹尽可能少重复
   "+?"  重复1次或更多次，但尽可能少重复
   "??"  重复0次或1次，但尽可能少重复
   "{n,m}?"  重复n到m次，但尽可能少重复
   "{n,}?"   重复n次以上，但尽可能少重复
   
   捕获分组
   '(exp)': 匹配exp，并捕获文本到自动命名的组里
   "(?<name>exp)"   匹配exp,并捕获文本到名称为name的组里
   "(?:exp)"  匹配exp,不捕获匹配的文本，也不给此分组分配组号
   "(?=exp)"  匹配exp前面的位置
   "(?<=exp)"  匹配exp后面的位置
   "(?!exp)"  匹配后面跟的不是exp的位置
   "(?<!exp)"  匹配前面不是exp的位置
   "(?#comment)"  这种类型的分组不对正则表达式的处理产生任何影响，用于提供注释让人阅读
   
7. text-overflow 属性规定当文本溢出包含元素时发生的事情
      clip: 修剪文本
      ellipsis: 显示省略符号来代表被修剪的文本
      string: 使用给定的字符串来代表被修剪的文
      
8. align-items 属性定义flex子项在flex容器的当前行的侧轴（纵轴）方向上的对齐方式

9. -webkit-line-clamp必须配合display: -webkit-box; text-overflow: -o-ellipsis-lastline; -webkit-box-orient: vertical;来使用。

10. on
    $(selector).on(event, childSelector, data, function, map)
    event: 必需， 规定要从被选元素移除的一个或多个事件或命名空间 由空格分割多个事件值 必须是有效事件
    childSelector: 可选， 规定只能添加到指定的子元素的事件处理程序（且不是选择器本身）
    data: 可选， 规定传递到函数的额外数据
    function: 规定当事件发生时运行的函数
    map: 规定事件映射（{event:function, event:function,...}）,包含要添加到元素的一个或多个事件，以及当事件发生时运行的函数

11. ajax方法
    url： string  （默认为当前页地址）发送请求的地址 
    type: 
    timeout: 
    async:  false: 同步  true: 异步 (默认)  同步请求将锁住浏览器 用户其他操作必须等待请求完成才可以执行
    cache:  默认为true, 设置为false将不会从浏览器缓存中加载请求信息。
    data: 要求为Object或String类型的参数，发送到服务器的数据。
    dataType: 要求为String类型的参数，预期服务器返回的数据类型
        xml：返回XML文档，可用JQuery处理。
        html：返回纯文本HTML信息；包含的script标签会在插入DOM时执行。
        script：返回纯文本JavaScript代码。不会自动缓存结果。除非设置了cache参数。注意在远程请求时（不在同一个域下），所有post请求都
                将转为get请求。
        json：返回JSON数据。
        jsonp：JSONP格式。使用JSONP形式调用函数时，例如myurl?callback=?，JQuery将自动替换后一个“?”为正确的函数名，以执行回调函数.
        text：返回纯文本字符串。
        beforeSend：要求为Function类型的参数，发送请求前可以修改XMLHttpRequest对象的函数，例如添加自定义HTTP头。在beforeSend中
                     如果返回false可以取消本次ajax请求。XMLHttpRequest对象是惟一的参数。
        complete： 要求为Function类型的参数，请求完成后调用的回调函数（请求成功或失败时均调用）。参数：XMLHttpRequest对象和一个描
                   述成功请求类型的字符串。
        success: 要求为Function类型的参数，请求成功后调用的回调函数，有两个参数
         (1)由服务器返回，并根据dataType参数进行处理后的数据
         (2)描述状态的字符串。
             function(data, textStatus){
                //data可能是xmlDoc、jsonObj、html、text等等
                this;  //调用本次ajax请求时传递的options参数
             }
         error: 要求为Function类型的参数，请求失败时被调用的函数。该函数有3个参数，即XMLHttpRequest对象、错误信息、捕获的错误对象
                (可选)。ajax事件函数如下：
                function(XMLHttpRequest, textStatus, errorThrown){
                   //通常情况下textStatus和errorThrown只有其中一个包含信息
                   this;   //调用本次ajax请求时传递的options参数
                }
          contentType：要求为String类型的参数，当发送信息至服务器时，内容编码类型默认为"application/x-www-form-urlencoded"。该默
                       认值适合大多数应用场合。
          dataFilter： 要求为Function类型的参数，给Ajax返回的原始数据进行预处理的函数。提供data和type两个参数。data是Ajax返回的原
                       始数据，type是调用jQuery.ajax时提供的dataType参数。函数返回的值将由jQuery进一步处理。
                       function(data, type){
                          //返回处理后的数据
                          return data;
                       }
           global：要求为Boolean类型的参数，默认为true。表示是否触发全局ajax事件。设置为false将不会触发全局ajax事件，ajaxStart或
                   ajaxStop可用于控制各种ajax事件。
           ifModified：要求为Boolean类型的参数，默认为false。仅在服务器数据改变时获取新数据。服务器数据改变判断的依据是Last-
                       Modified头信息。默认值是false，即忽略头信息。
           jsonp： 要求为String类型的参数，在一个jsonp请求中重写回调函数的名字。该值用来替代在"callback=?"这种GET或POST请求中URL
                   参数里的"callback"部分，例如{jsonp:'onJsonPLoad'}会导致将"onJsonPLoad=?"传给服务器。
           username： 要求为String类型的参数，用于响应HTTP访问认证请求的用户名。
           password： 要求为String类型的参数，用于响应HTTP访问认证请求的密码。
           processData： 要求为Boolean类型的参数，默认为true。默认情况下，发送的数据将被转换为对象（从技术角度来讲并非字符串）以配
                         合默认内容类型"application/x-www-form-urlencoded"。如果要发送DOM树信息或者其他不希望转换的信息，请设置
                         为false。
           scriptCharset：要求为String类型的参数，只有当请求时dataType为"jsonp"或者"script"，并且type是GET时才会用于强制修改字符
                          集(charset)。通常在本地和远程的内容编码不同时使用。
        
12. for forEach map对比
     https://segmentfault.com/a/1190000007627597

13. Object.keys()
     Object.keys() 方法会返回一个由一个给定对象的自身可枚举属性组成的数组，数组中属性名的排列顺序和使用 for...in 循环遍历该对象时返
                   回的顺序一致 （两者的主要区别是 一个 for-in 循环还会枚举其原型链上的属性）。    
    
14. each() 方法规定为每个匹配元素规定运行的函数。  返回 false 可用于及早停止循环。
     $(selector).each(function(index,element))   
       function(index,element)   必需。为每个匹配元素规定运行的函数。
       index - 选择器的 index 位置
       element - 当前的元素（也可使用 "this" 选择器）
       
15. trigger() 方法触发被选元素的指定事件类型。
