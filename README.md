# JooqGeneratorDependencies

            <!-- JOOQ Generator Plugin -->
            <plugin>
                <groupId>org.jooq</groupId>
                <artifactId>jooq-codegen-maven</artifactId>
                <version>${jooq.version}</version>
                <executions>
                    <execution>
                        <phase>generate-sources</phase>
                        <goals>
                            <goal>generate</goal>
                        </goals>
                    </execution>
                </executions>
                <configuration>
                    <jdbc>
                        <driver>org.postgresql.Driver</driver>
                        <url>jdbc:postgresql://localhost:5432/db</url>
                        <user>root</user>
                        <password>root</password>
                    </jdbc>
                    <generator>
                        <database>
                            <includes>.*</includes>  <!-- включаемые подпакеты и файлы -->
                            <excludes>  <!-- исключаемые подпакеты и файлы -->
                                flyway_schema_history
                            </excludes>
                            <inputSchema>public</inputSchema>  <!-- схема -->
                        </database>
                        <generate>
                            <records>true</records>
                            <daos>true</daos>
                            <comments>false</comments>
                            <pojos>true</pojos>
                            <sequences>false</sequences>
                        </generate>
                        <target>
                            <packageName>jooq-generated</packageName>
                            <directory>src/main/java/ru/psychotech/model</directory>
                        </target>
                    </generator>
                </configuration>
            </plugin>
