---
title: Java Web以输入输出流实现读取数据库图片
mathjax: true
tags:
  - Java
  - Web
  - JSP
  - 输入输出流
  - 数据库
categories: 编程开发
date: 2019-03-19 11:32:05
---
在web开发中，读取显示图片非常常见，实现方式也有很多，下面介绍一种以流的形式实现读取数据库图片。java环境：eclipse，数据库：MySQL。
其他过程忽略，只写Servlet和jsp代码。
# Servlet写法
``` bash
  		public String imgAddr;
	protected void doPost(HttpServletRequest request, HttpServletResponse response) throws ServletException, IOException {
        request.setCharacterEncoding("UTF-8");
      	response.setCharacterEncoding("UTF-8");
      	response.setContentType("text/html;charset=UTF-8");

      	HttpSession session = request.getSession();
      	String op = request.getParameter("op");

      	switch (op) {
            case "showimg":
			           imgRead(request, response,imgAddr);
			           break;
		default:
			break;
		}
  }
	private void imgRead(HttpServletRequest request, HttpServletResponse response, String imgAddr) throws ServletException, IOException {
			// 本地文件路径
			String filePath = "E:" + File.separator + "Users" + File.separator + "Yohua " + File.separator + "weixinapp "
					+ File.separator + "Medical_master" + File.separator + imgAddr;
			File file = new File(filePath);
			// 获取输出流
			OutputStream outputStream = response.getOutputStream();
			FileInputStream fileInputStream = new FileInputStream(file);
			// 读数据
			byte[] data = new byte[fileInputStream.available()];
			fileInputStream.read(data);
			fileInputStream.close();
			// 回写
			response.setContentType(JPG);
			outputStream.write(data);
			outputStream.flush();
			outputStream.close();
		}
```

# JSP代码
``` bash
<body>
<img alt="showImage" src="AdminServlet?op=showimg">
</body>
```
