<!---
Licensed to the Apache Software Foundation (ASF) under one or more
contributor license agreements.  See the NOTICE file distributed with
this work for additional information regarding copyright ownership.
The ASF licenses this file to You under the Apache License, Version 2.0
(the "License"); you may not use this file except in compliance with
the License.  You may obtain a copy of the License at

http://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing, software
distributed under the License is distributed on an "AS IS" BASIS,
WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
See the License for the specific language governing permissions and
limitations under the License.
-->

# Maven Site

[![Apache License, Version 2.0, January 2004](https://img.shields.io/github/license/apache/maven.svg?label=License)][license]
[![Jenkins Status](https://img.shields.io/jenkins/s/https/ci-maven.apache.org/job/Maven/job/maven-box/job/maven-site/job/master.svg)][build]

This is the Git repository for the content of <https://maven.apache.org/>.

## 本地运行

You can run

```
$ mvn site:run
```

to run locally and see the website on <http://localhost:8080/>.

执行 `mvn site:run` 命令后，Maven 会启动一个内置的 Jetty 服务器，并运行项目的站点（Site）。以下是具体的行为和步骤：
1. **加载站点配置**  
   Maven 会根据项目的 `pom.xml` 和 `src/site` 目录中的内容生成或加载站点文档。如果项目中定义了报告插件（如 Surefire、Checkstyle 等），这些插件的报告也会被包含在站点中。
2. **启动 Jetty 服务器**  
   Maven 使用内置的 Jetty 服务器来托管生成的站点。
3. **实时更新**  
   在 `site:run` 模式下，Maven 会监视项目文件的变化。如果检测到文件被修改，它会自动重新生成受影响的部分并刷新站点内容。
4. **终止命令**  
   要停止 Jetty 服务器和站点运行，可以在终端按下 `Ctrl+C`。

### 注意事项
- 确保项目已经正确配置了 Maven Site 插件（`maven-site-plugin`）。
- 如果需要生成完整的站点文件（而不是实时运行），可以使用 `mvn site` 命令。
- 如果站点依赖于某些报告插件，确保这些插件已在 `pom.xml` 中正确配置。

Additional Resources
--------------------

+ [Contributing patches](https://maven.apache.org/guides/development/guide-maven-development.html#Creating_and_submitting_a_patch)
+ [Contributor License Agreement][cla]
+ [General GitHub documentation](https://docs.github.com)
+ [GitHub pull request documentation](https://docs.github.com/pull-requests)
+ [Apache Maven Twitter Account](https://twitter.com/ASFMavenProject)
+ [Slack channel in ASF Workspace](https://infra.apache.org/slack.html)

[license]: https://www.apache.org/licenses/LICENSE-2.0
[ml-list]: https://maven.apache.org/mailing-lists.html
[cla]: https://www.apache.org/licenses/#clas
[build]: https://ci-maven.apache.org/job/Maven/job/maven-box/job/maven-site/job/master/

