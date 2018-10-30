---
title: 批准设备更新规则
TOCTitle: 批准设备更新规则
ms:assetid: 9dbb1c9a-be0f-4e13-9234-05501ab43ac5
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ994053(v=OCS.15)
ms:contentKeyID: 52061085
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 批准设备更新规则

 

_**上一次修改主题：** 2013-02-23_

导入一条设备更新规则后，它将安装在您的测试设备上。如果您的测试成功，并且您希望将更新部署到组织中，可使用 Lync Server 控制面板或 Windows PowerShell 批准它。

## 使用 Lync Server 控制面板批准设备更新规则

1.  使用分配给 CsUserAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。

2.  打开浏览器窗口，然后输入管理 URL 以打开 Lync Server 控制面板。有关可以用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅[打开 Lync Server 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在“设备更新”页上，执行下列操作之一：
    
      - 若要批准一个规则，请选择该规则。
    
      - 若要批准所有规则，请单击“编辑”，然后单击“全选”。

4.  单击“操作”，然后单击“批准”。

## 使用 Windows PowerShell Cmdlet 批准设备更新规则

也可以使用 Windows PowerShell 和 **Approve-CsDeviceUpdateRule** cmdlet 批准设备更新规则。可以从 Lync Server 2013 命令行管理程序或从 Windows PowerShell 的远程会话运行此 cmdlet。

> [!NOTE]  
> 有关使用远程 Windows PowerShell 连接到 Lync Server 的详细信息，请参阅 Lync Server Windows PowerShell 博客文章“快速入门：使用远程 PowerShell 管理 Microsoft Lync Server 2010”，网址为 <a href="http://go.microsoft.com/fwlink/p/?linkid=255876">http://go.microsoft.com/fwlink/p/?linkId=255876</a>。



## 批准单个设备更新规则

  - 下面的命令批准在 Web 服务器 atl-cs-001.litwareinc.com 上找到的设备更新规则 d5ce3c10-2588-420a-82ac-dc2d9b1222ff9：
    
        Approve-CsDeviceUpdateRule -Identity service:WebServer:atl-cs-001.litwareinc.com/d5ce3c10-2588-420a-82ac-dc2d9b1222ff9

## 批准多个设备更新规则

  - 此命令批准 Microsoft 品牌设备的所有设备更新规则：
    
        Get-CsDeviceUpdateRule | Where-Object {$_.Brand -eq "Microsoft"} | Approve-CsDeviceUpdateRule

有关详细信息，请参阅 [Approve-CsDeviceUpdateRule](https://docs.microsoft.com/en-us/powershell/module/skype/Approve-CsDeviceUpdateRule) cmdlet 的帮助主题。

## 另请参阅

#### 任务

[导入设备更新规则](lync-server-2013-import-device-update-rules.md)  
[还原设备更新规则](lync-server-2013-restore-a-device-update-rule.md)

