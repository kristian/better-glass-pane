BetterGlassPane
===============

This project provides a better glass pane implementation, to replace the default glass pane of a `JRootPane` object. In contrast to the default glass pane (`JPanel`) of a `JRootPane`, this `BetterGlassPane` handles any mouse events, without interrupting the controls underneath the glass pane (in the content pane of the root pane). Also cursors are handled as if the glass pane was invisible (if no cursor gets explicit set to the glass pane).

Usage
-----

Feel free to use the class `lc.kra.swing.BetterGlassPane` by copying the `BetterGlassPane.java` file to your project. Instantiate a `BetterGlassPane` by using the `BetterGlassPane()` constructor. In addition you have to set the root pane to the glass pane and the glass pane to the root pane:

```java
JRootPane anyRootPane = ...;
BetterGlassPane betterGlassPane = new BetterGlassPane();
betterGlassPane.setRootPane(anyRootPane);
anyRootPane.setGlassPane(betterGlassPane);
```

Alternatively you can call the specific `BetterGlassPane(JRootPane)` constructor, so you don't have to set the root pane / glass pane (the glass pane will be set to visible by default): 

```java
JRootPane anyRootPane = ...;
BetterGlassPane betterGlassPane = new BetterGlassPane(anyRootPane);
```

Afterwards add any number of mouse listeners (`addMouseListener`), mouse motion listeners (`addMouseMotionListener`) or mouse wheel listeners (`addMouseWheelListener`) to the glass pane.

### Maven Dependency
You can include better-glass-pane from this GitHub repository by adding this dependency to your `pom.xml`:

```xml
<dependency>
  <groupId>lc.kra.swing</groupId>
  <artifactId>better-glass-pane</artifactId>
  <version>0.1.3</version>
</dependency>
```

Additionally you will have to add the following repository to your `pom.xml`:

```xml
<repositories>
  <repository>
    <id>better-glass-pane-mvn-repo</id>
    <url>https://raw.github.com/kristian/better-glass-pane/mvn-repo/</url>
    <snapshots>
      <enabled>true</enabled>
      <updatePolicy>always</updatePolicy>
    </snapshots>
  </repository>
</repositories>
```

Build
-----

To build better-glass-pane on your machine, checkout the repository, `cd` into it, and call:
```
mvn clean install
```

License
-------

The code is available under the terms of the [MIT License](http://opensource.org/licenses/MIT).