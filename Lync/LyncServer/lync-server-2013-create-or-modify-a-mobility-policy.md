---
title: 创建或修改移动策略
TOCTitle: 创建或修改移动策略
ms:assetid: fc2dfea0-2215-440d-9f4b-7c985da29211
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ721946(v=OCS.15)
ms:contentKeyID: 49888693
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 创建或修改移动策略

 

_**上一次修改主题：** 2013-02-23_

您可以创建可修改移动策略以允许移动用户使用受支持的移动设备来实现 Lync 功能，例如，即时消息 (IM)、状态和联系人。可以从 Lync Server 2013 控制面板或 Lync Server 2013 命令行管理程序创建或修改移动策略

## 从 Lync Server 控制面板创建移动策略

1.  使用分配给 CsUserAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。

2.  打开浏览器窗口，然后输入管理 URL 以打开 Lync Server 控制面板。有关可以用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅[打开 Lync Server 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左侧导航栏中，单击“客户端”，然后单击“移动策略”导航按钮。

4.  在“移动策略”页上，单击“新建”，并执行下列操作之一：
    
    1.  要创建站点移动策略，请依次单击“站点策略”、“站点”和“确定”，查看默认设置，且如果需要，可做任何更改。
    
    2.  要创建用户移动策略，请单击“用户策略”，键入名称，查看默认设置，且如果需要，可做任何更改。

5.  单击“提交”。

## 从 Lync Server 控制面板修改移动策略

1.  使用分配给 CsUserAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。

2.  打开浏览器窗口，然后输入管理 URL 以打开 Lync Server 控制面板。有关可以用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅[打开 Lync Server 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左侧导航栏中，单击“客户端”，然后单击“移动策略”导航按钮。

4.  在“移动策略”页上，单击其中的一个现有移动策略。

5.  在“编辑”菜单上，单击“显示详细信息”。

6.  编辑任何设置。

7.  单击“提交”。

## 使用 Windows PowerShell Cmdlet 删除外部访问策略

还可以通过使用 Windows PowerShell 和 **New-CsMobilityPolicy** cmdlet（在站点作用域或每用户作用域）创建移动策略。另外，可以使用 **Set-CsMobilityPolicy** cmdlet 修改任何现有策略，包括全局策略。这些 cmdlet 可以从 Lync Server 2013 命令行管理程序或从 Windows PowerShell 的远程会话运行。有关使用远程 Windows PowerShell 连接到 Lync Server 的详细信息，请参阅 Lync Server Windows PowerShell 博客文章“快速入门：使用远程 PowerShell 管理 Microsoft Lync Server 2010”，网址为 [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)。

## 在站点作用域创建移动策略

  - 此命令可用于为 Redmond 站点创建新的移动策略：
    
        New-CsMobilityPolicy -Identity "site:Redmond"
    
    因为在上述命令中没有指定任何参数（不是必需的 Identity 参数），所以这些策略会为其所有属性使用默认值。

## 在每用户作用域创建移动策略

  - 要在每用户作用域创建移动策略，请为该策略指定唯一身份：
    
        New-CsMobilityPolicy -Identity "RedmondMobilityPolicy"

## 创建移动策略时更改单个属性值

  - 要创建使用不同属性值的策略，请包括属性参数和属性值。例如，此命令可创建禁用单位电话的移动策略：
    
        New-CsMobilityPolicy -Identity "site:Redmond" -EnableOutsideVoice $False

## 创建移动策略时更改多个属性值

  - 通过包括多个参数可修改多个属性值。例如，此命令可用于创建禁用移动和单位电话的策略：
    
        New-CsMobilityPolicy "site:Redmond" -EnableMobility $False -EnableOutsideVoice $False

有关详细信息，请参阅 [New-CsMobilityPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsMobilityPolicy) 和 [Set-CsMobilityPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsMobilityPolicy) cmdlet 的帮助主题。

## 另请参阅

#### 任务

[在 Lync Server 2013 中配置移动策略](lync-server-2013-configuring-mobility-policy.md)

