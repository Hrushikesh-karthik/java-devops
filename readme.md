Java_app/
│
├── pom.xml
├── Dockerfile
│
└── src/
    └── main/
        └── java/
            └── com/
                └── example/
                    └── demo/
                        ├── DemoApplication.java
                        └── HomeController.java



pom.xml
   ↓
Maven builds Java application
   ↓
JAR
   ↓
Dockerfile
   ↓
Docker builds container image
   ↓
Kubernetes YAML
   ↓
Kubernetes runs containers

hostname I