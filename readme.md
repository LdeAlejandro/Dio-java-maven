
 ```bash
mvn archetype:generate -DgroupId=one.digitalinnovation -DartifactId=quick-start-maven -DarchetypeArtifactId=maven-archetype-quickstart -DinteractiveMode=false
mvn archetype:generate -DgroupId=one.digital.innovation -DartifactId=project-parent -Darchetype=maven-archetype-quickstart
mvn compile
mvn test
mvn package

mvn clean

mvn dependency:analyze

mvn dependency:build-classpath -DincludeScope=compile
mvn dependency:build-classpath -DincludeScope=runtime
mvn dependency:build-classpath -DincludeScope=
```
## criando projeto multimodulo
 ```bash
mvn archetype:generate -DgroupId=one.digital.innovation -DartifactId=project-parent -Darchetype=maven-archetype-quickstart
mvn archetype:generate -DgroupId=one.digital.innovation -DartifactId=controller -Darchetype=maven-archetype-quickstart -DinterativeMode=false
mvn archetype:generate -DgroupId=one.digital.innovation -DartifactId=core -Darchetype=maven-archetype-quickstart -DinterativeMode=false
mvn archetype:generate -DgroupId=one.digital.innovation -DartifactId=service -Darchetype=maven-archetype-quickstart -DinterativeMode=false
```

# Maven Quick Start Guide

## **Basic Maven Commands**

### **Create a Basic Maven Project**
```bash
mvn archetype:generate -DgroupId=one.digitalinnovation -DartifactId=quick-start-maven -DarchetypeArtifactId=maven-archetype-quickstart -DinteractiveMode=false
```

### **Compile the Project**
```bash
mvn compile
```

### **Run Unit Tests**
```bash
mvn test
```

### **Package the Application**
Generates a JAR or WAR file in the `target` directory:
```bash
mvn package
```

### **Clean the Project**
Removes the `target` directory:
```bash
mvn clean
```

---

## **Dependency Management**

### **Analyze Dependencies**
Checks for unused or undeclared dependencies:
```bash
mvn dependency:analyze
```

### **Build Classpath for Dependencies**
- Include only compile-time dependencies:
  ```bash
  mvn dependency:build-classpath -DincludeScope=compile
  ```
- Include runtime dependencies:
  ```bash
  mvn dependency:build-classpath -DincludeScope=runtime
  ```
- Include all dependencies:
  ```bash
  mvn dependency:build-classpath -DincludeScope=
  ```

---

## **Creating a Multi-Module Project**

### **Step 1: Create the Parent Project**
```bash
mvn archetype:generate -DgroupId=one.digital.innovation -DartifactId=project-parent -Darchetype=maven-archetype-quickstart
```

### **Step 2: Create Submodules**
1. **Controller Module**:
   ```bash
   mvn archetype:generate -DgroupId=one.digital.innovation -DartifactId=controller -Darchetype=maven-archetype-quickstart -DinteractiveMode=false
   ```
2. **Core Module**:
   ```bash
   mvn archetype:generate -DgroupId=one.digital.innovation -DartifactId=core -Darchetype=maven-archetype-quickstart -DinteractiveMode=false
   ```
3. **Service Module**:
   ```bash
   mvn archetype:generate -DgroupId=one.digital.innovation -DartifactId=service -Darchetype=maven-archetype-quickstart -DinteractiveMode=false
   ```

### **Parent POM Structure**
Ensure the `parent` project has a `pom.xml` file with modules listed:
```xml
<modules>
    <module>controller</module>
    <module>core</module>
    <module>service</module>
</modules>
```

---

## **Key Notes**
- **`groupId`**: Identifies the group or organization.
- **`artifactId`**: Name of the project or module.
- **`archetypeArtifactId`**: Specifies the Maven archetype template to use.
- **Multi-module Projects**: The parent project coordinates and aggregates submodules, which can be compiled and packaged together.

