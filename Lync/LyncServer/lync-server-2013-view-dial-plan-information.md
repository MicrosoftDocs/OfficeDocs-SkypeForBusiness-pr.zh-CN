---
title: 查看拨号计划信息
TOCTitle: 查看拨号计划信息
ms:assetid: 25ed0112-a8a7-418a-8c2c-580081be692a
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ687997(v=OCS.15)
ms:contentKeyID: 49888347
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 查看拨号计划信息

 

_**上一次修改主题：** 2012-11-01_

若要查看现有拨号计划信息，请执行以下过程中的步骤。如果要创建新拨号计划，请参阅[在 Lync Server 2013 中创建拨号计划](lync-server-2013-create-a-dial-plan.md)。

## 从 Lync Server 控制面板查看有关拨号计划的信息

1.  以 RTCUniversalServerAdmins 组成员的身份或者以 CsVoiceAdministrator、CsServerAdministrator 或 CsAdministrator 角色成员的身份登录计算机。有关详细信息，请参阅[Lync Server 2013 中的委派安装权限](lync-server-2013-delegate-setup-permissions.md)。

2.  打开浏览器窗口，然后输入管理 URL 以打开 Lync Server 控制面板。有关可以用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅[打开 Lync Server 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左侧导航栏中，单击“语音路由”，然后单击“拨号计划”。

4.  在“拨号计划”页上，双击某个拨号计划名称。
    
    > [!NOTE]
    > 一次只能查看一个拨号计划的信息。


## 使用 Windows PowerShell Cmdlet 查看拨号计划

  - 还可以使用 Windows PowerShell 命令行接口 和 **Get-CsDialPlan** cmdlet 查看拨号计划。可以从 Lync Server 2013 命令行管理程序或从 Windows PowerShell 的远程会话运行此 cmdlet。有关使用远程 Windows PowerShell 连接到 Lync Server 的详细信息，请参阅 Lync Server Windows PowerShell 博客文章“快速入门：使用远程 PowerShell 管理 Microsoft Lync Server 2010”，网址为 [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)。
    
    若要查看有关您的所有拨号计划的信息，请在 Lync Server 命令行管理程序中键入以下命令然后按 Enter：
    
        Get-CsDialPlan
    
    该命令将返回如下信息：
    
        Identity                 : Global
        Description              :
        DialinConferencingRegion :
        NormalizationRules       : {Description=;
                                   Pattern=^(\d+)$;Translation=$1;Name=
                                   KeepAll;IsInternalExtension=False}
        CountryCode              :
        State                    :
        City                     :
        ExternalAccessPrefix     :
        SimpleName               : DefaultProfile
        OptimizeDeviceDialing    : False

## 另请参阅

#### 任务

[在 Lync Server 2013 中创建拨号计划](lync-server-2013-create-a-dial-plan.md)  
[在 Lync Server 2013 中修改拨号计划](lync-server-2013-modify-a-dial-plan.md)

