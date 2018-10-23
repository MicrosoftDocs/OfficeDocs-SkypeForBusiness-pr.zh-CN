---
title: Lync Server 2013：创建并验证 DNS SRV 记录
TOCTitle: 创建并验证 DNS SRV 记录
ms:assetid: 86888c7e-1401-458f-9a7b-08ac726deeec
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg398680(v=OCS.15)
ms:contentKeyID: 49313474
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 在 Lync Server 2013 中创建并验证 DNS SRV 记录

 

_**上一次修改主题：** 2013-02-21_

若要成功完成此过程，至少应以 Domain Admins 组或 DnsAdmins 组成员的身份登录到服务器或域。

本主题介绍如何配置需要在 Lync Server 2013 部署中创建的域名系统 (DNS) 记录，以及自动客户端登录所需的域名系统记录。在创建前端池时，安装程序会为池创建 Active Directory 对象和设置，其中包括池的完全限定的域名 (FQDN)。将为 Standard Edition Server 创建类似的对象和设置。要使客户端能够连接到池或Standard Edition Server，必须在 DNS 中注册该池或Standard Edition Server 的 FQDN。必须在内部 DNS 中为每个 SIP 域创建 DNS SRV 记录。此过程假定内部 DNS 具有 SIP 用户域的区域。

## 配置 DNS SRV 记录

1.  在 DNS 服务器上，单击“开始”，再单击“管理工具”，然后单击“DNS”。

2.  在 SIP 域的控制台树中，展开“正向查找区域”，然后右键单击要安装 Lync Server 2013 的 SIP 域。

3.  单击“其他新记录”。

4.  在“选择资源记录类型”中，单击“服务位置(SRV)”，然后单击“创建记录”。

5.  单击“服务”，然后键入 **\_sipinternaltls** 。

6.  单击“协议”，然后键入 **\_tcp** 。

7.  单击“端口号”，然后键入 **5061**。

8.  单击“提供此服务的主机”，然后键入池或 Standard Edition Server 的 FQDN。

9.  单击“确定”，然后单击“完成”。

## 验证 DNS SRV 记录的创建

1.  使用属于 Authenticated Users 组成员的帐户或具有等效权限的帐户登录到域中的客户端计算机。

2.  单击“开始”，然后单击“运行”。

3.  在“打开”框中，键入 **cmd** ，然后单击“确定”。

4.  在命令提示符处键入 **nslookup** ，然后按 Enter。

5.  键入 **set type=srv** ，然后按 Enter。

6.  键入 **\_sipinternaltls.\_tcp.contoso.com** ，然后按 Enter。输出的传输层安全性 (TLS) 记录如下所示：
    
    服务器：*\<dns server\>*.contoso.com
    
    地址：*\<IP address of DNS server\>*
    
    Non-authoritative answer:
    
    \_sipinternaltls.\_tcp.contoso.com SRV service location:
    
    priority = 0
    
    weight = 0
    
    port = 5061
    
    svr hostname = poolname.contoso.com（或 Standard Edition Server A 记录）
    
    poolname.contoso.com internet 地址 = *\<virtual IP Address of the load balancer\>* 或 *\<IP address of a single Enterprise Edition server for pools with only one Enterprise Edition server\>* 或 *\<IP address of the Standard Edition server\>*

7.  完成后，在命令提示符处键入 **exit** ，然后按 Enter。

## 验证是否可以解析前端池或 Standard Edition Server 的 FQDN

1.  登录到域中的一台客户端计算机。

2.  单击“开始”，然后单击“运行”。

3.  在“打开”框中，键入 **cmd** ，然后单击“确定”。

4.  在命令提示符处键入 **nslookup**<span></span>*\<FQDN of the Front End pool\>* 或 *\<FQDN of the Standard Edition server\>*，然后按 Enter。

5.  验证是否收到一个解析为 FQDN 的相应 IP 地址的答复。

