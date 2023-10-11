# LoginTest
OrangeHRM Login Test - Selenium

package LoginTestPack;

import java. time.Duration;

import org.openqa.selenium.By;
import org.openqa.selenium.WebDriver;
import org.openqa.selenium.WebElement;
import org.openqa.selenium.chrome.ChromeDriver;

public class OrangeHRMLoginTest {

	public static void main(String[] args) throws InterruptedException {
		
		//Launch browser

		WebDriver driver = new ChromeDriver();
		driver.manage().timeouts().implicitlyWait(Duration.ofSeconds(10));

		//Open URL: https://opensource-demo.orangehrmlive.com/web/index.php/auth/login
		
		driver.get("https://opensource-demo.orangehrmlive.com/web/index.php/auth/login");
		driver.manage().window().maximize();
		
		//Provide UserName: Admin
		//Provide Password: admin123
		
		driver.findElement(By.xpath("//input[@placeholder='Username']")).sendKeys("Admin");
		driver.findElement(By.xpath("//input[@placeholder='Password']")).sendKeys("admin123");
		//Click on Login button
		driver.findElement(By.xpath("//button[normalize-space()='Login']")).click();
		
		WebElement ActText = driver.findElement(By.xpath("//title[normalize-space()='OrangeHRM']"));
		
		String Txt = driver.getTitle();
		System.out.println(Txt);
		String ExpText = "OrangeHRM";
		
		if(Txt.equals(ExpText))
		{
			System.out.println("Test is Passed");
		}
		else {
			System.out.println("Test is Failed");
		}
		
		
		
		
		
		
	}

}

