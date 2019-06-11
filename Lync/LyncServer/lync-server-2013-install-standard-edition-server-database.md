---
title: Lync Server 2013：安装 Standard Edition 服务器数据库
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Install Standard Edition server database
ms:assetid: 0bd3a804-aad6-48cb-981b-54725af032db
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398167(v=OCS.15)
ms:contentKeyID: 48183385
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5cad6f67dbf1bfff1ee16dbd7455b02d904aac0d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34830000"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="install-standard-edition-server-database-for-lync-server-2013"></a>安装适用于 Lync Server 2013 的 Standard Edition 服务器数据库

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2012-10-01_

将标准版服务器设置为基础结构中的唯一服务器, 以使家庭用户与其他服务器安装不同, 因为**部署向导**中有专门用于设置初始服务器的选择。

<div>

## <a name="to-install-a-standard-edition-server"></a>安装标准版服务器

1.  登录到要将标准版服务器安装为本地管理员或等效域的服务器。

2.  如果尚未准备好 Active Directory 域服务, 则首先执行这些过程。 有关详细信息, 请参阅[准备适用于 Lync Server 2013 的 Active Directory 域服务](lync-server-2013-preparing-active-directory-domain-services.md)。

3.  在 Lync Server 部署向导中, 单击 "**准备第一个标准版服务器**"。

4.  在 "**准备单个标准版服务器**" 页面上, 单击 "**下一步**"。

5.  在 "**执行命令**" 页面上, SQL Server 2012 Express 作为中央管理存储进行安装。 已创建必要的防火墙规则。 当数据库和必备软件的安装完成后, 单击 "**完成**"。
    
    <div>
    

    > [!NOTE]  
    > 初始安装可能需要一些时间, 但不显示命令输出摘要屏幕的更新。 这是由于 SQL Server Express 的安装所致。 如果需要监视数据库的安装, 请使用 "任务管理器" 监视设置。

    
    </div>

6.  在 "Lync Server 部署向导" 页面上, 如果之前尚未安装 "管理工具", 请单击 "**安装拓扑生成器**"。 有关详细信息, 请参阅[安装 Lync Server 2013 管理工具](lync-server-2013-install-lync-server-administrative-tools.md)。

7.  确认 "准备 Active Directory"、"准备第一个标准版服务器" 和 "安装拓扑生成器" 旁边有绿色复选标记。

</div>

</div>

<span> </span>

</div>

</div>

</div>

