---
title: Lync Server 2013：验证能否通过反向代理进行访问
TOCTitle: 验证能否通过反向代理进行访问
ms:assetid: 3076a786-e022-4d41-91ec-1bf252b2a468
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg429697(v=OCS.15)
ms:contentKeyID: 49312396
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 在 Lync Server 2013 中验证能否通过反向代理进行访问

 

_**上一次修改主题：** 2013-03-29_

使用以下过程验证用户是否能够访问反向代理上的信息。您可能需要完成防火墙配置和域名系统 (DNS) 配置，才能正确进行访问。

## 验证是否能通过 Internet 访问网站

  - 打开 Web 浏览器，在“地址”栏中键入客户端用于访问通讯簿文件和会议网站的 URL，具体如下：
    
      - 对于通讯簿服务器，请键入类似下面的 URL：**https://<span></span>*externalwebfarmFQDN*<span></span>/abs** ，其中 *externalwebfarmFQDN* 是托管通讯簿服务的外部 Web 服务的外部 FQDN。用户应收到 HTTP 质询，因为默认情况下将通讯簿服务器文件夹的目录安全性配置为 Windows 身份验证。
    
      - 对于会议，请键入类似下面的 URL：**https://<span></span>*externalwebfarmFQDN*<span></span>/meet** ，其中 *externalwebfarmFQDN* 是托管会议内容的 Web 场的外部 FQDN。此 URL 应会显示会议的疑难解答页。或者，确认您的会议的简单 URL 能正常工作。用于加入会议的简单 URL 的示例是 https://meet.contoso.com
    
      - 对于通讯组扩展，请键入类似下面的 URL：**https://<span></span>*externalwebfarmFQDN*<span></span>/GroupExpansion/service.svc** 。用户应收到 HTTP 质询，因为默认情况下将通讯组扩展服务的目录安全性配置为 Windows 身份验证。
    
      - 对于电话拨入式会议，请键入类似下面的简单 URL：**https://<span></span>*externalwebfarmFQDN*<span></span>/dialin** ，其中 *externalwebfarmFQDN* 是托管电话拨入式会议的拨入页的 Web 场的外部 FQDN。应将用户定向到拨入页。或者，确认您的电话拨入式会议的简单 URL 能正常工作。电话拨入式会议的简单 URL 的示例是 https://dialin.contoso.com
    
      - 要确认自动发现 URL 是否正常工作，请键入 https://lyncdiscover. *externaldomainFQDN*。浏览器应会提示您打开文件。选择记事本以将其打开。典型的响应类似于：
        
            {"AccessLocation":"External","Root":{"Links":[{"href":"https:\/\/extweb.contoso.com\/Autodiscover\/AutodiscoverService.svc\/root\/domain","token":"Domain"},
            {"href":"https:\/\/extweb.contoso.com\/Autodiscover\/AutodiscoverService.svc\/root\/user","token":"User"},
            {"href":"https:\/\/lyncweb.contoso.com\/Autodiscover\/AutodiscoverService.svc\/root\/oauth\/user","token":"OAuth"}]}}

