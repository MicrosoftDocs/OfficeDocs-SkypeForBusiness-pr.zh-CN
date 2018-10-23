---
title: 导入设备更新规则
TOCTitle: 导入设备更新规则
ms:assetid: 919e9c87-912b-4bc9-92e7-5998fc2e0bf0
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ994056(v=OCS.15)
ms:contentKeyID: 52061072
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 导入设备更新规则

 

_**上一次修改主题：** 2013-02-23_

只能使用 Windows PowerShell 和 **Import-CsDeviceUpdate** cmdlet 导入设备更新规则。可以从 Lync Server 2013 命令行管理程序或从 Windows PowerShell 的远程会话运行此 cmdlet。

> [!NOTE]  
> 有关使用远程 Windows PowerShell 连接到 Lync Server 的详细信息，请参阅 Lync Server Windows PowerShell 博客文章“快速入门：使用远程 PowerShell 管理 Microsoft Lync Server 2010”，网址为 <a href="http://go.microsoft.com/fwlink/p/?linkid=255876">http://go.microsoft.com/fwlink/p/?linkId=255876</a>。




## 将设备更新规则导入单个 Web 服务器

  - 以下命令将设备更新规则导入 Web 服务器 atl-cs-001.litwareinc.com：
    
        Import-CsDeviceUpdate -Identity "service:WebServer:atl-cs-001.litwareinc.com" -FileName C:\Updates\UCUpdates.cab

## 将设备更新规则导入所有 Web 服务器

  - 在此示例中，设备更新规则将导入您的组织中部署的所有 Web 服务器。为使此命令生效，文件夹 \\\\atl-fs-001.litwareinc.com\\Updates 必须是共享的且可供所有 Web 服务器使用。
    
        Get-CsService -WebServer | ForEach-Object {Import-CsDeviceUpdate -Identity $_.Identity -FileName \\atl-fs-001.litwareinc.com\Updates\UCUpdates.cab}

有关详细信息，请参阅 [Import-CsDeviceUpdate](https://docs.microsoft.com/en-us/powershell/module/skype/Import-CsDeviceUpdate) cmdlet 的帮助主题。

## 另请参阅

#### 任务

[查看有关设备更新规则的信息](lync-server-2013-view-information-about-device-update-rules.md)  
[批准设备更新规则](lync-server-2013-approve-a-device-update-rule.md)

