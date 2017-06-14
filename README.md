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
