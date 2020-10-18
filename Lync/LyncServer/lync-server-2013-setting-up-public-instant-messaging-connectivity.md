---
title: Lync Server 2013：设置公共即时消息连接
description: Lync Server 2013：设置公共即时消息连接。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Setting up public instant messaging connectivity
ms:assetid: 816dea2a-96fa-4a36-b6c2-a9402675868b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205041(v=OCS.15)
ms:contentKeyID: 48184661
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1d2f11c5e01de697b97395b6bc52815fadedff5c
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48580108"
---
# <a name="setting-up-public-instant-messaging-connectivity-in-lync-server-2013"></a>在 Lync Server 2013 中设置公共即时消息连接

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-09-08_

如果组织希望支持与 AOL 的公共即时消息 (IM) 连接，则不能使用 Lync Server 部署向导请求证书。而是应执行以下过程中的步骤。

<div>

## <a name="setting-up-public-instant-messaging-connectivity"></a>设置公共即时消息连接

1.  在前端服务器上，打开拓扑生成器。展开“边缘池”，然后右键单击您的边缘服务器或边缘服务器池。选择“编辑属性”。

2.  在“编辑属性”中的“常规”下，选择“为此边缘池启用联盟(端口 5061)”。单击“确定”。

3.  单击“操作”，选择“拓扑”，再选择“发布”。当“发布拓扑”中出现提示时，单击“下一步”。完成发布后，单击“完成”。

4.  在边缘服务器上，打开 Lync Server 部署向导。单击“安装或更新 Lync Server 系统”，然后单击“安装或删除 Lync Server 组件”。单击“再次运行”。

5.  在“设置 Lync Server 组件”中，单击“下一步”。摘要屏幕将显示已执行的操作。部署完成后，单击“查看日志”可查看可用日志文件。单击“完成”以完成部署。

</div>

<div>

## <a name="to-create-a-certificate-request-for-the-external-interface-of-the-edge-server-to-support-public-im-connectivity-with-aol"></a>为边缘服务器的外部接口创建证书请求以支持与 AOL 的公共 IM 连接

1.  如果所需模板可供 CA 使用，请使用以下 Windows PowerShell cmdlet 在边缘服务器上请求证书：
    
        Request-CsCertificate -New -Type AccessEdgeExternal  -Output C:\ <certfilename.txt or certfilename.csr>  -ClientEku $true -Template <template name>
    
    用于 Lync Server 的模板的默认证书名称是 Web 服务器。 仅 \<template name\> 当需要使用与默认模板不同的模板时才指定。
    
    <div>
    

    > [!IMPORTANT]  
    > 如果您的组织想要支持与 AOL 的公共 IM 连接，则必须使用 Windows PowerShell 而不是证书向导请求将证书分配给访问边缘服务的外部边缘。 这是因为证书向导用于请求证书的证书颁发机构 (CA) Web 服务器模板不支持客户端 EKU 配置。 在使用 Windows PowerShell 创建证书之前，CA 管理员必须创建和部署支持客户端 EKU 的新模板。

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

