Common
====

```
$ tree .
.
├── README.md
├── common-jar-A
│   └── pom.xml
├── common-pom-A
│   ├── common-A-jar-A
│   │   └── pom.xml
│   ├── common-A-jar-B
│   │   └── pom.xml
│   └── pom.xml
├── common-pom-B
│   └── pom.xml
└── pom.xml
```

```
$  mvn dependency:tree
[INFO] Scanning for projects...
[INFO] ------------------------------------------------------------------------
[INFO] Reactor Build Order:
[INFO] 
[INFO] Common libs and tools                                              [pom]
[INFO] Common JAR A                                                       [jar]
[INFO] Common POM A                                                       [pom]
[INFO] Common A - JAR A                                                   [jar]
[INFO] Common A - JAR B                                                   [jar]
[INFO] Common POM B                                                       [pom]
[INFO] 
[INFO] ------------------< org.sample.common:common-parent >-------------------
[INFO] Building Common libs and tools 1.5.0-SNAPSHOT                      [1/6]
[INFO]   from pom.xml
[INFO] --------------------------------[ pom ]---------------------------------
[INFO] 
[INFO] --- dependency:3.6.0:tree (default-cli) @ common-parent ---
[INFO] org.sample.common:common-parent:pom:1.5.0-SNAPSHOT
[INFO] \- junit:junit:jar:4.8:compile
[INFO] 
[INFO] -------------------< org.sample.common:common-jar-A >-------------------
[INFO] Building Common JAR A 1.5.0-SNAPSHOT                               [2/6]
[INFO]   from common-jar-A/pom.xml
[INFO] --------------------------------[ jar ]---------------------------------
[INFO] 
[INFO] --- dependency:3.6.0:tree (default-cli) @ common-jar-A ---
[INFO] org.sample.common:common-jar-A:jar:1.5.0-SNAPSHOT
[INFO] +- org.apache.commons:commons-lang3:jar:3.7:compile
[INFO] +- com.google.protobuf:protobuf-java-util:jar:3.12.0:compile
[INFO] |  +- com.google.protobuf:protobuf-java:jar:3.12.0:compile
[INFO] |  +- com.google.guava:guava:jar:29.0-android:compile
[INFO] |  |  +- com.google.guava:failureaccess:jar:1.0.1:compile
[INFO] |  |  +- com.google.guava:listenablefuture:jar:9999.0-empty-to-avoid-conflict-with-guava:compile
[INFO] |  |  +- com.google.code.findbugs:jsr305:jar:3.0.2:compile
[INFO] |  |  +- org.checkerframework:checker-compat-qual:jar:2.5.5:compile
[INFO] |  |  \- com.google.j2objc:j2objc-annotations:jar:1.3:compile
[INFO] |  +- com.google.errorprone:error_prone_annotations:jar:2.3.4:compile
[INFO] |  \- com.google.code.gson:gson:jar:2.8.6:compile
[INFO] \- junit:junit:jar:4.8:compile
[INFO] 
[INFO] -------------------< org.sample.common:common-pom-A >-------------------
[INFO] Building Common POM A 1.5.0-SNAPSHOT                               [3/6]
[INFO]   from common-pom-A/pom.xml
[INFO] --------------------------------[ pom ]---------------------------------
[INFO] 
[INFO] --- dependency:3.6.0:tree (default-cli) @ common-pom-A ---
[INFO] org.sample.common:common-pom-A:pom:1.5.0-SNAPSHOT
[INFO] \- junit:junit:jar:4.8:compile
[INFO] 
[INFO] ------------------< org.sample.common:common-A-jar-A >------------------
[INFO] Building Common A - JAR A 1.5.0-SNAPSHOT                           [4/6]
[INFO]   from common-pom-A/common-A-jar-A/pom.xml
[INFO] --------------------------------[ jar ]---------------------------------
[INFO] 
[INFO] --- dependency:3.6.0:tree (default-cli) @ common-A-jar-A ---
[INFO] org.sample.common:common-A-jar-A:jar:1.5.0-SNAPSHOT
[INFO] +- com.fasterxml.jackson.core:jackson-databind:jar:2.10.4:compile
[INFO] |  +- com.fasterxml.jackson.core:jackson-annotations:jar:2.10.4:compile
[INFO] |  \- com.fasterxml.jackson.core:jackson-core:jar:2.10.4:compile
[INFO] +- org.sample.common:common-jar-A:jar:1.5.0-SNAPSHOT:compile
[INFO] |  +- org.apache.commons:commons-lang3:jar:3.7:compile
[INFO] |  \- com.google.protobuf:protobuf-java-util:jar:3.12.0:compile
[INFO] |     +- com.google.protobuf:protobuf-java:jar:3.12.0:compile
[INFO] |     +- com.google.guava:guava:jar:29.0-android:compile
[INFO] |     |  +- com.google.guava:failureaccess:jar:1.0.1:compile
[INFO] |     |  +- com.google.guava:listenablefuture:jar:9999.0-empty-to-avoid-conflict-with-guava:compile
[INFO] |     |  +- com.google.code.findbugs:jsr305:jar:3.0.2:compile
[INFO] |     |  +- org.checkerframework:checker-compat-qual:jar:2.5.5:compile
[INFO] |     |  \- com.google.j2objc:j2objc-annotations:jar:1.3:compile
[INFO] |     +- com.google.errorprone:error_prone_annotations:jar:2.3.4:compile
[INFO] |     \- com.google.code.gson:gson:jar:2.8.6:compile
[INFO] \- junit:junit:jar:4.8:compile
[INFO] 
[INFO] ------------------< org.sample.common:common-A-jar-B >------------------
[INFO] Building Common A - JAR B 1.5.0-SNAPSHOT                           [5/6]
[INFO]   from common-pom-A/common-A-jar-B/pom.xml
[INFO] --------------------------------[ jar ]---------------------------------
[INFO] 
[INFO] --- dependency:3.6.0:tree (default-cli) @ common-A-jar-B ---
[INFO] org.sample.common:common-A-jar-B:jar:1.5.0-SNAPSHOT
[INFO] +- commons-collections:commons-collections:jar:3.2.1:compile
[INFO] +- org.apache.httpcomponents:httpcore:jar:4.4.3:compile
[INFO] +- org.sample.common:common-A-jar-A:jar:1.5.0-SNAPSHOT:compile
[INFO] |  +- com.fasterxml.jackson.core:jackson-databind:jar:2.10.4:compile
[INFO] |  |  +- com.fasterxml.jackson.core:jackson-annotations:jar:2.10.4:compile
[INFO] |  |  \- com.fasterxml.jackson.core:jackson-core:jar:2.10.4:compile
[INFO] |  \- org.sample.common:common-jar-A:jar:1.5.0-SNAPSHOT:compile
[INFO] |     +- org.apache.commons:commons-lang3:jar:3.7:compile
[INFO] |     \- com.google.protobuf:protobuf-java-util:jar:3.12.0:compile
[INFO] |        +- com.google.protobuf:protobuf-java:jar:3.12.0:compile
[INFO] |        +- com.google.guava:guava:jar:29.0-android:compile
[INFO] |        |  +- com.google.guava:failureaccess:jar:1.0.1:compile
[INFO] |        |  +- com.google.guava:listenablefuture:jar:9999.0-empty-to-avoid-conflict-with-guava:compile
[INFO] |        |  +- com.google.code.findbugs:jsr305:jar:3.0.2:compile
[INFO] |        |  +- org.checkerframework:checker-compat-qual:jar:2.5.5:compile
[INFO] |        |  \- com.google.j2objc:j2objc-annotations:jar:1.3:compile
[INFO] |        +- com.google.errorprone:error_prone_annotations:jar:2.3.4:compile
[INFO] |        \- com.google.code.gson:gson:jar:2.8.6:compile
[INFO] \- junit:junit:jar:4.8:compile
[INFO] 
[INFO] -------------------< org.sample.common:common-pom-B >-------------------
[INFO] Building Common POM B 1.5.0-SNAPSHOT                               [6/6]
[INFO]   from common-pom-B/pom.xml
[INFO] --------------------------------[ pom ]---------------------------------
[INFO] 
[INFO] --- dependency:3.6.0:tree (default-cli) @ common-pom-B ---
[INFO] org.sample.common:common-pom-B:pom:1.5.0-SNAPSHOT
[INFO] \- junit:junit:jar:4.8:compile
[INFO] ------------------------------------------------------------------------
[INFO] Reactor Summary for Common libs and tools 1.5.0-SNAPSHOT:
[INFO] 
[INFO] Common libs and tools .............................. SUCCESS [  1.432 s]
[INFO] Common JAR A ....................................... SUCCESS [  0.102 s]
[INFO] Common POM A ....................................... SUCCESS [  0.004 s]
[INFO] Common A - JAR A ................................... SUCCESS [  0.041 s]
[INFO] Common A - JAR B ................................... SUCCESS [  0.025 s]
[INFO] Common POM B ....................................... SUCCESS [  0.005 s]
[INFO] ------------------------------------------------------------------------
[INFO] BUILD SUCCESS
[INFO] ------------------------------------------------------------------------
```