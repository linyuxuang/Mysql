# Mysql
Mysql 常用函数


  1常用的函数：
  
  
	       1》mysql_connect("主机名称/ip","用户名","密码")   -->建立php ---》mysql连接的 返回资源
	        
	       2》mysql_error(); 返回上mysql操作的文本错误信息
	            @ 错误一直符号
	            
	       3》mysql_select_db("数据库名称","数据库返回的资源") 
	       
	       4》mysql_query(); 向数据库发送一条sql命令 ，理解：执行sql。返回资源
	
	      5》 mysql_affected_rows() 取得前一条sql语句 返回受影响(修改过的哪一行) 的行数   主要对 增(insert)，删(delete)，改(update) 有作用
            
	      6》 mysql_close()    关闭数据库连接


 例子
 
 
       	header("content-type:text/html;charset=utf-8");
        
        连接成功   die()输出内容  终止后边程序
	       $link=@mysql_connect("localhost","root","root") or die("连接数据库失败".mysql_error());
         
         参数1："数据库名称",  参数2： "数据库返回的资源"
         mysql_select_db("pro",$link);
     
         添加语句
         $sql="insert into user(uId, uName, uPwd, uSex, uTel, uEmai) values('2','李四','66666','1','133888888888','12365@qq.com')";
     
         修改语句
         $sql="update user set uId='0' where uName='李四'";
  
        删除语句
         $sql="delete from user where uId=2";
         mysql_query($sql);
	 
	 关闭数据库连接
	   mysql_close($link)








