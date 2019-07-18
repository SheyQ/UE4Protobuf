# UE4Protobuf

在UE4里使用Google Protobuffer ver3.5.1

参考教程：
<a href="https://thecodeway.com/blog/?p=1394" target="_blank">在UnrealEngine4中使用Google Protobuf</a>

我已经编译整理好了关于windows下的需要的lib库和相关头文件。
直接把ThirdParty文件夹复制到虚幻4项目的Source目录下。
在[项目名称].Build.cs里加入  
bEnableShadowVariableWarnings = false;  
bEnableUndefinedIdentifierWarnings = false;  
PrivateDependencyModuleNames.AddRange(new string[] { "protobuf" });  
禁用警告和添加protobuf模块。

使用.uproject重新生成.sln文件,这一步会把protobuf模块加入到项目中。

使用protoc.exe生成的.h文件中加入以下代码。
\#pragma warning(disable:4125)
\#wpragma warning(disable:4577)
\#pragma warning(disable:4800)
\#pragma warning(disable:4668)
\#pragma warning(disable:4647)
\#pragma warning(disable:4146)

由于protobuf和ue4两个独有的check宏冲突，在ue4里不要使用该宏。

之后 在项目文件里直接使用即可。
