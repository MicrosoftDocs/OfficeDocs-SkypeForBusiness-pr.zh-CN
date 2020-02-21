---
title: Lync Server 2013：安装 Standard Edition server database
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Install Standard Edition server database
ms:assetid: 0bd3a804-aad6-48cb-981b-54725af032db
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398167(v=OCS.15)
ms:contentKeyID: 48183385
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 877a9b8519c6c0e8b0c3e4a92d190f5a55d8861e
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "42197115"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="install-standard-edition-server-database-for-lync-server-2013"></a>安装适用于 Lync Server 2013 的 Standard Edition 服务器数据库

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-10-01_

将 Standard Edition 服务器设置为基础结构中的唯一服务器，让家庭用户与其他服务器安装不同，因为**部署向导**中有专门用于设置初始服务器的选择。

<div>

## <a name="to-install-a-standard-edition-server"></a>安装 Standard Edition Server

1.  登录到要将 Standard Edition server 安装为本地管理员或等效域的服务器。

2.  如果尚未准备好 Active Directory 域服务，则先执行这些过程。 有关详细信息，请参阅[为 Lync Server 2013 准备 Active Directory 域服务](lync-server-2013-preparing-active-directory-domain-services.md)。

3.  在 "Lync Server 部署向导" 中，单击 "**准备第一个 Standard Edition Server**"。

4.  在“准备单个 Standard Edition Server”**** 页上，单击“下一步”****。

5.  在 "**正在执行命令**" 页上，SQL Server 2012 Express 安装为中央管理存储。 创建必需的防火墙规则。 安装数据库和必备软件后，单击“完成”****。
    
    <div>
    

    > [!NOTE]  
    > 初始安装可能要花费一些时间，这期间命令输出摘要屏幕上不显示更新。 这是因为安装了 SQL Server Express。 如果需要监视数据库安装，请使用任务管理器监视安装过程。

    
    </div>

6.  在 "Lync Server 部署向导" 页上，单击 "**安装拓扑生成器**" （如果以前未安装过管理工具）。 有关详细信息，请参阅[Install Lync Server 2013 管理工具](lync-server-2013-install-lync-server-administrative-tools.md)。

7.  确认“准备 Active Directory”、“准备第一个 Standard Edition Server”和“安装拓扑生成器”旁边有绿色复选标记。

</div>

</div>

<span> </span>

</div>

</div>

</div>

