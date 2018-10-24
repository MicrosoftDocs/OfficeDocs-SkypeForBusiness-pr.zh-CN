---
title: 修改用户体验质量设置
TOCTitle: 修改用户体验质量设置
ms:assetid: a6b41de2-1466-4240-8a70-14ce6f0f3ddc
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg182563(v=OCS.15)
ms:contentKeyID: 49313837
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 修改用户体验质量设置

 

_**上一次修改主题：** 2013-02-23_

默认情况下，用户体验质量 (QoE) 数据会在 60 天后清除。可以使用“用户体验质量数据”页上的设置将该数据保留更长或更短的时间。如果禁用 QoE，则在启用 QoE 之前捕获的数据也将清除。

> [!NOTE]  
> 应该对呼叫详细信息记录 (CDR) 和 QoE 进行配置，使二者保留数据的天数相同。监控报告主页上提供的呼叫详细信息报告 (CDR) 中的每个呼叫均包括 CDR 和 QoE 信息。如果 CDR 和 QoE 的清除期限不同，则某些呼叫可能只包含 CDR 数据，而其他呼叫可能只包含 QoE 数据。



以下过程介绍如何配置 QoE 数据的清除设置。

## 通过使用 Lync Server 控制面板指定 QoE 数据的保留

1.  以 RTCUniversalServerAdmins 组成员的身份或者以 CsVoiceAdministrator、CsServerAdministrator 或 CsAdministrator 角色成员的身份登录计算机。有关详细信息，请参阅[Lync Server 2013 中的委派安装权限](lync-server-2013-delegate-setup-permissions.md)。

2.  打开浏览器窗口，然后输入管理 URL 以打开 Lync Server 控制面板。有关可以用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅[打开 Lync Server 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左侧导航栏中，单击“监控和存档”，然后单击“用户体验质量数据”。

4.  在“用户体验质量数据”页上，单击表中的相应站点，再单击“编辑”，然后单击“显示详细信息”。

5.  要打开清除，请选择“启用 QoE 清除”。

6.  在“QoE 最长保留期限(天)”中选择 QoE 数据的最长保留天数。

7.  单击“提交”。

## 使用 Windows PowerShell cmdlet 指定 QoE 保留

您可以使用 Windows PowerShell 和 **Set-CsQoEConfiguration** cmdlet 来创建 QoE 保留设置。可以从 Lync Server 2013 命令行管理程序或从 Windows PowerShell 的远程会话中运行此 cmdlet。有关使用远程 Windows PowerShell 连接到 Lync Server 的详细信息，请参阅 Lync Server Windows PowerShell 博客文章“快速入门：使用远程 PowerShell 管理 Microsoft Lync Server 2010”，网址为 [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)。

## 为特定位置指定 QoE 保留

  - 此命令会为 Redmond 站点启用 QoE 数据的清除，并将该站点配置为保留 QoE 数据 20 天。
    
        Set-CsQoeConfiguration -Identity "site:Redmond" -EnablePurging -KeepQoEDataForDays 20

## 为多个位置指定 QoE 保留

  - 此命令会为组织中使用的所有 QoE 配置设置配置 QoE 保留。
    
        Get-CsQoEConfiguration | Set-CsQoEConfiguration-EnablePurging -KeepQoEDataForDays 20 

有关详细信息，请参阅 [Set-CsQoEConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsQoEConfiguration) cmdlet 的帮助主题。

## 另请参阅

#### 其他资源

[部署监控](lync-server-2013-deploying-monitoring.md)

