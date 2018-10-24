---
title: 指定保留 CDR 数据
TOCTitle: 指定保留 CDR 数据
ms:assetid: c0fd6056-87bc-4136-902a-f1b37cd3a1ca
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg182581(v=OCS.15)
ms:contentKeyID: 49314137
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 指定保留 CDR 数据

 

_**上一次修改主题：** 2013-02-23_

默认情况下，呼叫详细信息记录 (CDR) 数据会在 60 天后清除。可以使用“呼叫详细信息记录”页上的设置将该数据保留更长或更短的时间。如果禁用 CDR，则在启用 CDR 之前捕获的数据也将清除。

> [!NOTE]  
> 应该对 CDR 和用户体验质量 (QoE) 进行配置，使二者保留数据的天数相同。监控服务器报告网页上提供的呼叫详细信息报告 (CDR) 中的每个呼叫均包括 CDR 和 QoE 信息。如果 CDR 和 QoE 的清除期限不同，则某些呼叫可能只包含 CDR 数据，而其他呼叫可能只包含 QoE 数据。



使用以下过程来配置 CDR 数据的清除设置。

## 指定 CDR 数据的保留

1.  使用 RTCUniversalServerAdmins 组成员（或具有同等用户权限）的用户帐户，或分配给 CsServerAdministrator 或 CsAdministrator 角色的用户帐户，登录到网络中部署了 Lync Server 2013 的任何计算机。

2.  打开浏览器窗口，然后输入管理 URL 以打开 Lync Server 控制面板。有关可以用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅[打开 Lync Server 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左侧导航栏中，单击“监控和存档”，然后单击“呼叫详细信息记录”。

4.  在“呼叫详细信息记录”页上，单击表中的相应站点，再单击“编辑”，然后单击“显示详细信息”。

5.  要打开清除，请选择“启用 CDR 清除”。

6.  在“CDR 最长保留期限(天):”中选择呼叫详细信息记录的最长保留天数。

7.  在“错误报告数据最长保留期限(天):”中选择错误报告的最长保留天数。

8.  单击“提交”。

## 通过 Lync Server 命令行管理程序 cmdlet 指定 CDR 保留

您可以使用 Windows PowerShell 和 Set-CsCdrConfiguration cmdlet 来创建 CDR 保留设置。可以从 Lync Server 2013 命令行管理程序 或从 Windows PowerShell 的远程会话中运行此 cmdlet。有关使用远程 Windows PowerShell 连接到 Lync Server 的详细信息，请参阅 Lync Server Windows PowerShell 博客文章“快速入门：使用远程 PowerShell 管理 Microsoft Lync Server 2010”，网址为 [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)。

## 指定特定位置的 CDR 保留

  - 此命令允许清除 Redmond 站点的 CDR 数据，并将该站点配置为将 CDR 数据和错误报告数据保留 20 天。
    
        Set-CsCdrConfiguration -Identity "site:Redmond" -EnablePurging -KeepCallDetailForDays 20 -KeepErrorReportForDays 20

## 指定多个位置的 CDR 保留

  - 此命令会为组织中使用的所有 CDR 配置设置配置 CDR 保留。
    
        Get-CsCdrConfiguration | Set-CsCdrConfiguration-EnablePurging -KeepCallDetailForDays 20 -KeepErrorReportForDays 20

有关详细信息，请参阅 [Set-CsCdrConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsCdrConfiguration) cmdlet 的帮助主题。

## 另请参阅

#### 其他资源

[Lync Server 2013 中的呼叫详细信息记录 (CDR)](lync-server-2013-call-detail-recording-cdr.md)

