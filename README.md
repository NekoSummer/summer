# Summer Repo

It's my Maven Repo

## Use this repo?

### **if maven**

pom.xml
```xml
<repositories>
    <repository>
        <id>github</id>
        <url>https://maven.pkg.github.com/NekoSummer/summer</url>
    </repository>
</repositories>
```
and settings.xml
```xml
<servers>
    <server>
        <id>github</id>
        <username>GitHub Username</username>
        <password>GitHub Token</password>
    </server>
</servers>
```

### **else if gradle**

Groovy DSL
```groovy
repositories {
    maven {
        url = 'https://maven.pkg.github.com/NekoSummer/summer'

        credentials {
            username = project.findProperty("gpr.user") ?: System.getenv("GITHUB_ACTOR")
            password = project.findProperty("gpr.token") ?: System.getenv("GITHUB_TOKEN")
        }
    }
}
```

Kotlin DSL
```kotlin
repositories {
    maven { 
        url = uri("https://maven.pkg.github.com/NekoSummer/summer")
        
        credentials {
            username = project.findProperty("gpr.user") as String? ?: System.getenv("GITHUB_ACTOR")
            password = project.findProperty("gpr.token") as String? ?: System.getenv("GITHUB_TOKEN")
        }
    }
}
```