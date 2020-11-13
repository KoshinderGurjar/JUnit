package com.lambdatest.Tests;

import org.junit.*;
import org.openqa.selenium.By;
import org.openqa.selenium.InvalidElementStateException;
import org.openqa.selenium.JavascriptExecutor;

public class ParallelTest extends TestBase {

	public static String status = "failed";

	public ParallelTest(String osName, String browserName, String browserVersion) {
		super(osName, browserName, browserVersion);
	}

	@Test
	public void testParallelTest() throws Exception {
		try {
			// Launch the app
			driver.get("https://lambdatest.github.io/sample-todo-app/");

			// Click on First Item
			driver.findElement(By.name("li1")).click();

			// Click on Second Item
			driver.findElement(By.name("li2")).click();

			// Add new item is list
			driver.findElement(By.id("sampletodotext")).clear();
			driver.findElement(By.id("sampletodotext")).sendKeys("Yey, Let's add it to list");
			driver.findElement(By.id("addbutton")).click();

			// Verify Added item
			String item = driver.findElement(By.xpath("/html/body/div/div/div/ul/li[6]/span")).getText();
			Assert.assertTrue(item.contains("Yey, Let's add it to list"));
			status = "passed";
		}

		catch (Exception e) {
			System.out.println(e.getMessage());
			throw e;
		} finally {
			((JavascriptExecutor) driver).executeScript("lambda-status=" + status + "");
		}

	}

}
