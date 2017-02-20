## How to use Apache Ant and Ant-Contrib on macOS?

If you don't know what is Ant and Ant-Contrib, please refer to the reference.

### 1. Installation on macOS

```
brew install ant
brew install ant-contrib
```

### 2. Verify Ant Installation

edit build.xml:

```
<?xml version="1.0"?>

<project name="hello" basedir=".">

  <target name="hello-ant">
    <echo>Hello, world!</echo>
  </target>

</project>
```

run command below:
```
ant hello-ant
```

### 3. Verify Ant-Contrib Installation

update build.xml:
```
<?xml version="1.0"?>

<project name="hello" basedir=".">

  <taskdef resource="net/sf/antcontrib/antlib.xml">
    <classpath>
      <pathelement location="/usr/local/Cellar/ant-contrib/1.0b3/share/ant/ant-contrib-1.0b3.jar"/>
    </classpath>
  </taskdef>

  <target name="hello-ant">
    <echo>Hello, world!</echo>
  </target>

  <target name="hello-ant-contrib">
    <property name="test.value" value="A"/>

    <if>
      <equals arg1="${test.value}" arg2="A" />
    <then>
      <echo message="Test value you have specified is A." />
    </then>
    <else>
      <echo message="Test value you have specified is not A." />
    </else>
    </if>
  </target>

</project>
```

run command below:
```
ant hello-ant-contrib
```

### Note
To integrate Ant with Ant-Contrib, you have two choices:

1. Copy ant-contrib-version.jar to the lib directory of your Ant installation, or on your CLASSPATH environment variable. If you want to use one of the tasks in your project, add the line
```<taskdef resource="net/sf/antcontrib/antlib.xml"/>```
to your build file.

2. Keep ant-contrib-version.jar in a separate location. You now have to tell Ant explicitly where to find it (say in /usr/share/java/lib):
```
<taskdef resource="net/sf/antcontrib/antlib.xml">
  <classpath>
    <pathelement location="/usr/share/java/lib/ant-contrib-version.jar"/>
  </classpath>
</taskdef>
```

### Reference
1. [Apache Ant](http://ant.apache.org/)
1. [Apache Ant Manual](http://ant.apache.org/manual/index.html)
1. [Ant-Contrib Tasks](http://ant-contrib.sourceforge.net/)
