# TestNG Commands CheatSheet

## Setup & Installation

### Add TestNG to your Maven project
```xml
<dependency>
    <groupId>org.testng</groupId>
    <artifactId>testng</artifactId>
    <version>7.x.y</version>
    <scope>test</scope>
</dependency>
```

### Install TestNG plugin for Eclipse
Go to Help > Eclipse Marketplace > Search "TestNG" > Install

### Define a test method
```java
@Test
public void testMethod() {
    // Test code
}
```

---

## TestNG Annotations

### Run code before each test method
```java
@BeforeMethod
public void setUp() {
    // Setup code
}
```

### Run code after each test method
```java
@AfterMethod
public void tearDown() {
    // Cleanup code
}
```

### Run code before the test class
```java
@BeforeClass
public void beforeClass() {
    // Initialization code
}
```

### Run code after the test class
```java
@AfterClass
public void afterClass() {
    // Finalization code
}
```

---

## Assertions

### Assert equality
```java
Assert.assertEquals(actual, expected);
```

### Assert true condition
```java
Assert.assertTrue(condition);
```

### Assert false condition
```java
Assert.assertFalse(condition);
```

### Fail a test explicitly
```java
Assert.fail("Test failed due to condition");
```

### Run code once before the entire suite
```java
@BeforeSuite
public void beforeSuite() {
    // Suite setup code
}
```

---

## Parameterization

### Pass parameters via XML file
```xml
<parameter name="url" value="https://example.com" />
```

### Retrieve parameters in test methods
```java
@Parameters("url")
public void testMethod(String url) {
    System.out.println(url);
}
```

### Use DataProvider for data-driven tests
```java
@DataProvider(name = "data")
public Object[][] dataProvider() {
    return new Object[][] { {"value1"}, {"value2"} };
}

@Test(dataProvider = "data")
public void testMethod(String value) {
    System.out.println(value);
}
```

### Run code once after the entire suite
```java
@AfterSuite
public void afterSuite() {
    // Suite cleanup code
}
```

---

## Grouping & Prioritization

### Group tests
```java
@Test(groups = {"group1"})
public void testMethod() {
    // Test code
}
```

### Prioritize tests
```java
@Test(priority = 1)
public void firstTest() {
    // Runs first
}
```

### Exclude groups in testng.xml
```xml
<groups>
    <exclude name="group1" />
</groups>
```

### Retry failed tests
```java
public class RetryAnalyzer implements IRetryAnalyzer {
    private int count = 0;
    private static final int maxTry = 3;

    @Override
    public boolean retry(ITestResult result) {
        if (count < maxTry) {
            count++;
            return true;
        }
        return false;
    }
}
```

---

## Reporting & Logs

### Add logs in test methods
```java
Reporter.log("Log message", true);
```

### Generate TestNG default report
After execution, view the `test-output` folder for reports.

### Parallel execution in testng.xml
```xml
<suite name="Suite" parallel="tests" thread-count="4">
    <test name="Test">
        <classes>
            <class name="com.example.TestClass" />
        </classes>
    </test>
</suite>
```

---

## Master TestNG Automation Framework
Enhance your automation skills with TestNG and build robust test frameworks with different annotations and configurations.



