---
title: Lync Server 2013：配置 DNS 主机记录
TOCTitle: 配置 DNS 主机记录
ms:assetid: 78a1afcf-41c8-4da5-8740-c6570c19078c
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg398593(v=OCS.15)
ms:contentKeyID: 49313315
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 配置 Lync Server 2013 的 DNS 主机记录

 

_**上一次修改主题：** 2012-10-01_

要成功完成此过程，应至少以 Domain Admins 组或 DNSAdmins 组成员的身份登录到服务器或域。

## 配置 DNS 主机 A 记录

1.  在域名系统 (DNS) 服务器上，单击“开始”，再单击“管理工具”，然后单击“DNS”。

2.  在域的控制台树中，展开“正向查找区域”，然后右键单击要安装 Lync Server 2013 的域。

3.  单击“新建主机(A 或 AAAA)”。

4.  单击“名称”，键入池的主机名（根据在其中定义记录的区域采用域名，但不需要输入域名作为 A 记录的一部分）。

5.  单击“IP 地址”，为 前端池键入负载平衡器虚拟 IP (VIP)。
    
    > [!IMPORTANT]  
    > 在使用控制器池的部署中，简单 URL 的主机 (A) 记录应指向控制器负载平衡器的 VIP。
    
    > [!NOTE]  
    > 如果只部署一台 Enterprise Edition Server 或控制器（连接到不带负载平衡器的拓扑中），或者部署一台 Standard Edition Server，请键入该 Enterprise Edition Server、Standard Edition Server 或控制器的 IP 地址。如果在一个池中部署多台 Enterprise Edition Server 或控制器，则需要使用负载平衡器。负载平衡器不与 Standard Edition Server 一起使用。
    


6.  单击“添加主机”，然后单击“确定”。

7.  要创建另一个 A 记录，请重复步骤 4 和 5。

8.  创建完所需的全部 A 记录后，单击“完成”。

