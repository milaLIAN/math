- 线程组
  - 线程数
  - Ramp-Up 时间(秒)：需要多少时间能够实现所有线程的生成
  - 集合点：
    - 添加——>定时器——>syncharonizing Timer
- 取样器(人为实现脚本)

  - chrome->检查->network
  - jmeter:[人工实现脚本](https://www.bilibili.com/video/BV1hL4y1B7Et?p=4&vd_source=16f4bafb6f36ee2d7f0055c3cd74a17c)
  - 添加-->sample-->http 请求

- 监听器

  - 根节点——>添加——>监听——>查看结果树

- http 请求默认值
  - 可以设置协议 http
  - 服务器名称或 IP
  - 将默认值应用于所有中，然后将所有 http 请求中的 IP 地址修改
- 定时器
  - 在时间发生之前进行时间等待
  - 固定时间定时器/测试时间进行时间模拟
- 压力测试(**以下内容的 jmeter 均是 jmeter 文件路径**)

  - jmeter -n -t 文件.jmx -l log.jtl
    > - 用户数量=线程数，所以直接更改线程数量即可
    > - 在.jmx 文件目录中直接敲 cmd，之后输入上述命令行
    > - 运行结束后生成的文件即结果文件
    > - .jtl 文件更改后缀为 csv，即可使用 excel 进行查找
  - 产生图表
    - jmeter -g log.jtl -o report1
    - 产生 report1 目录，里面的 index.html 文件即报告
    - -o 后面的目录不能存在或者内容为空，否则就会报错
    - 结果
      > apdex:满意度，1 是 100%
      > 最后的图片 pass 表示全部通过
      > 数据分析：根据 api 这些动态数据进行分析，静态数据可以提前加载以此来保证加载时间不会过长
      > 并发连接数、流量

- cookie 管理器

  - 需要登录 login
  - 在测试根节点中添加 cookie 管理器

- 后置管理器
  - 管理后台的任务
- csv 文件
  - 添加——>配置文件——>csv config
- 评分标准
  - 根节点完成内容
    - 线程名称
    - 线程数：用户数量
    - 启动时间：根据线程数的增加而增加
    - 运行时间：持续时间
  - 事件节点完成内容
    - 事务：事务管理器(添加——>逻辑控制器——>事务管理器)
      - 将所有事务都移交到该内容下面
    - 集结点：添加——>定时器——>synchronizing Timer——>选择集合的线程数量
    - 参数化

```java
import org.openqa.selenium.chrome.ChromeDriver;
import org.openqa.selenium.WebDriver;
import org.openqa.selenium.WebElement;
import org.openqa.selenium.By;

@SuppressWarnings("unused")
public class Example {

    // Mooctest Selenium Example


    // <!> Check if selenium-standalone.jar is added to build path.

    public static void test(WebDriver chromeDriver) {
        // TODO Test script
        // eg:driver.get("https://www.baidu.com/")
        // eg:driver.findElement(By.id("wd"));


    	try {

        	chromeDriver.get("");
        	chromeDriver.manage().window().maximize();
        	chromeDriver.findElement(By.id("")).click();
        	Thread.sleep(1500);
        	chromeDriver.findElement(By.linkText("")).click();
        	Thread.sleep(1500);
        	chromeDriver.findElement(By.xpath("")).click();
        	Thread.sleep(1500);
        	chromeDriver.findElement(By.cssSelector("")).click();
        	Thread.sleep(1500);
        	chromeDriver.findElement(By.name("")).click();
        	Thread.sleep(1500);
        	chromeDriver.findElement(By.className("")).click();
        	Thread.sleep(1500);
          //如果出现需要跳转但是不需要关闭的情况直接跳转即可
          //关掉页面的情况也是直接进行就可以.close()
        	chromeDriver.switchTo().window(chromeDriver.getWindowHandles().toArray()[6].toString());
        	Thread.sleep(1500);



		} catch (InterruptedException e) {
			// TODO Auto-generated catch block
			e.printStackTrace();
		}




    }

    public static void main(String[] args) {
        // Run main function to test your script.
        WebDriver chromeDriver = new ChromeDriver();
        try { test(chromeDriver); }
        catch(Exception e) { e.printStackTrace(); }
        finally { chromeDriver.quit(); }
    }

}

```
