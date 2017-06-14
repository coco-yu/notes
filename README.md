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
   
7. 
   
