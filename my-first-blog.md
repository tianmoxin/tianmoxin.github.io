title: Test
date: 2017-01-06 17:31:53
tags: js


```html
<!DOCTYPE html>
<html>
    <head>
        <meta charset="UTF-8">
        <title></title>
        <script type="text/javascript">
            //用户名的验证        
            function focus_username () {
                var result= document.getElementById("result_uername");
                result.innerHTML="请输入用户名!";
                result.style.color="deepskyblue";
            }
            
            function blur_username () {
                var result= document.getElementById("result_uername");
                if (document.form1.username.value=="") {
                    result.innerHTML="用户名不能为空！";
                    result.style.color="red";
                    return false;
                }
                else if(document.form1.username.value.Length<5 || document.form1.username.value.Length>20){
                    result.innerHTML="用户名长度介于5到20之间！";
                    result.style.color="red";
                    return false;
                }
                else
                {
                    result.innerHTML="合法";
                    return true;
                }
            }
            
            //密码验证
            function focus_userpwd () {
                var result= document.getElementById("result_userpwd");
                result.innerHTML="请输入密码!";
                result.style.color="deepskyblue";
            }
            
            function blur_userpwd () {
                var result= document.getElementById("result_userpwd");
                if (document.form1.username.value=="") {
                    result.innerHTML="用户名不能为空！";
                    result.style.color="red";
                    return false;
                }
                else if(document.form1.userpwd.value.Length<5 || document.form1.userpwd.value.Length>20){
                    result.innerHTML="用户名长度介于5到20之间！";
                    result.style.color="red";
                    return false;                    
                }
                else
                {
                    result.innerHTML="合法";
                    return true;
                }
            }
            
            function checkForm () {
                var flag_username= blur_username();
                var flag_userpwd= blur_userpwd();
                if (flag_username && flag_userpwd) {
                    return true;
                } else{
                    return false;
                }
            }
        </script>
    </head>
    <body>
    <form name="form1" method="post" action="login.php" onsubmit="return checkForm()">
        <table border="1" cellspacing="0" cellpadding="5" width="600" rules="all" bordercolor="#ccc" align="center">
            <tr>
                <td width="100" align="right">用户名：</td> 
                <td><input type="text" id="username" onfocus="focus_username()" onblur="blur_username()"/></td> 
                <td width="300"><div id= "result_uername"></div></td>
            </tr>
            <tr>
                <td  align="right">密码：</td> 
                <td><input type="password" id="userpwd" onfocus="focus_userpwd()" onblur="blur_userpwd()"/></td> 
                <td ><div id= "result_userpwd"></div></td>
            </tr>
            <tr>
                <td>&nbsp;</td> 
                <td colspan="2">
                    <input type="submit" value="提交表单" />
                    <input type="reset" value="重置表单" />
                </td> 
            </tr>
        </table>
    </form>
    </body>
</html>

```
