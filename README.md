# shareCircle
package test_scenarios_2;

import org.testng.annotations.Test;

import objects_ShareCircle.Locators;
import utilities_ShareCircle.CommonFunctions;

import org.testng.annotations.BeforeClass;

import java.io.File;
import java.io.FileInputStream;
import java.io.FileNotFoundException;
import java.io.IOException;
import java.util.Properties;

import org.openqa.selenium.By;
import org.openqa.selenium.WebElement;
import org.testng.Assert;
import org.testng.annotations.AfterClass;

public class CustomerLoginChecking 
	extends CommonFunctions {
		Locators loc = new Locators();
		 CommonFunctions comm = new  CommonFunctions();
		 Properties prop = new Properties();
			File f = new File(".\\testdata\\data.properties");
  @Test
  public void checkingwithout_values() throws IOException, Exception {
	  FileInputStream fi = new FileInputStream(f);
		prop.load(fi);
	  comm.ClickableByXPath(Locators.Xpath_LOgin_Button);
	//  comm.sendKeysByName(Locators.NAME_Login_UserName,prop.getProperty("Usname"));
	//  comm.sendKeysByName(Locators.NAME_Login_Password,prop.getProperty("Password"));
	  Thread.sleep(500);
	  /*comm.ClickableByXPath(Locators.XPATH_Sign_BUTTON);
	 WebElement e_user= driver.findElement(By.xpath("//*[@id='login_form']/div[1]/em"));
	 System.out.println(e_user.getText());
	 Assert.assertEquals(e_user.getText(), prop.getProperty("alert1"));
	 WebElement e_password= driver.findElement(By.xpath("//*[@id='login_form']/div[2]/em"));
	 System.out.println(e_password.getText());
	 Assert.assertEquals(e_password.getText(), prop.getProperty("alert2"));*/
	 
	 comm.ClickableById(loc.id_fb);
	 Thread.sleep(3000);
	// comm.ClickableById(loc.id_google);
	
		
	
	  
	  
	  
  }
  @Test
  
  @BeforeClass
  public void beforeClass() throws IOException {
	  FileInputStream fi = new FileInputStream(f);
		prop.load(fi);
	  comm.getAndOpenBrowser("chrome");
	comm.launchURL(prop.getProperty("URL"));
  }

  @AfterClass
  public void afterClass() {
	  driver.quit();
  }
  

}
