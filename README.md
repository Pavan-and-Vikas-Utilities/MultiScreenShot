# About Developers

##   Pavankumar Nagaraj
   Software Test Engineer
   <a href="pavankumar.nagaraj@gmail.com?Subject=MultiScreenShot %20GitHub" target="_top">pavankumar.nagaraj@gmail.com</a>
  <a href="in.linkedin.com/in/pavankumarnagaraj/">Pavankumar Nagaraj Linkedin Profile</a>
  Mobile:+91 8971673487
  Bangalore.
![image](https://cloud.githubusercontent.com/assets/10204148/5486859/29c114ae-86d1-11e4-8ee2-980a0c3086d5.png)
--------------

##   Vikas Kumar Singh
   Senior Software Test Engineer
  <a href="mailto:mr.vikasdumka@gmail.com?Subject=MultiScreenShot %20GitHub" target="_top">mr.vikasdumka@gmail.com</a>
  <a href="in.linkedin.com/pub/vikas-singh/85/b10/124/">Vikas Kumar Linkedin Profile</a>
  Mobile:+91 8123492801
  Bangalore.
![image](https://cloud.githubusercontent.com/assets/10204148/5486910/97a7600e-86d1-11e4-9da8-6a0a59e2bc58.png)


# MultiScreenShot

This class helps the WebDriver 2.0 users to take multiple screenshots and element screenshots and mininimize the browser.


## Constructor Details:
This construtor accepts two argument one is the path where to save the screenshots
public MultiScreenShot(String path,String className)

### Eg:
path=C:\\Users\\xxxxxx\\Desktop\New folder\\TestMultiScreenShot_Screenshots\\

and another argument is className,we are using this class name to create the folder and save the screenshot inside that.

### Eg:
className=MultiScreenShot


## Methods Details:
### public void multiScreenShot(WebDriver driver) throws IOException

Takes the full screenshot of page whenever you call the method and this method accepts WebDriver object as argument

### Eg:
``` Java
mShot.multiScreenShot(driver);
```

### public void elementScreenShot( WebDriver driver,WebElement element) throws IOException  

Takes the element screenshot in a page whenever you call the method and this method accepts 2 arguments one is WebDriver object as argument and another one is WebElement object,(i.e ) which element we want to take as screenshot

### Eg:
``` Java
mShot.elementScreenShot(driver, driver.findElement(By.id("search-submit")));
```

### public void minimize() throws AWTException

This method minimizes the browser window if the browser is maximized on windows os,it does not accept any arguments

``` Java
	mShot.minimize();
```

***************************************************************************************************************************

### Example:
Associate the MultiScreenshot.jar file in your project by navigating
Right click on project>Properties>Java Build path>Add Externar jars.

![jar](https://cloud.githubusercontent.com/assets/10204148/5450342/25a93fa2-852a-11e4-8a30-a325054f00be.jpg)




``` Java
package testPackage;

import java.awt.AWTException;
import java.io.IOException;

import org.openqa.selenium.By;
import org.openqa.selenium.WebDriver;
import org.openqa.selenium.firefox.FirefoxDriver;

import multiScreenShot.MultiScreenShot;

public class TestMultiScreenShot 
{
	
	
	public static void main(String[] args) throws IOException, AWTException 
	{
		
	  MultiScreenShot mShot=new MultiScreenShot("C:\\xxxx\\Desktop\\New\\","TestMultiScreenShot");
		WebDriver driver =new FirefoxDriver();
		driver.get("https://google.com");
		
		//maximze the window
		driver.manage().window().maximize();
		
		//take full screenshot using MultiScreenShot class
		mShot.multiScreenShot(driver);
		
		//take element screenshot using MultiScreenShot class
		mShot.elementScreenShot(driver, driver.findElement(By.id("gbqfq")));
		
		//navigate to yahoo
		driver.navigate().to("https://yahoo.in");
		
		//take element screenshot using MultiScreenShot class
		mShot.elementScreenShot(driver, driver.findElement(By.id("search-submit")));
		
		//take full screenshot using MultiScreenShot class
		mShot.multiScreenShot(driver);
		
		//minimize the window using MultiScreenShot class
		mShot.minimize();
		
		driver.quit();
		
	}

}
```

## Output will look like below one

![output](https://cloud.githubusercontent.com/assets/10204148/5450009/f7b098ca-8524-11e4-942f-68aa77705b2d.jpg)
