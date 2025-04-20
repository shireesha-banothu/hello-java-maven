# Hello Java Maven Project

This is a simple Java project that uses Maven to build the application. The project includes a basic HelloWorld program written in Java and a Jenkins pipeline to automate the build process.

## Project Structure:
- `src/main/java/HelloWorld.java`: The main Java source code file that prints "Hello, Jenkins + Maven!".
- `pom.xml`: Maven build configuration file for the project.
- `Jenkinsfile`: Jenkins pipeline configuration to automate the build.

## Prerequisites:
Before starting, ensure you have the following installed on your system:
- **Java JDK 8 or 11**
- **Maven**
- **Jenkins** (local or Docker version)

## Steps for Setup and Execution:

### 1. Install Java:
- Download and install Java JDK from [Oracle's Java Downloads](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).
- Set the `JAVA_HOME` environment variable.
    ```bash
    export JAVA_HOME=/path/to/your/jdk
    export PATH=$JAVA_HOME/bin:$PATH
    ```

### 2. Install Maven:
- Download Maven from the [official Maven website](https://maven.apache.org/download.cgi).
- Extract the Maven archive and set the `MAVEN_HOME` environment variable.
    ```bash
    export MAVEN_HOME=/path/to/your/maven
    export PATH=$MAVEN_HOME/bin:$PATH
    ```

### 3. Create the Java HelloWorld Application:
- Create a directory structure: `src/main/java/`.
    ```bash
    mkdir -p src/main/java
    ```
- In the `src/main/java/` folder, create a file `HelloWorld.java` with the following content:
    ```java
    public class HelloWorld {
        public static void main(String[] args) {
            System.out.println("Hello, Jenkins + Maven!");
        }
    }
    ```

### 4. Create the `pom.xml` (Maven Configuration):
In the project root directory, create the `pom.xml` file with the following Maven configuration:
```xml
<project>
  <modelVersion>4.0.0</modelVersion>
  <groupId>com.example</groupId>
  <artifactId>hello</artifactId>
  <version>1.0</version>
  <build>
    <plugins>
      <plugin>
        <groupId>org.apache.maven.plugins</groupId>
        <artifactId>maven-compiler-plugin</artifactId>
        <version>3.8.1</version>
        <configuration>
          <source>1.8</source>
          <target>1.8</target>
        </configuration>
      </plugin>
    </plugins>
  </build>
</project>

# Jenkins Maven Build – Commands Reference

## System & Git Commands

```bash
# Check Java version
java -version

# Check Maven version
mvn -v

# Clone the repository
git clone https://github.com/shireesha-banothu/hello-java-maven.git
cd hello-java-maven
# Start Jenkins using Docker
docker run -p 8080:8080 jenkins/jenkins:lts

Access Jenkins at: http://localhost:8080

# Add a screenshot or file to staging
git add output_screenshot.png

# If you added a README or multiple files:
git add README.md output_screenshot.png

# Commit the changes
git commit -m "Add README and build success screenshot"

# Push to GitHub
git push origin main
