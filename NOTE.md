-> Failed ở Build with Maven
file workflows không đúng, không checkout -> runner không xác định được file POM
[INFO] Scanning for projects...
[INFO] ------------------------------------------------------------------------
[INFO] BUILD FAILURE
[INFO] ------------------------------------------------------------------------
[INFO] Total time:  0.087 s
[INFO] Finished at: 2026-05-08T09:47:57Z
[INFO] ------------------------------------------------------------------------
Error:  The goal you specified requires a project to execute but there is no POM in this directory (/home/runner/work/TEST11/TEST11). Please verify you invoked Maven from the correct directory. -> [Help 1]
Error:  
Error:  To see the full stack trace of the errors, re-run Maven with the -e switch.
Error:  Re-run Maven using the -X switch to enable full debug logging.
Error:  
Error:  For more information about the errors and possible solutions, please read the following articles:
Error:  [Help 1] http://cwiki.apache.org/confluence/display/MAVEN/MissingProjectException
Error: Process completed with exit code 1.



(Ver 9.9.9 của logback-classic không có trên Maven Central)
Error:  Failed to execute goal on project ExerciseTen: Could not resolve dependencies for project com.lab:ExerciseTen:jar:1.0-SNAPSHOT
Error:  dependency: org.junit.jupiter:junit-jupiter:jar:9.9.9 (test)
Error:  	Could not find artifact org.junit.jupiter:junit-jupiter:jar:9.9.9 in central (https://repo.maven.apache.org/maven2)


Maven Surefire Plugin cũ không hỗ trợ JUnit 5   -> nâng ver 3.1.2
0 Tests -> không nhận diện các TestCase





Lỗi tự thêm chỉnh
void testInvalidWeight() {
assertThrows(IllegalArgumentException.class,
() -> calc.calculate(-1, "STANDARD"));
}
->
void testInvalidWeight() {
assertThrows(IllegalArgumentException.class,
() -> calc.calculate(5, "STANDARD"));
}
Error:  Failed to execute goal org.apache.maven.plugins:maven-compiler-plugin:3.15.0:testCompile (default-testCompile) on project shipping-app: Compilation failure
Error:  /home/runner/work/TEST11/TEST11/src/test/java/com/lab/ShippingCalculatorTest.java:[31,8] method testInvalidWeight() is already defined in class com.lab.ShippingCalculatorTest
Error:  
Error:  -> [Help 1]
Error:  
Error:  To see the full stack trace of the errors, re-run Maven with the -e switch.
Error:  Re-run Maven using the -X switch to enable full debug logging.
Error:  
Error:  For more information about the errors and possible solutions, please read the following articles:
Error:  [Help 1] http://cwiki.apache.org/confluence/display/MAVEN/MojoFailureException
Error: Process completed with exit code 1.

Error:  Failed to execute goal org.apache.maven.plugins:maven-surefire-plugin:3.1.2:test (default-test) on project shipping-app: There are test failures.
Error:  
Error:  Please refer to /home/runner/work/TEST11/TEST11/target/surefire-reports for the individual test results.
Error:  Please refer to dump files (if any exist) [date].dump, [date]-jvmRun[N].dump and [date].dumpstream.
Error:  -> [Help 1]
Error:  
Error:  To see the full stack trace of the errors, re-run Maven with the -e switch.
Error:  Re-run Maven using the -X switch to enable full debug logging.
Error:  
Error:  For more information about the errors and possible solutions, please read the following articles:
Error:  [Help 1] http://cwiki.apache.org/confluence/display/MAVEN/MojoFailureException
Error: Process completed with exit code 1.