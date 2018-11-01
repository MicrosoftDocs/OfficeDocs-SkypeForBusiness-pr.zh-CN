---
title: 创建或修改新客户端版本策略
TOCTitle: 创建或修改新客户端版本策略
ms:assetid: 4be6e449-aa82-4b46-abb1-d31281573a72
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ898476(v=OCS.15)
ms:contentKeyID: 52061017
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 创建或修改新客户端版本策略

 

_**上一次修改主题：** 2013-02-23_

您可以使用客户端版本策略来指定您的环境中所支持的客户端版本。使用客户端版本控制可以帮助降低与支持多个客户端版本相关的成本。它还可以改善总体用户体验，因为在较低和较高版本的客户端交互时，可用功能受较早版本客户端的限制。您可以从 Lync Server 2013 控制面板或 Lync Server 2013 命令行管理程序创建或修改客户端版本策略。

## 使用 Lync Server 控制面板创建或修改客户端版本策略

1.  使用分配给 CsUserAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。

2.  打开浏览器窗口，然后输入管理 URL 以打开 Lync Server 控制面板。有关可以用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅[打开 Lync Server 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左侧导航栏中，单击“客户端”。
    
    > [!NOTE]  
    > 默认情况下，选中“客户端版本策略”选项卡。
    


4.  在“客户端版本策略”页上，执行下列操作之一：
    
      - 若要创建客户端版本策略，请单击“新建”，选择“站点策略”、“池策略”或“用户策略”，然后单击“确定”。
    
      - 若要修改全局策略或另一个现有客户端版本策略，请选择该策略，单击“编辑”，然后单击“显示详细信息”。

5.  在“编辑客户端版本策略”页上，按照[创建或修改新客户端版本策略规则](lync-server-2013-create-or-modify-a-new-client-version-policy-rule.md)中所述创建或修改规则。

## 使用 Windows PowerShell Cmdlet 创建或修改客户端版本策略

您可以使用 **New-CsClientVersionPolicy** cmdlet 创建客户端版本策略，并使用 **Set-CsClientVersionPolicy** cmdlet 修改它们。这些 cmdlet 可从 Lync Server 2013 命令行管理程序或从 Windows PowerShell 的远程会话中运行。有关使用远程 Windows PowerShell 连接到 Lync Server 的详细信息，请参阅 Lync Server Windows PowerShell 博客文章“快速入门：使用远程 PowerShell 管理 Microsoft Lync Server 2010”，网址为 [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)。

## 创建新的网站范围内的客户端版本策略

  - 以下命令创建应用于 Redmond 网站的新客户端版本策略。因为没有指定其他参数，所以新策略将使用默认的客户端版本设置。
    
        New-CsClientVersionPolicy -Identity "site:Redmond"

## 创建新的每用户客户端版本策略

  - 若要创建每用户策略，请使用类似如下的命令：
    
        New-CsClientVersionPolicy -Identity "RedmondClientVersionPolicy"

有关详细信息，请参阅 [Set-CsClientVersionPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsClientVersionPolicy) cmdlet 和 [New-CsClientVersionPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsClientVersionPolicy) cmdlet 的帮助主题。

