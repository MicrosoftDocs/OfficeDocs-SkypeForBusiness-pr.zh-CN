---
title: Lync Server 2013：设置公共即时消息连接
TOCTitle: 设置公共即时消息连接
ms:assetid: 816dea2a-96fa-4a36-b6c2-a9402675868b
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ205041(v=OCS.15)
ms:contentKeyID: 49313428
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 在 Lync Server 2013 中设置公共即时消息连接

 

_**上一次修改主题：** 2012-09-08_

如果组织希望支持与 AOL 的公共即时消息 (IM) 连接，则不能使用 Lync Server 部署向导请求证书。而是应执行以下过程中的步骤。

## 设置公共即时消息连接

1.  在前端服务器上，打开拓扑生成器。展开“边缘池”，然后右键单击您的边缘服务器或边缘服务器池。选择“编辑属性”。

2.  在“编辑属性”中的“常规”下，选择“为此边缘池启用联盟(端口 5061)”。单击“确定”。

3.  单击“操作”，选择“拓扑”，再选择“发布”。当“发布拓扑”中出现提示时，单击“下一步”。完成发布后，单击“完成”。

4.  在边缘服务器上，打开 Lync Server 部署向导。单击“安装或更新 Lync Server 系统”，然后单击“安装或删除 Lync Server 组件”。单击“再次运行”。

5.  在“设置 Lync Server 组件”中，单击“下一步”。摘要屏幕将显示已执行的操作。部署完成后，单击“查看日志”可查看可用日志文件。单击“完成”以完成部署。

## 为边缘服务器的外部接口创建证书请求以支持与 AOL 的公共 IM 连接

1.  如果所需模板可供 CA 使用，请使用以下 Windows PowerShell cmdlet 在边缘服务器上请求证书：
    
        Request-CsCertificate -New -Type AccessEdgeExternal  -Output C:\ <certfilename.txt or certfilename.csr>  -ClientEku $true -Template <template name>
    
    用于 Lync Server 的模板的默认证书名称是 Web Server。仅当需要使用与默认模板不同的模板时指定 \<模板名称\>。
    
    > [!IMPORTANT]
    > 如果组织希望支持与 AOL 的公共 IM 连接，则必须使用 Windows PowerShell（而非证书向导）请求要分配给访问边缘服务的外部边缘的证书。这是因为证书向导用于请求证书的证书颁发机构 (CA) Web 服务器模板不支持客户端 EKU 配置。使用 Windows PowerShell 创建证书之前，CA 管理员必须创建和部署支持客户端 EKU 的新模板。

