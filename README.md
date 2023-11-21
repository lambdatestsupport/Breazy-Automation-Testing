# Run Breazley WebAutomation tests with using TestNG On LambdaTest

![image](https://user-images.githubusercontent.com/70570645/171934563-4806efd2-1154-494c-a01d-1def95657383.png)


<p align="center">
  <a href="https://www.lambdatest.com/blog/?utm_source=github&utm_medium=repo&utm_campaign=Java-TestNG-Selenium" target="_bank">Blog</a>
  &nbsp; &#8901; &nbsp;
  <a href="https://www.lambdatest.com/support/docs/?utm_source=github&utm_medium=repo&utm_campaign=Java-TestNG-Selenium" target="_bank">Docs</a>
  &nbsp; &#8901; &nbsp;
  <a href="https://www.lambdatest.com/learning-hub/?utm_source=github&utm_medium=repo&utm_campaign=Java-TestNG-Selenium" target="_bank">Learning Hub</a>
  &nbsp; &#8901; &nbsp;
  <a href="https://www.lambdatest.com/newsletter/?utm_source=github&utm_medium=repo&utm_campaign=Java-TestNG-Selenium" target="_bank">Newsletter</a>
  &nbsp; &#8901; &nbsp;
  <a href="https://www.lambdatest.com/certification/?utm_source=github&utm_medium=repo&utm_campaign=Java-TestNG-Selenium" target="_bank">Certifications</a>
  &nbsp; &#8901; &nbsp;
  <a href="https://www.youtube.com/c/LambdaTest" target="_bank">YouTube</a>
</p>
&emsp;
&emsp;
&emsp;

## Table Of Contents
* [Pre-requisites](#pre-requisites)
* Cloning Repo and Installing Dependencies
* Setting Up Your Authentication
* To run the Tests:
* Run Parallel Tests:

# Pre-requisites:

Before you can start performing Java automation testing with Selenium, you would need to:

Install the latest Java development environment i.e. JDK 1.6 or higher. We recommend using the latest version.

Download the latest Selenium Client and its WebDriver bindings from the official website. Latest versions of Selenium Client and WebDriver are ideal for running your automation script on LambdaTest Selenium cloud grid.

Install Maven which supports JUnit framework out of the box. Maven can be downloaded and installed following the steps from the official website. Maven can also be installed easily on Linux/MacOS using Homebrew package manager.

### Cloning Repo and Installing Dependencies:

Step 1: Clone the LambdaTest’s Breazley-Automation-Testing repository and navigate to the code directory as shown below:

```bash
git clone https://github.com/lambdatestsupport/Breazley-Automation-Testing
cd Breazley-Automation-Testing
```

You can also run the command below to check for outdated dependencies.

```bash
mvn versions:display-dependency-updates
```

### Setting Up Your Authentication:

Make sure you have your LambdaTest credentials with you to run test automation scripts. You can get these credentials from the LambdaTest Automation Dashboard or by your LambdaTest Profile.

**Step 2:** Set LambdaTest **Username** and **Access Key** in environment variables.

* For **Linux/macOS**:
  
  ```bash
  export LT_USERNAME="YOUR_USERNAME" 
  export LT_ACCESS_KEY="YOUR ACCESS KEY"
  ```
  * For **Windows**:
  ```bash
  set LT_USERNAME="YOUR_USERNAME" 
  set LT_ACCESS_KEY="YOUR ACCESS KEY"
  ```

## To run the Tests:
```bash
mvn test -D suite=parallel.xml
mvn test
```

##   Run Parallel Tests:

Here is an xml file location `src/test/java/parallel.xml` which would help you to run parallel test on different devices and browser at the same time.
<?xml version="1.0" encoding="UTF-8"?>
<!DOCTYPE suite SYSTEM "http://testng.org/testng-1.0.dtd">
<suite thread-count="10" name="Desktop" parallel="tests">
    <test thread-count="100" name="Chrome 10">
        <classes>
            <class name="BeazleyChrome10"/>
        </classes>
    </test><!-- Test -->
    <test thread-count="100" name="Chrome 11">
        <classes>
            <class name="beazleyChrome11"/>
        </classes>
    </test><!-- Test -->
    <test thread-count="100" name="Edge 10">
        <classes>
            <class name="beazleyEdge10"/>
        </classes>
    </test><!-- Test -->
    <test thread-count="100" name="Edge 11">
        <classes>
            <class name="beazleyEdge11"/>
        </classes>
    </test><!-- Test -->
     <test thread-count="100" name="Safari 17">
        <classes>
            <class name="MacOSSonomaSafari"/>
        </classes>
    </test><!-- Test -->
     <test thread-count="100" name="Safari 16">
        <classes>
            <class name="beazleyMacOSVenturaSafari"/>
        </classes>
    </test><!-- Test -->

</suite>
