
# Artifact Management

- [Blog](https://medium.com/@mistazidane/artifact-management-ad7768c3ca00)

## 🔧 What Is Artifact Management?

Artifact management is the process of storing, versioning, and managing binary files(aka artifacts) that are generated during the software build process. These can include:

JAR, WAR, EAR files (Java)
NPM packages (JavaScript)
Docker images
Python wheels (`.whl`) or eggs
Helm charts
and more...

Instead of storing artifacts directly in your source repo (like Git), you use a repository manager like Nexus or JFrog Artifactory.

---

## 📦 What Is Nexus Repository Manager?

Nexus (by Sonatype) is a popular artifact repository manager that allows you to:

Host your own private repositories (Maven, npm, Docker, PyPI, etc.)
Proxy public repositories (e.g. Maven Central, npmjs.org) so your builds don't break if upstream goes down
Group repositories for easier access by developers

---

## ✅ What You’ll Learn (Beginner to Intermediate)

 1. Basic Concepts

What is an artifact
Types of repositories: *hosted*, *proxy*, *group*
Nexus architecture overview

2. Installing Nexus

Install Nexus Repository Manager OSS (open-source edition)
Run it locally (on Docker or bare metal)
Access the web UI

 3. Repository Management

Create a Maven/npm/Docker/PyPI repository
Upload/download artifacts
Set up a proxy to public repos
Create a group repo

 4. Integrate with Build Tools

Use Nexus with:

  Maven (`settings.xml`)
  Gradle
  npm
  Docker

 5. Security & Users

Create users and roles
Set access control

---

### 🎯 1. What is Artifact Management?

 🧱 What is an Artifact?

In software development, an artifact*is any file that is produced as a result of building your code. Examples include:

Compiled files like `.jar`, `.war`, `.exe`
Package files like `.zip`, `.tar.gz`, `.whl`
Docker images
Libraries and dependencies
Configuration files (like Helm charts)

---

### 📦 Why Do We Need Artifact Management?

In real-world software projects:

Your application is built many times (daily or with each commit).
Each build produces artifacts.
These need to be stored safely, versioned, and retrievable later (for deployment or rollback).
You also need to share these artifacts across teams or services.

That's where artifact repository managers come in.

---

## 🛠️ 2. What is Nexus Repository Manager?

Nexus Repository Manager (by [Sonatype](https://www.sonatype.com/)) is a tool that:

Stores artifacts (binaries, packages)
Acts as a cache (proxy)*for public repositories (like Maven Central or npm)
Lets you create private/internal repositories
Controls access*(permissions, authentication)
Supports many formats:

  Maven (Java)
  npm (JavaScript)
  PyPI (Python)
  Docker
  NuGet (.NET)
  Helm (Kubernetes)
  Raw (any files)

---

## 🧰 3. Types of Repositories in Nexus

Repository Type     Description

Hosted  Local repo where you upload your own artifacts
Proxy   Caches remote public repositories (e.g., Maven Central)
Group   Combines multiple repositories into one (simplifies configuration for clients)

---

💡 Example Scenario (Java Project)

Let’s say you’re working on a Java project using Maven. You want to:

1. Use libraries from Maven Central → Nexus proxy repo.
2. Store your build artifacts (.jar files) → Nexus hosted repo.
3. Make developers use a single endpoint → Nexus group repo.

---

## ✅ Summary of What You Know So Far:

Concept Explanation 

Artifact    Output from the build process (like `.jar`, `.whl`, or Docker image)
Artifact Management     The process of storing, versioning, retrieving build outputs
Nexus   A tool to manage artifacts, acting as a private or proxy repository
Repository Types    Hosted (your artifacts), Proxy (remote cache), Group (combination)

---
