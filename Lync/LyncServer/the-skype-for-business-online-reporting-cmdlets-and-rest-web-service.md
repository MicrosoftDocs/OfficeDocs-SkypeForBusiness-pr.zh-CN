---
title: Lync Online：Lync Online 报告 cmdlet 和 REST Web 服务
TOCTitle: Lync Online 报告 cmdlet 和 REST Web 服务
ms:assetid: cadd73a7-c08a-4102-b73a-ccb3ad4987bf
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Dn362845(v=OCS.15)
ms:contentKeyID: 56271204
ms.date: 06/02/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Online 报告 cmdlet 和 REST Web 服务

 

_**上一次修改主题：** 2016-12-08_

与报告功能接合使用，Skype for Business Online 可提供对五个 Windows PowerShell cmdlet 的访问权限，这些 cmdlet 可帮助生成那些报告，也可以由管理员用于返回自定义的报告数据。Skype for Business Online 也包括 REST（表述性状态转移），可以由开发人员用于检索自定义的报告信息。

可供管理员使用的报告 cmdlet 包括：

  - Get-CsActiveUserReport：提供有关活动用户（即，已登录到 Skype for Business Online 并至少参与一个会议或对等通信会话的用户）数目的信息。

  - Get-CsAVConferenceTimeReport：提供有关用户对音频/视频会议所花的时间（分钟）的信息。

  - Get-CsConferenceReport：提供有关用户参与的会议数和会议类型的信息。

  - Get-CsP2PAVTimeReport：提供有关用户对对等会话（包括音频和/或视频）所花的时间（分钟）的信息。

  - Get-CsP2PSessionReport：提供有关用户参与的对等会话数和对等会话类型的信息。

大多数管理员将使用 Office 365 管理中心中可用的报告：这些报告不仅仅是自动生成的，它们还提供数据的图形表示，这些图形表示比报告 cmdlet 返回的原始数值更容易解释。但是，熟悉 Windows PowerShell 的管理员可以使用报告 cmdlet 返回无法从 Lync Online 报告轻松获得的数据。例如，报告 cmdlet 返回有关会话持续时间的信息（每个会话持续的时间量，以分钟为单位）。个别会话持续时间无法使用 Lync Online 报告获得。同样，在天视图中，Lync Online 报告仅显示过去 7 天的信息。如果想要查看不同日期（例如，四个月以前的某个日期）的日总计，则可以使用报告 cmdlet 实现。

管理员还可能会对文章[使用 Excel 检索 Office 365 报告数据](http://msdn.microsoft.com/en-us/library/dn781442.aspx)感兴趣，该文章说明如何使用 Microsoft Excel 中的 OData 数据查询功能创建自定义 Office 365 报告。自定义报告使您能够规定从 Office 365 报告服务返回哪些数据以及数据量。自定义报告还使您能够指定如何对数据进行排序和分组等操作，并提供对未显示在 Office 365 管理中心中的信息的访问。

有开发背景的管理员可以使用 REST Web 服务获得 Skype for Business Online 管理中心中未显示的信息。REST 服务与 SOAP 服务类似，因为每项技术都提供在客户端和服务器之间传输 XML 数据的方式。但是，相比 SOAP 服务，REST 服务至少有两个优势。首先，REST 使用标准化格式（也称为 ATOM 联合格式）执行 XML 数据传输。相反，SOAP 传输数据时使用非标准格式。此外，REST 能够跨可阻止 GET 和 POST 之外的其他 HTTP 谓词的网络传输数据。

## 另请参阅

#### 其他资源

[Lync Online 报告](https://technet.microsoft.com/zh-cn/library/dn362827\(v=ocs.15\))  
[Office 365 报告 Web 服务](http://msdn.microsoft.com/en-us/library/office/jj984325.aspx)  
[了解 Office 365 报告 Web 服务](http://msdn.microsoft.com/en-us/library/office/jj984321.aspx)  
[Exchange Online 报告 Cmdlet](http://technet.microsoft.com/en-us/library/jj200780\(v=exchg.150\).aspx)  
[使用 Excel 检索 Office 365 报告数据](http://msdn.microsoft.com/en-us/library/dn781442.aspx)

