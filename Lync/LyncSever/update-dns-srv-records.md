---
title: 更新 DNS SRV 记录
TOCTitle: 更新 DNS SRV 记录
ms:assetid: 9542b91a-108c-4980-89ec-634905cbbf26
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ688139(v=OCS.15)
ms:contentKeyID: 49888521
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 更新 DNS SRV 记录

 

_**上一次修改主题：** 2012-09-29_

若要成功完成此过程，应以 Domain Admins 组或 DnsAdmins 组成员的身份登录到服务器或域。

本主题介绍如何在迁移到 Lync Server 2013 后更新域名系统 (DNS) 记录。将所有用户移至 Lync Server 2013 后和停用旧版 Lync Server 2010 池或控制器之前，必须更新每个 SIP 域的内部 DNS 中的 DNS SRV 记录。此过程假定内部 DNS 具有 SIP 用户域的区域。

**配置 DNS SRV 记录**

1.  在 DNS 服务器上，单击“开始”，再单击“管理工具”，然后单击“DNS”。

2.  在 SIP 域的控制台树中，展开“正向查找区域”，再展开安装了 Lync Server 2013 的 SIP 域，然后导航到 **\_tcp** 设置。

3.  在右侧窗格中，右键单击“\_sipinternaltls” 并选择“属性”。

4.  在“提供此服务的主机”中，更新主机 FQDN 以指向 Lync Server 2013 池。

5.  单击“确定”。

**验证是否可以解析前端池或 Standard Edition Server 的 FQDN**

1.  登录到域中的一台客户端计算机。

2.  单击“开始”，然后单击“运行”。

3.  在“打开”框中，键入 **cmd** ，然后单击“确定”。

4.  在命令提示符处键入 **nslookup**<span></span>*\<FQDN of the Front End pool\>* 或 *\<FQDN of the Standard Edition server\>*，然后按 Enter。

5.  验证是否收到一个解析为 FQDN 的相应 IP 地址的答复。

