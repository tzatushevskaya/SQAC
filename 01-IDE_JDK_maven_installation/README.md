## Installation of Git, IDE, JDK & Maven ##

- [Windows](#windows)
- [Mac](#mac)
- [Linux](#linux)

---

### <a id=windows></a> Installation on Windows ###

1. Download & install [git](https://www.jetbrains.com/idea/download/download-thanks.html?platform=windows&code=IIC).
1. Download & install [IntelliJ IDEA Community Edition](https://www.jetbrains.com/idea/download/download-thanks.html?platform=windows&code=IIC).
2. Download [OpenJDK 16](https://download.java.net/openjdk/jdk16/ri/openjdk-16+36_windows-x64_bin.zip) or select a newer version [here](https://jdk.java.net/).
3. Extract the archive into the dedicated folder.
4. Set system environment variables:
    - Start > Edit the system environment variables > \[Environment Variables...] >
        - System variables > \[New] >
          ```
          Variable name: JAVA_HOME
          Variable value: <absolute path to the openjdk directory>
          ```
        - System variables > select _Path_ variable > \[Edit] > \[New] > enter `%JAVA_HOME%\bin`.
    - Click \[OK] > \[OK] > \[OK]
5. Open the terminal and execute `java -version` to check if jdk is available.
6. Download [Apache Maven 3.9.0](https://dlcdn.apache.org/maven/maven-3/3.9.0/binaries/apache-maven-3.9.0-bin.zip) or select a newer version [here](https://maven.apache.org/download.cgi).
7. Extract the archive into the dedicated folder.
8. Set system environment variables:
    - Start > Edit the system environment variables > \[Environment Variables...] >
        - System variables > \[New] >
          ```
          Variable name: MAVEN_HOME
          Variable value: <absolute path to the apache-maven directory>
          ```
        - System variables > select Path variable > \[Edit] > \[New] > enter
          ```
          %MAVEN_HOME%\bin
          ```
    - Click \[OK] > \[OK] > \[OK]
8. Open the terminal and execute `mvn -version` to check if maven is available.

### <a id=mac></a> Installation on Mac ###

1. Install [IntelliJ IDEA Community Edition](https://www.jetbrains.com/idea/download/download-thanks.html?platform=mac&code=IIC).
2. Install [OpenJDK 19 for macOS/AArch64](https://download.java.net/java/GA/jdk19.0.2/fdb695a9d9064ad6b064dc6df578380c/7/GPL/openjdk-19.0.2_macos-aarch64_bin.tar.gz) or [OpenJDK 19 for macOS/x64](https://download.java.net/java/GA/jdk19.0.2/fdb695a9d9064ad6b064dc6df578380c/7/GPL/openjdk-19.0.2_macos-x64_bin.tar.gz) or select a newer version [here](https://jdk.java.net/).
3. Extract the archive into the dedicated folder.
4. Open terminal and run the command in order to trust the folder you have downloaded:

```
xattr -d com.apple.quarantine <absolute path to the openjdk directory>
```

5. Run the command to create bash resource file:

```
cat <<EOF > .bash_profile
export JAVA_HOME=$HOME/OpenJDK/<jdk-version.jdk>/Contents/Home
export PATH=$JAVA_HOME/bin:$PATH
EOF
```

Run the command to apply source:

```
source .bash_profile
```

Execute `java -version` to check if jdk is available.

8. Download [Apache Maven 3.9.0](https://dlcdn.apache.org/maven/maven-3/3.9.0/binaries/apache-maven-3.9.0-bin.zip) or select a newer version [here](https://maven.apache.org/download.cgi)
9. Open terminal and run the command in order to add a new system variable:

```
nano .bash_profile
```

Add following lines, then press [Ctrl]+[O], [Enter], [Ctrl]+[X].

```
export M2_HOME=/Applications/apache-maven-3.6.3
export PATH=$PATH:$M2_HOME/bin
```

Run the command to apply source:

```
source .bash_profile
```

Execute `mvn -version` to check if maven is available.

### <a id=linux></a> Installation on Linux ###

1. Download & install [IntelliJ IDEA Community Edition](https://www.jetbrains.com/idea/download/download-thanks.html?platform=linux&code=IIC).
2. Download [OpenJDK 16](https://download.java.net/openjdk/jdk16/ri/openjdk-16+36_linux-x64_bin.tar.gz) or select a newer version [here](https://jdk.java.net/).

```
$ tar -xvf <archive name>
$ mv jdk-13.0.1 $HOME/opt/
```

Run the command in order to add a new system variable:

```
nano ./profile
```

Add following lines, then press [Ctrl]+[S], [Enter], [Ctrl]+[X].

```
JAVA_HOME='$HOME/opt/jdk-13.0.1'
PATH="$JAVA_HOME/bin:$PATH"
export PATH
```

Execute `java -version` to check if jdk is available.

3. Download [Apache Maven 3.9.0](https://dlcdn.apache.org/maven/maven-3/3.9.0/binaries/apache-maven-3.9.0-bin.zip) or select a newer version [here](https://maven.apache.org/download.cgi)

```
tar -xvf apache-maven-3.6.3-bin.tar.gz
mv apache-maven-3.6.3 $HOME/opt/
```

Run the command in order to add a new system variable:

```
nano ./profile
```

Add following lines, then press [Ctrl]+[S], [Enter], [Ctrl]+[X].

```
M2_HOME='$HOME/opt/apache-maven-3.6.3'
PATH="$M2_HOME/bin:$PATH"
export PATH
```

Relaunch the terminal or execute `source .profile` to apply the changes. 
Execute `mvn -version` to check if mvn is
available.