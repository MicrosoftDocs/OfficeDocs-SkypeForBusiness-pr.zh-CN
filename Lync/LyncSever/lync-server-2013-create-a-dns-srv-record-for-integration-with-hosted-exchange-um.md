---
title: Lync Server 2013：为与托管 Exchange UM 的集成创建 DNS SRV 记录
TOCTitle: 为与托管 Exchange UM 的集成创建 DNS SRV 记录
ms:assetid: 8ea590ae-58ea-4ca5-9853-e0708b3ea760
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Hh500728(v=OCS.15)
ms:contentKeyID: 49313558
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 为与托管 Exchange UM 的集成创建 DNS SRV 记录

 

_**上一次修改主题：** 2016-12-08_

本主题介绍如何配置 Lync Server 2013  边缘服务器所需的域名系统 (DNS) SRV 记录以传送到托管 Exchange 服务（如 Microsoft Exchange Online）。

## 为托管 Exchange 服务创建外部 DNS SRV 记录

1.  以 DnsAdmins 组成员的身份登录外部 DNS 服务器。

2.  依次单击“开始”、“管理工具”和“DNS”。

3.  在 SIP 域的控制台树中，展开“正向查找区域”，并选择将在其中安装 Lync Server 2013 的 SIP 域。
    
    > [!IMPORTANT]
    > 您必须在 Lync Server 所在的或将安装 Lync Server 的 SIP 域中创建 DNS SRV 记录。在创建 SRV 记录时，用于“提供此服务的主机”字段的 FQDN 必须是边缘池的外部 FQDN。例如，如果边缘池的外部 FQDN 为 edge01.contoso.net，请输入该值。此外，此记录必须位于 DNS 主机 (A) 记录所在的域中。


4.  右键单击选定的域，再单击“其他新记录”。

5.  在“资源记录类型”中，单击“服务位置(SRV)”，再单击“创建记录”。

6.  在“新建资源记录”中，单击“服务”，再键入 **\_sipfederationtls** 。

7.  单击“协议”，再键入 **\_tcp**。

8.  单击“端口号”，然后键入 **5061**。

9.  单击“提供此服务的主机”，再键入为受信任的外部客户端提供对您的 Lync Server 2013 系统的访问权的 Lync Server 2013  边缘池的完全限定的域名 (FQDN)。
    
    > [!NOTE]  
    > 此外，还必须将域设置为 Exchange Online 设置中的权威性的接受域。有关详细信息，请参阅“创建接受域”，网址为 <a href="http://go.microsoft.com/fwlink/p/?linkid=229762">http://go.microsoft.com/fwlink/p/?linkId=229762</a>。
    


10. 单击“确定”，然后单击“完成”。

## 验证是否已成功创建 DNS SRV 记录

1.  登录到域中的一台客户端计算机。

2.  单击“开始”，然后单击“运行”。

3.  在命令提示符下，运行下列命令：
    
        nslookup <FQDN Lync Edge Pool>

4.  验证是否收到一个解析为 FQDN 的相应 IP 地址的答复。

## 另请参阅

#### 概念

[在 Lync Server 2013 中为反向代理服务器创建 DNS 记录](lync-server-2013-create-dns-records-for-reverse-proxy-servers.md)

