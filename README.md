# Programs

import org.openqa.selenium.*;
import org.openqa.selenium.chrome.ChromeDriver;
import java.awt.Robot;
import java.awt.event.InputEvent;
import java.awt.*;

public class Program1{

public static void main(String[] args) throws InterruptedException, AWTException {

//Browser intialization

WebDriver driver;
System.setProperty("webdriver.chrome.driver","./src/drivers/chromedriver.exe");
driver =  new ChromeDriver();
driver.get("http://www.htmlcanvasstudio.com/");
Thread.sleep(5000);

driver.findElement(By.xpath("//input[@title='Draw a line']")).click();
Thread.sleep(3000);

Robot robot = new Robot();
robot.mouseMove(250,350);
robot.mousePress(InputEvent.Button1_Down_Mask);
robot.mouseMove(250,510);
robot.mousePress(InputEvent.Button1_Down_Mask);
robot.mouseRelease(InputEvent.Button1_Down_Mask);

robot.mouseMove(170,430);
robot.mousePress(InputEvent.Button1_Down_Mask);
robot.mouseMove(330,430);
robot.mousePress(InputEvent.Button1_Down_Mask);
robot.mouseRelease(InputEvent.Button1_Down_Mask);

System.out.println("Vertical and Horizontal Lines are drawn successfully");

driver.findElement(By.xpath("//input[@title='Draw a rectangle']")).click();
Thread.sleep(3000);

robot.mouseMove(170,550);
robot.mousePress(InputEvent.Button1_Down_Mask);
robot.mouseMove(400,640);
robot.mousePress(InputEvent.Button1_Down_Mask);
robot.mouseRelease(InputEvent.Button1_Down_Mask);

System.out.println("Rectangle has been drawn successfully");

driver.findElement(By.xpath("//input[@title='Use eraser']")).click();
Thread.sleep(3000);

for(int i = 1; i <=4 ; i++)
{
robot.mouseMove(248 + i,330);
robot.mousePress(InputEvent.Button1_Down_Mask);
robot.mouseMove(248 + i,512);
robot.mousePress(InputEvent.Button1_Down_Mask);
robot.mouseRelease(InputEvent.Button1_Down_Mask);

}

System.out.println("Horizontal line has been erased successfully");

}

}
