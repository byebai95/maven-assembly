#### maven 插件 Assembly 对项目进行打包
```pom
   <plugins>
            <!-- compiler插件参数设置，指定编码 -->
            <plugin>
                <groupId>org.apache.maven.plugins</groupId>
                <artifactId>maven-compiler-plugin</artifactId>
                <version>3.1</version>
                <configuration>
                    <source>1.8</source>
                    <target>1.8</target>
                    <encoding>utf-8</encoding>
                </configuration>
            </plugin>

            <!--   这个插件是关键   -->
            <plugin>
                <groupId>org.apache.maven.plugins</groupId>
                <artifactId>maven-assembly-plugin</artifactId>
                <configuration>
                    <!--   这个是assembly 所在位置  -->
                    <descriptor>src/main/assembly/assembly.xml</descriptor>
                </configuration>
                <executions>
                    <execution>
                        <id>make-assembly</id>
                        <phase>package</phase>
                        <goals>
                            <goal>single</goal>
                        </goals>
                    </execution>
                </executions>
            </plugin>
        </plugins>
    </build>
```
参考博客: [Assembly使用](https://blog.csdn.net/zhongzunfa/article/details/82465939)