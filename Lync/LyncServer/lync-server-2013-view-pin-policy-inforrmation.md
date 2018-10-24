---
title: 查看 PIN 策略信息
TOCTitle: 查看 PIN 策略信息
ms:assetid: 1d48b060-d77f-44ee-b70f-3ce128aedac4
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ687985(v=OCS.15)
ms:contentKeyID: 49888324
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 查看 PIN 策略信息

 

_**上一次修改主题：** 2013-02-23_

可以使用“PIN 策略”选项卡查看通过 IP 电话连接至 Lync 2013 的用户的个人标识号 (PIN)。若要使用 PIN 身份验证，请确保在 Web 服务设置中选择了“启用 PIN 身份验证”。有关详细信息，请参阅[修改现有的 Web 服务配置设置](lync-server-2013-modify-existing-web-service-configuration-settings.md)。

按照以下步骤修改用户级别或站点级别的 PIN 策略。

## 在 Lync Server 控制面板中查看有关 PIN 策略的信息

1.  使用 RTCUniversalServerAdmins 组成员（或具有同等用户权限）的用户帐户，或分配给 CsServerAdministrator 或 CsAdministrator 角色的用户帐户，登录到网络中部署了 Lync Server 2013 的任何计算机。

2.  打开浏览器窗口，然后输入管理 URL 以打开 Lync Server 控制面板。有关可以用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅[打开 Lync Server 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左侧导航栏中，单击“安全性”，然后单击“PIN 策略”。

4.  在“PIN 策略”页上，单击某个策略，再单击“编辑”，然后单击“显示详细信息”。

## 使用 Lync Server PowerShell Cmdlet 查看 PIN 策略

还可以使用 Windows PowerShell 和 Get-CsPinPolicy cmdlet 查看 PIN 策略。此 cmdlet 可从 Lync Server 2013 命令行管理程序或 Windows PowerShell 的远程会话中运行。有关使用远程 Windows PowerShell 连接到 Lync Server 的详细信息，请参阅 Lync Server Windows PowerShell 博客文章“快速入门：使用远程 PowerShell 管理 Microsoft Lync Server 2010”，网址为 [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)。

## 查看 PIN 策略

  - 若要查看有关所有 PIN 策略的信息，请在 Lync Server 命令行管理程序中键入以下命令，然后按 Enter：
    
        Get-CsPinPolicy
    
    此时将返回如下信息：
    
        Identity             : Global
        Description          :
        MinPasswordLength    : 5
        PINHistoryCount      : 0
        AllowCommonPatterns  : False
        PINLifetime          : 0
        MaximumLogonAttempts :

有关详细信息，请参阅 [Get-CsPinPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsPinPolicy) cmdlet 的帮助主题。

## 另请参阅

#### 任务

[修改现有的 Web 服务配置设置](lync-server-2013-modify-existing-web-service-configuration-settings.md)  
[创建新的 PIN 策略](lync-server-2013-create-a-new-pin-policy.md)

