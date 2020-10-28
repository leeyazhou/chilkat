# chilkat

由于官方chilkat未把jar发布到maven仓库，为了方便maven项目引入依赖，所以创建了这个项目，重新打包了chilkat项目的Java源码和不同平台（Linux、Windows和macoxs）对应的二进制库。

## 示例

示例展示了项目根据操作系统类型引入正确的chilkat的方式。

1. pom.xml引入扩展插件：

```
<build>
	<extensions>
		<extension>
			<groupId>kr.motd.maven</groupId>
			<artifactId>os-maven-plugin</artifactId>
			<version>1.6.2</version>
		</extension>
	</extensions>
</build>
```

2. 引用chilkat依赖

```
<dependency>
	<groupId>com.github.leeyazhou.chilkat</groupId>
	<artifactId>chilkat-${os.detected.name}</artifactId>
	<version>9.5.0</version>
</dependency>
```