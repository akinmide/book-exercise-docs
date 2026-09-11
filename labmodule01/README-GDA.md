## Lab Module 01

### Description

The Gateway Device Application (GDA) provides the Java-based gateway portion of the Programming the Internet of Things system. For this lab, I configured the GDA development environment in WSL2 using Ubuntu 22.04, OpenJDK 17, and Apache Maven 3.6.3. Java 17 was used because the current InfluxDB client dependency contains Java 17 bytecode. The application compiled successfully and demonstrated the expected initialization, startup, and shutdown behavior.

The implementation works through the GatewayDeviceApp class, which controls the application lifecycle. Its startApp() method starts the application, while stopApp(0) performs an orderly shutdown with exit code 0. I validated this behavior using GatewayDeviceAppTest. The test starts the application, allows it to run for approximately 65 seconds, and then stops it. Maven was run without a forked test JVM because the intentional System.exit(0) call can otherwise be reported as an unexpected JVM termination.

### Code Repository and Branch

URL: https://github.com/akinmide/gda-java-components/tree/labmodule01

### UML Design Diagram(s)

GatewayDeviceAppTest creates and exercises GatewayDeviceApp. GatewayDeviceApp provides the startApp() and stopApp() lifecycle operations.

### Unit Tests Executed

- No Lab Module 01-specific unit tests were required.

### Integration Tests Executed

- Test case: GatewayDeviceAppTest
- Test method: testStartAndStopGatewayApp
- Command: mvn -Dtest=GatewayDeviceAppTest -DforkCount=0 test
- Result: The GDA initialized, started successfully, stopped successfully, and returned exit code 0.
