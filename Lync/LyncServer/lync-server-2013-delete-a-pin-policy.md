---
title: 删除 PIN 策略
TOCTitle: 删除 PIN 策略
ms:assetid: 7c378927-2e41-418e-9721-327021bd2e45
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg521020(v=OCS.15)
ms:contentKeyID: 49313353
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 删除 PIN 策略

 

_**上一次修改主题：** 2013-02-23_

按照以下步骤删除个人标识号 (PIN) 策略。

> [!NOTE]  
> 无法删除全局 PIN 策略。



## 在 Lync Server 2013 控制面板中删除 PIN 策略

1.  使用 RTCUniversalServerAdmins 组成员（或具有同等用户权限）的用户帐户，或分配给 CsServerAdministrator 或 CsAdministrator 角色的用户帐户，登录到网络中部署了 Lync Server 2013 的任何计算机。

2.  打开浏览器窗口，然后输入管理 URL 以打开 Lync Server 控制面板。有关可以用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅[打开 Lync Server 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左侧导航栏中，单击“安全性”，然后单击“PIN 策略”。

4.  在“PIN 策略”页上的搜索字段中，键入要删除的策略的全部或部分名称。

5.  在策略列表中，单击所需的策略，再单击“编辑”，然后单击“删除”。

6.  单击“确定”。

## 使用 Lync Server 命令行管理程序和 Cmdlet 删除 PIN 策略

使用 Windows PowerShell 和 Remove-CsPinPolicy cmdlet 删除 PIN 策略。您可以从 Lync Server 2013 命令行管理程序或从 Windows PowerShell 的远程会话运行此 cmdlet。有关使用远程 Windows PowerShell 连接到 Lync Server 的详细信息，请参阅 Lync Server Windows PowerShell 博客文章“快速入门：使用远程 PowerShell 管理 Microsoft Lync Server 2010”，网址为 [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)。

## 删除特定 PIN 策略

  - 以下命令使用 Identity RedmondPinPolicy 删除 PIN 策略：
    
        Remove-CsPinPolicy -Identity "RedmondPinPolicy"

## 删除应用于站点作用域的所有 PIN 策略

  - 以下命令删除在站点作用域配置的所有 PIN 策略：
    
        Get-CsPinPolicy -Filter "site:*" | Remove-CsPinPolicy

## 删除允许使用通用模式的所有 PIN 策略

  - 以下命令删除允许使用通用模式的所有 PIN 策略：G
    
        et-CsPinPolicy | Where-Object {$_.AllowCommonPatterns -eq $True} | Remove-CsPinPolicy

有关详细信息，请参阅 [Remove-CsPinPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsPinPolicy) cmdlet 的帮助主题。

