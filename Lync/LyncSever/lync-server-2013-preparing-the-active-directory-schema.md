---
title: Lync Server 2013：准备 Active Directory 架构
TOCTitle: 准备 Active Directory 架构
ms:assetid: 067726ae-fd3f-4133-a32f-26d2603ac674
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg398119(v=OCS.15)
ms:contentKeyID: 49311886
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 在 Lync Server 2013 中准备 Active Directory 架构

 

_**上一次修改主题：** 2016-12-08_

开始准备 Active Directory 域服务 之前，可以使用文本编辑器（例如，Windows 记事本）打开架构文件，或者参阅 [Lync Server 2013 使用的 Active Directory 架构扩展、类和属性](lync-server-2013-active-directory-schema-extensions-classes-and-attributes-used-by-lync-server.md)以查看将为 Lync Server 2013 修改的所有 Active Directory 域服务 架构扩展。 Lync Server 使用以下四个架构文件：

  - ExternalSchema.ldf，用于实现与 Microsoft Exchange Server 的互操作性

  - ServerSchema.ldf， Lync Server 2013 主架构文件

  - BackCompatSchema.ldf，用于实现与以前版本中任何组件的互操作性

  - VersionSchema.ldf，用于所准备架构的版本信息

所有 .ldf 文件都是在架构准备期间安装的，无论是从以前的版本中进行迁移还是执行全新安装。这些架构文件按以上列表中所示的顺序安装，位于安装介质上的 \\Support\\schema 文件夹中。

Lync Server 架构扩展会在所有域中进行复制，因此会影响网络流量。请在网络利用率较低时运行架构准备。

> [!NOTE]  
> 如果需要将 Microsoft? Office Communicator Mobile 2007 R2 for Java 和 Microsoft? Office Communicator Mobile for Nokia 1.0 移动客户端的支持添加到 Lync Server 2013 部署中，您需要在 Lync Server 2013 安装期间为 Microsoft Office Communications Server 2007 R2 准备 Active Directory 架构。有关必要的软件和文档，请参阅 <a href="http://go.microsoft.com/fwlink/?linkid=207172%26clcid=0x804" class="uri">http://go.microsoft.com/fwlink/?linkid=207172&amp;clcid=0x804</a>。



## ADSI Edit

Active Directory 服务界面编辑器 (ADSI Edit) 是一个 AD DS 管理工具，可以用来验证架构准备和复制。

安装 AD DS 角色以使服务器成为域控制器时，会默认安装 ADSI Edit。对于 Windows Server 2008 和 Windows Server 2008 R2，ADSI Edit (adsiedit.msc) 随附在远程服务器管理工具 (RSAT) 中。还可以在域成员服务器或独立服务器上安装 RSAT。默认情况下，RSAT 包会在安装 Windows 时复制到这些服务器，但默认情况下不安装该包。请使用服务器管理器安装各个工具。ADSI Edit 包括在“角色管理工具”、“Active Directory 域服务工具”、“Active Directory 域控制器工具”下。

对于 Windows Server 2003，ADSI Edit 随附在支持工具中。支持工具位于 Windows Server 2003 CD 的 \\SUPPORT\\TOOLS 文件夹中，也可以从“Windows Server 2003 Service Pack 2 32 位支持工具”下载，网址为 [http://go.microsoft.com/fwlink/p/?linkId=125770](http://go.microsoft.com/fwlink/p/?linkid=125770)。有关从产品 CD 安装支持工具的说明位于“安装 Windows 支持工具”中，网址为 [http://go.microsoft.com/fwlink/p/?linkId=125771](http://go.microsoft.com/fwlink/p/?linkid=125771)。安装支持工具时，Adsiedit.dll 会自动注册。但是，如果已经将文件复制到您的计算机，则您必须在您可运行工具之前运行 **regsvr32** 命令注册 adsiedit.dll 文件。

## 本节内容

  - [在 Lync Server 2013 中运行 Active Directory 架构准备](lync-server-2013-running-schema-preparation.md)

  - [在 Lync Server 2013 中验证 Active Directory 架构复制](lync-server-2013-verifying-schema-replication.md)

## 另请参阅

#### 其他资源

[为 Lync Server 2013 准备林](lync-server-2013-preparing-the-forest.md)  
[为 Lync Server 2013 准备域](lync-server-2013-preparing-domains.md)

