---
title: Lync Server 2013：规划边缘服务器证书
TOCTitle: 规划边缘服务器证书
ms:assetid: f1dfe220-2398-4ac8-ba4c-206c8c0cbc50
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg413010(v=OCS.15)
ms:contentKeyID: 49314706
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 在 Lync Server 2013 中规划边缘服务器证书

 

_**上一次修改主题：** 2012-11-05_

Lync Server 2013 中简化了为边缘服务器创建证书的步骤。

**边缘服务器的流程图**

![证书流程图](images/Gg413010.a5fc20db-7ced-4364-b577-6a709a8367cd(OCS.15).jpg "证书流程图")

使用证书向导创建单个公共证书，确保有一个证书定义的可导出私钥并将其分配到以下边缘服务器外部接口：

> [!IMPORTANT]
> Lync Server 中不支持通配符证书，除非用于通过反向代理总结简单 URL。您必须为每个 SIP 域名、 Web 会议边缘服务、 A/V 边缘服务以及您的部署提供的 XMPP 域定义不同的使用者替代名称 (SAN)。


> [!NOTE]  
> 临时音频/视频身份验证证书在 Lync Server 2013 中引入，优先于到期的当前证书，它要求一些其他规划。除了用于外部边缘接口的具有多种用途的一个证书外，还需要两个证书，一个分配到 访问边缘服务和 Web 会议边缘服务，另一个证书用于 A/V 边缘服务。有关其他详细信息，请参阅 <a href="lync-server-2013-staging-av-and-oauth-certificates-using-roll-in-https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsCertificate">在 Set-CsCertificate 中使用滚动分期 AV 和 OAuth 证书</a>



> [!IMPORTANT]
> 在 边缘服务器的池的事件中，将具有私钥的证书导出到每个 边缘服务器，并将该证书分配到每个 边缘服务器服务。对内部 边缘服务器证书执行相同的操作，导出具有私钥的证书，并将其分配到每个内部边缘接口。


  - 确保有一个分配到该证书的可导出私钥

  - 访问边缘服务（在证书向导中称为“SIP 访问边缘外部”）

  - Web 会议边缘服务（在证书向导中称为“Web 会议边缘外部”）

  - A/V 身份验证服务（在证书向导中称为“A/V 边缘外部”）

使用可导出的私钥创建单个内部证书，并将其复制和分配到每个边缘服务器内部接口：

  - 边缘服务器（在证书向导中称为“边缘内部”）

> [!IMPORTANT]
> 可将单独和不同的证书用于每个 边缘服务器服务。选择单独证书的较好理由是是否想将新的滚动证书功能用于 A/V 边缘服务证书。如果是此功能，则建议将 A/V 边缘服务证书从 访问边缘服务和 Web 会议边缘服务分开，如果您选择为每项服务请求、获得和分配单独的证书，则必须请求可为 A/V 边缘服务（这实际上仍然是 A/V 身份验证服务）导出的私钥，并将相同的证书分配到每个 边缘服务器上的 A/V 边缘外部接口。


## 另请参阅

#### 任务

[在 Set-CsCertificate 中使用滚动分期 AV 和 OAuth 证书](lync-server-2013-staging-av-and-oauth-certificates-using-roll-in-https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsCertificate)  

#### 概念

[Lync Server 2013 中影响边缘服务器规划的更改](lync-server-2013-changes-in-lync-server-that-affect-edge-server-planning.md)

