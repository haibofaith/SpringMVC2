# SpringMVC2
基于注解

1.在springmvc-servlet.xml加入注解驱动
<!-- 加入注解驱动 -->
	<mvc:annotation-driven></mvc:annotation-driven>
	
2.加入扫描器
<!-- 扫描器 -->
	<context:component-scan base-package="com"></context:component-scan>
	
3.写一个controller基于注解：
<code>
@Controller
public class HelloController {
	//返回到index.jsp	
	@RequestMapping(value="/hello.do")
	public String hello(String userName,Model model){
		System.out.println(userName);
		model.addAttribute("helloworld","hello"+userName);
		return "index";
	}
}
</code>
其中：参数userName对应hello.jsp的表单请求参数，
	返回index对应view文件夹index.jsp文件。

4.遇到问题：找不到hello.jsp文件
/SpringMVC2/hello.jsp 404错误：路径错误。原因是将hello.jsp放在web-inf中。

5.出现乱码怎么办？filter

6.如何传递多个参数？把上述controller的方法参数换成对象。




