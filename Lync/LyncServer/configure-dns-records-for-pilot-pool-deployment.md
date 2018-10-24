---
title: 为试点池部署配置 DNS 记录
TOCTitle: 为试点池部署配置 DNS 记录
ms:assetid: eb421bad-4bf1-4837-a077-7795094692d9
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ721921(v=OCS.15)
ms:contentKeyID: 49888666
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 为试点池部署配置 DNS 记录

 

_**上一次修改主题：** 2012-09-29_

部署 Lync Server 2013 试点池之前，必须为试点池更新 DNS 主机 A 条目。若要成功完成此过程，至少应以 Domain Admins 组或 DnsAdmins 组成员的身份登录到服务器或域。

**配置 DNS 主机 A 记录**

1.  在域名系统 (DNS) 服务器上，单击“开始”，再单击“管理工具”，然后单击“DNS”。

2.  在域的控制台树中，展开“正向查找区域”，然后右键单击要安装 Lync Server 2013 的域。

3.  单击“新建主机（A 或 AAAA）”。

4.  单击“名称”，键入 Lync Server 2013 池的主机名（根据在其中定义记录的区域采用域名，但不需要输入域名作为 A 记录的一部分）。

5.  单击“IP 地址”，键入 前端池的 IP 地址。

6.  单击“添加主机”，然后单击“确定”。

7.  完成后，单击“完成”。

