# 超级 POM

- 定义各个maven仓库
- 定义常用依赖的版本号
- 统一所使用的三方依赖版本，避免版本使用混乱

可自行查看该pom中已定义的三方依赖版本，有缺就补。

## 注意⚠️

若父pom更新了，本地没来得及更新，可使用 `-U`参数 ，如 `mvn package -U`


## 使用示例

使用 Spring.io 生成的SpringBoot项目，默认的`parent`会类似这样

```xml
    <parent>
        <groupId>org.springframework.boot</groupId>
        <artifactId>spring-boot-starter-parent</artifactId>
        <version>2.3.0.RELEASE</version>
        <relativePath/> <!-- lookup parent from repository -->
    </parent>
```

把它改为以下的即可

```xml
<parent>
    <groupId>io.github.taills</groupId>
    <artifactId>spring-boot-parent</artifactId>
    <version>1.0.0</version>
    <relativePath/> <!-- lookup parent from repository -->
</parent>
```

## 版本升级
```bash
mvn versions:set -DnewVersion=1.0.2-SNAPSHOT
mvn versions:commit
# 以下命令会根据版本号自动选择仓库
mvn deploy
```

