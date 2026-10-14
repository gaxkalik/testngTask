# QA Automation TestNG Training API Library

[![Build Status](https://img.shields.io/badge/build-passing-brightgreen.svg)](#)
[![Java Version](https://img.shields.io/badge/Java-17%2B-blue.svg)](#)
[![TestNG](https://img.shields.io/badge/TestNG-7.10.2-orange.svg)](#)
[![Functions](https://img.shields.io/badge/Testable%20Functions-87-success.svg)](#)

A Java domain and utility API library specifically architected for QA Automation courses and workshops. Students import the compiled JAR into their testing projects, inspect the documentation and contracts, and design comprehensive unit test suites using **TestNG**.

---

## 📌 Project Highlights
- **Pure Java Business API**: No REST, HTTP, or mock servers needed. 100% focused on pure Java unit testing.
- **87 Testable Functions**: Far exceeding the 50-function requirement, enabling 85–120+ unique test cases.
- **Realistic Domain Architecture**: E-Commerce checkout, account security, product catalogs, inventory management, coupons, order state machines, and loyalty rewards.
- **Full TestNG Training Coverage**:
  - Assertions (`assertEquals`, `assertTrue`, `assertFalse`, `assertNull`, `assertSame`, `assertThrows`)
  - Exception Testing (`@Test(expectedExceptions = ...)`)
  - Data-Driven Testing (`@DataProvider`)
  - Test Dependencies and State Transitions (`@Test(dependsOnMethods = ...)`)
  - Test Grouping (`groups = {"smoke", "regression", "security", "boundary"}`)
  - Lifecycle Fixtures (`@BeforeMethod`, `@AfterMethod`, `@BeforeClass`)

---

## 📦 How to Build the JAR

To compile the library and generate the exportable JARs:

```bash
mvn clean package
```

The resulting files will be generated in `target/`:
- `target/testingTask-1.0.0.jar` — **Main JAR for students**
- `target/testingTask-1.0.0-javadoc.jar` — **Complete Javadoc bundle**
- `target/testingTask-1.0.0-sources.jar` — Source code bundle

---

## 🚀 How Students Import the JAR in Maven

When students receive `testingTask-1.0.0.jar` and `testingTask-1.0.0-javadoc.jar`, they can install them together into their local Maven cache:

### 1. Install JAR and Javadoc to Local Maven Cache

Open a terminal in the folder containing the downloaded JARs and run:

```bash
mvn install:install-file \
  -Dfile=testingTask-1.0.0.jar \
  -Djavadoc=testingTask-1.0.0-javadoc.jar \
  -DgroupId=am.gortsup \
  -DartifactId=testingTask \
  -Dversion=1.0.0 \
  -Dpackaging=jar \
  -DgeneratePom=true
```

*(On Windows PowerShell, run the command on a single line without the `\` backslashes).*

> **Tip**: Including `-Djavadoc=testingTask-1.0.0-javadoc.jar` automatically attaches the Javadoc to the artifact in Maven.

### 2. Add Dependency to `pom.xml`

In the student's test project `pom.xml`, add the library dependency and TestNG:

```xml
<dependencies>
    <!-- QA Training API Library -->
    <dependency>
        <groupId>am.gortsup</groupId>
        <artifactId>testingTask</artifactId>
        <version>1.0.0</version>
    </dependency>

    <!-- TestNG -->
    <dependency>
        <groupId>org.testng</groupId>
        <artifactId>testng</artifactId>
        <version>7.10.2</version>
        <scope>test</scope>
    </dependency>
</dependencies>
```

---

## 📖 How Students Use the Javadoc Bundle

The `testingTask-1.0.0-javadoc.jar` contains HTML documentation, method signatures, parameter specifications, and exception rules. Students can use it in two ways:

### 1. In-IDE Quick Documentation & Tooltips (IntelliJ IDEA / Eclipse)

Because the Javadoc was attached via `-Djavadoc` during the `mvn install:install-file` step:
- **Hover**: Hover the mouse over any class or method (e.g. `ValidationUtils.isValidPassword`, `OrderService.payOrder`) to view its full documentation pop-up.
- **Shortcuts**:
  - **IntelliJ IDEA**: Press `F1` (macOS) or `Ctrl + Q` (Windows/Linux) on any method name to open the **Quick Documentation** tool window.
  - **Eclipse**: Press `F2` or `Shift + F2` to open the attached Javadoc view.

*If not installed via Maven*, students can attach it manually in IntelliJ IDEA:
1. Go to **File** -> **Project Structure** -> **Libraries**.
2. Select `am.gortsup:testingTask:1.0.0`.
3. Click the **`+`** icon at the bottom, select **Attach Files or Directories...**, and choose `testingTask-1.0.0-javadoc.jar`.

### 2. Browse as an Offline Website in a Web Browser

Since a Javadoc JAR is a standard zip archive:
1. Extract the file:
   ```bash
   unzip testingTask-1.0.0-javadoc.jar -d javadoc
   # On Windows: rename testingTask-1.0.0-javadoc.jar to testingTask-1.0.0-javadoc.zip and extract
   ```
2. Open `javadoc/index.html` in any web browser (Chrome, Safari, Firefox).
3. Students can search and read all class and method contracts in an organized website without needing an internet connection.

---

## 📚 Complete API Documentation

For the full specification of all **87 functions**, input parameters, return values, exception conditions, and **85+ recommended test scenarios**, please read:

👉 **[DOCUMENTATION.md](DOCUMENTATION.md)**
