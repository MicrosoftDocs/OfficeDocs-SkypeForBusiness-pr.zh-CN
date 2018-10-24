---
title: 删除未与设备关联的设备更新文件
TOCTitle: 删除未与设备关联的设备更新文件
ms:assetid: ecebbf73-b456-4990-a91d-308b84d39404
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ994084(v=OCS.15)
ms:contentKeyID: 52061150
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 删除未与设备关联的设备更新文件

 

_**上一次修改主题：** 2013-02-20_

每次将新设备更新上载到系统后，都会创建一个相应的设备更新规则。默认情况下，将这些新设备更新规则归为“待处理”状态。这意味着可在测试设备上下载和安装这些规则，但不能在生产设备上这样做，这使您能够先测试更新，然后再将其提供给用户。基于测试，您可接受并部署或者拒绝并删除更新。当您拒绝更新时，设备更新将与其设备更新规则解除关联。


可使用 Windows PowerShell 和 **Clear-CsDeviceUpdateFile** cmdlet 删除不再与设备关联的设备更新文件。可从 Lync Server 2013 命令行管理程序或从 Windows PowerShell 的远程会话中运行此 cmdlet。

> [!NOTE]  
> 有关使用远程 Windows PowerShell 连接到 Lync Server 的详细信息，请参阅 Lync Server Windows PowerShell 博客文章“快速入门：使用远程 PowerShell 管理 Microsoft Lync Server 2010”，网址为 <a href="http://go.microsoft.com/fwlink/p/?linkid=255876">http://go.microsoft.com/fwlink/p/?linkId=255876</a>。




  - 例如，以下命令删除 Web 服务器 atl-cs-001.litwareinc.com 上不再与设备关联的任何设备更新规则：
    
        Clear-CsDeviceUpdateFile -Identity "service:WebServer:atl-cs-001.litwareinc.com"

有关详细信息，请参阅 [Clear-CsDeviceUpdateFile](https://docs.microsoft.com/en-us/powershell/module/skype/Clear-CsDeviceUpdateFile) cmdlet 的帮助主题。

