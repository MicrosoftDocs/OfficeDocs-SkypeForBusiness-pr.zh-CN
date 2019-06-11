---
title: Lync Server 2013：设置公共即时消息连接
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Setting up public instant messaging connectivity
ms:assetid: 816dea2a-96fa-4a36-b6c2-a9402675868b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205041(v=OCS.15)
ms:contentKeyID: 48184661
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1e77d8914a1f55ac10544591913a7347e271e9de
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34845909"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="setting-up-public-instant-messaging-connectivity-in-lync-server-2013"></a>在 Lync Server 2013 中设置公共即时消息连接

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2012-09-08_

如果您的组织希望支持使用 AOL 的公共即时消息 (IM) 连接, 则不能使用 Lync Server 部署向导申请证书。 请改为执行以下过程中的步骤。

<div>

## <a name="setting-up-public-instant-messaging-connectivity"></a>设置公共即时消息连接

1.  在前端服务器上, 打开拓扑生成器。 展开 "边缘池", 然后右键单击 "边缘服务器" 或 "边缘服务器" 池。 选择 "编辑属性"。

2.  在 "常规" 下的 "编辑属性" 下, 选择 "为此边缘池启用联盟 (端口 5061)"。 单击“确定”。

3.  单击 "操作", 选择 "拓扑", 选择 "发布"。 当系统提示发布拓扑时, 单击 "下一步"。 发布完成后, 单击 "完成"。

4.  在边缘服务器上, 打开 "Lync Server 部署向导"。 单击 "安装或更新 Lync 服务器系统", 然后单击 "设置" 或 "删除 Lync Server 组件"。 再次单击 "运行"。

5.  在 "安装 Lync 服务器组件" 中, 单击 "下一步"。 "摘要" 屏幕将显示执行时的操作。 部署完成后, 单击 "查看日志" 以查看可用的日志文件。 单击 "完成" 以完成部署。

</div>

<div>

## <a name="to-create-a-certificate-request-for-the-external-interface-of-the-edge-server-to-support-public-im-connectivity-with-aol"></a>为边缘服务器的外部接口创建证书请求以支持与 AOL 的公共 IM 连接

1.  当所需模板可供 CA 使用时, 请从 Edge 服务器使用以下 Windows PowerShell cmdlet 来申请证书
    
        Request-CsCertificate -New -Type AccessEdgeExternal  -Output C:\ <certfilename.txt or certfilename.csr>  -ClientEku $true -Template <template name>
    
    Lync Server 使用的模板的默认证书名称是 Web 服务器。 仅当需要\<使用不同\>于默认模板的模板时, 才指定模板名称。
    
    <div>
    

    > [!IMPORTANT]  
    > 如果你的组织希望支持与 AOL 的公共 IM 连接, 你必须使用 Windows PowerShell 而不是证书向导请求将证书分配给访问边缘服务的外部边缘。 这是因为证书向导用于申请证书的证书颁发机构 (CA) Web 服务器模板不支持客户端 EKU 配置。 在使用 Windows PowerShell 创建证书之前, CA 管理员必须创建和部署支持客户端 EKU 的新模板。

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

