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

9. 
   
