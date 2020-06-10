# NetBeans Bug 1

This project demonstrates that the `--enable-preview` supplied to the
`maven-java-compiler` via its `<compilerArgs>` configuration does not
actually make it all the way into the editor in NetBeans 12 (with
`nb-javac` deliberately not installed).

I am not sure what the root cause is.

## Steps to Reproduce Things As I Have Them

* Install JDK 15 early access.  (Note that JEP 375 is still in preview
  and is the subject of this bug.)
* Download and install the NetBeans 12.0 `.dmg` installer.
* Verify that the Java that NetBeans will use is the 15 you just installed.
* Launch NetBeans via double-clicking, i.e. no command line switches or anything fancy.
* Uninstall `nb-javac` following the [instructions](http://netbeans.apache.org/download/nb120/index.html).
* Restart the IDE as necessary.
* Open this project.
* Observe that the `pom.xml` has followed the instructions to enable preview features.
* Observe that the `pom.xml` has defined the compiler `release` property as 14.
* Note that the NetBeans editor flags the `instanceof` test in `Greeter.java` as invalid.
* Note that when you do Clean and Build (`mvn clean install`) everything builds fine.


