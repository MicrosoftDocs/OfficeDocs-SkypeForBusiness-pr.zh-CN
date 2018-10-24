---
title: 启用或禁用公用办公桌
TOCTitle: 启用或禁用公用办公桌
ms:assetid: 93a7fed6-f61a-4b41-9336-a8320afa87cf
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ994057(v=OCS.15)
ms:contentKeyID: 52061073
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 启用或禁用公用办公桌

 

_**上一次修改主题：** 2013-02-20_

可以将公共区域电话设置为*公用办公桌电话*。通过公用办公桌电话，用户可以登录自己的用户帐户，并在登录后，使用 Lync Server 功能和自己的用户配置文件设置。通过客户端策略来管理公用办公桌：要启用或禁用公用办公桌，需要修改公共区域电话所使用的客户端策略。有关如何确定已分配给您的公共区域电话的会议策略的详细信息，请参阅[查看公共区域电话信息](lync-server-2013-view-common-area-phone-information.md)。

可以按如下所示使用 **New-CSClientPolicy** cmdlet 或 **Set-CSClientPolicy** cmdlet 的 EnableHotdesking 参数在电话上启用或禁用公用办公桌。从 Lync Server 2013 命令行管理程序或 Windows PowerShell 的远程会话运行这些 cmdlet。有关使用远程 Windows PowerShell 连接到 Lync Server 的详细信息，请参阅 Lync Server Windows PowerShell 博客文章“快速入门：使用远程 PowerShell 管理 Microsoft Lync Server 2010”，网址为 [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)。


## 启用公用办公桌

  - 要为公共区域电话启用公用办公桌，必须修改已分配给该电话（或手机集合）的客户端策略。
    
    在确定了需要修改的策略后，下一步是使用 **Set-CsClientPolicy** cmdlet 将 EnableHotdesking 参数设置为 True。例如：
    
        Set-CsClientPolicy -Identity "CommonAreaPhonePolicy" - EnableHotdesking $True

  - 或者，也可以使用 **New-CsClientPolicy** cmdlet 创建启用公用办公桌的新的客户端策略。例如：
    
        New-CsClientPolicy -Identity "NewCommonAreaPhonePolicy" - EnableHotdesking $True

> [!IMPORTANT]
> 创建此策略后，必须将它分配给适当的公共区域电话。有关详细信息，请参阅<a href="lync-server-2013-assign-policies-to-a-common-area-phone.md">向公共区域电话分配策略</a>。


## 禁用公用办公桌

  - 若要对某个公共区域电话禁用公用办公桌，请将 **Set-CsClientPolicy** cmdlet 的 EnableHotdesking 参数重置为默认值 False。例如：
    
        Set-CsClientPolicy -Identity "CommonAreaPhonePolicy" - EnableHotdesking $False

有关详细信息，请参阅 [New-CsClientPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsClientPolicy) cmdlet 和 [Set-CsClientPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsClientPolicy) cmdlet 的帮助主题。

