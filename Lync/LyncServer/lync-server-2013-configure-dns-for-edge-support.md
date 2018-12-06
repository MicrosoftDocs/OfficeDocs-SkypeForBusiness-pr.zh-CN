---
title: Lync Server 2013：配置边缘支持的 DNS
TOCTitle: 配置边缘支持的 DNS
ms:assetid: 955493e6-aa29-424d-bb81-1ef87b3b15e3
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg398756(v=OCS.15)
ms:contentKeyID: 49313645
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 在 Lync Server 2013 中配置边缘支持的 DNS

 

_**上一次修改主题：** 2013-02-15_

您必须为内部边缘接口和外部边缘接口配置域名系统 (DNS) 记录，同时包括边缘服务器和反向代理接口。默认情况下，边缘服务器不会加入域，并且不会具有完全限定的域名。边缘服务器仅引用短（计算机）名称，而不是完全限定的域名。但是 拓扑生成器使用 FQDNs，而不是短名称。边缘服务器的名称必须与 拓扑生成器使用的 FQDN 匹配。为此，定义与计算机名称结合使用的 DNS 后缀将生成预期 FQDN。使用“向未加入域的边缘服务器上的计算机名称添加 DNS 后缀”中的以下过程向计算机名称添加 DNS 后缀。

> [!NOTE]  
> 默认情况下，对于查询的 DNS 域名，如果查询结果中存在同一类型的多个资源记录，则 DNS 会使用循环算法轮换该查询结果中所返回的资源记录数据的顺序。 Lync Server 2013 DNS 负载平衡取取决于作为 DNS 负载平衡机制一部分的 DNS 循环。确认此循环设置未禁用。如果使用的不是运行 Windows 操作系统的 DNS 服务器，则确认循环资源记录顺序已启用。



使用“创建 DNS SRV 记录”中的过程创建并验证每个 DNS SRV 记录。使用“创建 DNS A 记录”中的过程定义外部用户访问所需的 DNS A 记录。若要确认已正确配置和运行记录，请参阅本主题的“验证 DNS 记录”。有关支持外部用户访问所需的每个记录的详细信息，请参阅[确定 Lync Server 2013 的 DNS 要求](lync-server-2013-determine-dns-requirements.md)。

## 向未加入域的边缘服务器上的计算机名称添加 DNS 后缀

1.  在计算机上，单击“开始”，右键单击“计算机”，然后单击“属性”。

2.  在“计算机名称、域和工作组设置”下，单击“更改设置”。

3.  在“计算机名称”选项卡上，单击“更改”。

4.  在“计算机名称/域更改”中，单击“更多”。

5.  在“DNS 后缀和 NetBIOS 计算机名称”的“此计算机的主 DNS 后缀”中，键入内部域的名称（例如，corp.contoso.com），然后单击“确定”三次。

6.  重新启动计算机。

## 创建 DNS SRV 记录

1.  在相应的 DNS 服务器上，依次单击“开始”、“控制面板”、“管理工具”，然后单击“DNS”。
    
    > [!IMPORTANT]  
    > 您需要配置 DNS 来提供以下内容：1) 由远程用户和联合合作伙伴查找的外部 DNS 的外部 DNS 条目；2) 由外围网络中的边缘服务器使用的 DNS 查找的条目（也称为 DMZ、第三区域和被筛选的子网），包括运行 Lync Server 2013 的内部服务器的 A 记录；3) 由运行 Lync Server 2013 的内部客户端和服务器查找的内部 DNS 条目。


2.  在 SIP 域的控制台树中，展开“正向查找区域”，然后右键单击安装了 Lync Server 2013 的域。

3.  单击“其他新记录”。

4.  在“选择资源记录类型”中，键入“服务位置 (SRV)”，然后单击“创建记录”。

5.  提供所有所需的 DNS SRV 记录的信息。

## 创建 DNS A 记录

1.  在 DNS 服务器上，依次单击“开始”、“控制面板”、“管理工具”，然后单击“DNS”。

2.  在 SIP 域的控制台树中，展开“正向查找区域”，然后右键单击安装了 Lync Server 2013 的域。

3.  单击“新建主机 (A)”。

4.  提供所有所需的 DNS SRV 记录的信息。

## 验证 DNS 记录

1.  登录到域中的一台客户端计算机。

2.  单击“开始”，然后单击“运行”。

3.  在命令提示符下，运行下列命令：
    
        nslookup <FQDN edge interface>

4.  验证是否收到一个解析为 FQDN 的相应 IP 地址的答复。

## 另请参阅

#### 任务

[为与托管 Exchange UM 的集成创建 DNS SRV 记录](lync-server-2013-create-a-dns-srv-record-for-integration-with-hosted-exchange-um.md)  

#### 概念

[确定 Lync Server 2013 的 DNS 要求](lync-server-2013-determine-dns-requirements.md)

