---
title: 迁移呼叫寄存应用程序设置
TOCTitle: 迁移呼叫寄存应用程序设置
ms:assetid: 23b192d2-93ec-42a8-b175-b6ed502a2c35
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ687993(v=OCS.15)
ms:contentKeyID: 49888342
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 迁移呼叫寄存应用程序设置

 

_**上一次修改主题：** 2012-10-19_

将呼叫寄存应用程序从 Lync Server 2010 迁移至 Lync Server 2013 涉及使用 Lync Server 2010 中已上载的任何自定义保持音乐文件设置 Lync Server 2013 池，还原服务级别设置以及将所有呼叫寄存轨道重定向到 Lync Server 2013 池。如果已在 Lync Server 2010 池中配置了自定义保持音乐文件，则需要将这些文件复制到新的 Lync Server 2013 池。另外，建议您将所有呼叫寄存自定义保持音乐文件从 Lync Server 2010 备份到其他目标位置，以保留已为呼叫寄存上载的任何自定义保持音乐文件的单独备份副本。呼叫寄存应用程序的自定义保持音乐文件存储在池的文件存储中。若要将音频文件从 Lync Server 2010 池文件存储复制到 Lync Server 2013 文件存储，请使用带以下参数的 **Xcopy** 命令：

    Xcopy <Source: Lync Server 2010 Pool CPS File Store Path> <Destination: Lync Server 2013 Pool CPS File Store Path>

   &nbsp;

    Example usage:  Xcopy "<Lync Server 2010 File Store Path>\OcsFileStore\coX-ApplicationServer-X\AppServerFiles\CPS\"  "<Lync Server 2013 File Store Path>\OcsFileStore\coX-ApplicationServer-X\AppServerFiles\CPS\" 

将所有自定义音频文件复制到 Lync Server 2013 文件存储后，必须配置 Lync Server 2013 池的呼叫寄存应用程序设置，且必须将与 Lync Server 2010 池关联的呼叫寄存轨道范围重新分配给 Lync Server 2013 池。

呼叫寄存应用程序设置包括应答超时阈值，启用或禁用保持音乐，最大呼叫应答尝试次数和超时请求。您必须通过使用 Lync Server 命令行管理程序运行 **Set-CsCpsConfiguration** cmdlet 来管理呼叫寄存应用程序设置。您无法使用 Lync Server 控制面板管理呼叫寄存应用程序设置。

**重新配置呼叫寄存服务设置**

1.  从 Lync Server 2013 前端服务器，打开 Lync Server 命令行管理程序。

2.  在命令行中键入：
    
    > [!NOTE]
    > 如果您的 Lync Server 2013 呼叫寄存应用程序设置与旧 Lync Server 2010 设置相同，则可以跳过运行此步骤。如果 Lync Server 2013 和 Lync Server 2010 环境的呼叫寄存应用程序设置不同，请使用下面的 cmdlet 作为模板来更新这些更改。
    
        Set-CsCpsConfiguration -Identity "<LS2013 Call Park Service ID>" -CallPickupTimeoutThreshold "<LS2010 CPS TimeSpan>" -EnableMusicOnHold "<LS2010 CPS value>" -MaxCallPickupAttempts "<LS2010 CPS pickup attempts>" -OnTimeoutURI "<LS2010 CPS timeout URI>"

要将所有呼叫寄存轨道范围从 Lync Server 2010 池重新分配给 Lync Server 2013 池，可以使用 Lync Server 控制面板或 Lync Server 命令行管理程序。

**使用 Lync Server 控制面板重新分配所有呼叫寄存轨道范围**

1.  打开 Lync Server 控制面板。

2.  在左窗格中，选择“语音功能”。

3.  选择“呼叫寄存”选项卡。

4.  对于分配给 Lync Server 2010 池的每个呼叫寄存轨道范围，请编辑“目标服务器的 FQDN”设置并选择将处理呼叫寄存请求的 Lync Server 2013 池。

5.  单击“提交”保存所做更改。

**使用 Lync Server 命令行管理程序重新分配所有呼叫寄存轨道范围**

1.  打开 Lync Server 命令行管理程序。

2.  在命令行中键入：
    
        Get-CsCallParkOrbit
    
    此 cmdlet 列出了部署中的所有呼叫寄存轨道范围。必须重新分配其 **CallParkServiceId** 和 **CallParkServerFqdn** 参数设置为 Lync Server 2010 池的所有呼叫寄存轨道。
    
    若要将 Lync Server 2010 呼叫寄存轨道范围重新分配给 Lync Server 2013 池，请在命令行中键入以下命令：
    
        Set-CsCallParkOrbit -Identity "<Call Park Orbit Identity>" -CallParkService "service:ApplicationServer:<Lync Server 2013 Pool FQDN>"

将所有呼叫寄存轨道范围重新分配给 Lync Server 2013 池后，将完成呼叫寄存应用程序的迁移过程并且 Lync Server 2013 池将处理所有未来的呼叫寄存请求。

