gvi-fqbn-jcm

Rakesh Perala
19:47
https://github.com/devops-perala/java-maven-hoststar.git

Rakesh Perala
20:10
# Apache Maven — Complete DevOps Training 2026

> **Ubuntu + Java 21/25 LTS + Apache Maven 3.9.x + Enterprise DevOps**

---

# Table of Contents

1. [What is Maven?](#what-is-maven)
2. [Why do we need Maven?](#why-do-we-need-maven)
3. [Maven Build Process](#maven-build-process)
4. [JAR vs WAR](#jar-vs-war)
5. [Maven 2026 Setup](#maven-2026-setup)
6. [Maven Terminology](#maven-terminology)
7. [Why pom.xml is Important](#why-pomxml-is-important)
8. [Basic pom.xml](#basic-pomxml)
9. [pom.xml Structure](#pomxml-structure)
10. [Maven Project Structure](#maven-project-structure)
11. [Maven Project Creation](#maven-project-creation)
12. [Maven Lifecycle](#maven-lifecycle)
13. [Maven Goals](#maven-goals)
14. [Maven Dependencies](#maven-dependencies)
15. [Transitive Dependencies](#transitive-dependencies)
16. [Dependency Exclusion](#dependency-exclusion)
17. [Dependency Scope](#dependency-scope)
18. [Maven Repositories](#maven-repositories)
19. [settings.xml](#settingsxml)
20. [Maven Profiles](#maven-profiles)
21. [Maven + Git](#maven--git)
22. [Maven + Jenkins](#maven--jenkins)
23. [Maven + SonarQube](#maven--sonarqube)
24. [Maven + Docker](#maven--docker)
25. [Maven + Nexus / JFrog](#maven--nexus--jfrog)
26. [SNAPSHOT vs RELEASE](#snapshot-vs-release)
27. [Maven Troubleshooting](#maven-troubleshooting)
28. [Enterprise Maven Project](#enterprise-maven-project)
29. [DevOps Engineer Checklist](#devops-engineer-checklist)
30. [Interview Questions](#maven-interview-questions)
31. [Final Enterprise Flow](#final-enterprise-flow)

---

# What is Maven?

Maven is a **build automation and project management tool** mainly used for Java/JVM projects.

Maven is:

* Free
* Open source
* Written in Java
* Widely used in enterprise Java projects
* Commonly integrated with CI/CD tools

Maven helps us automate:

```text
Download Dependencies
        ↓
Compile Source Code
        ↓
Run Unit Tests
        ↓
Perform Verification
        ↓
Package Application
        ↓
Install Artifact
        ↓
Deploy Artifact
```

---

# Why do we need Maven?

Suppose we are developing a Java application.

Our application may require:

```text
Spring
Spring Boot
JUnit
Mockito
Jackson
Kafka
Redis
MySQL Driver
PostgreSQL Driver
Log4j
```

Without Maven, developers may need to manually:

```text
Download JAR files
        ↓
Copy JAR files
        ↓
Configure classpath
        ↓
Compile Java code
        ↓
Run tests
        ↓
Create JAR/WAR
        ↓
Manage library versions
```

This becomes difficult in enterprise projects.

With Maven:

```text
                 pom.xml
                    |
                    v
             Maven reads config
                    |
        +-----------+-----------+
        |           |           |
        v           v           v
   Dependencies   Compile      Test
        |           |           |
        +-----------+-----------+
                    |
                    v
                 Package
                    |
                    v
                JAR / WAR
                    |
                    v
             Repository
                    |
                    v
               Deployment
```

---

# Maven Build Process

Maven can automate the Java project build process.

## 1. Download Dependencies

Examples:

```text
Spring
JUnit
Kafka
Redis
Jackson
MySQL Driver
PostgreSQL Driver
```

## 2. Compile Source Code

```text
src/main/java
       ↓
     javac
       ↓
target/classes
```

## 3. Execute Unit Tests

```text
src/test/java
       ↓
JUnit / Mockito
       ↓
Test Result
```

## 4. Package Application

```text
Java Application
       ↓
     Maven
       ↓
JAR / WAR
```

## 5. Install Artifact

```text
JAR / WAR
    ↓
~/.m2/repository
```

## 6. Deploy Artifact

Enterprise example:

```text
Developer
    ↓
Git
    ↓
Jenkins
    ↓
Maven
    ↓
JAR
    ↓
Nexus / JFrog
    ↓
Docker
    ↓
ECR
    ↓
EKS
```

---

# JAR vs WAR

## JAR

Standalone Java applications are commonly packaged as:

```text
.jar
```

Example:

```text
