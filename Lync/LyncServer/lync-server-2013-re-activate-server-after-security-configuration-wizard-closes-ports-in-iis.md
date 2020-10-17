---
title: 安全配置向导在 IIS 中关闭端口后重新激活服务器
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Re-activate server after Security Configuration Wizard closes ports in IIS
ms:assetid: cb8e17cf-f8c1-4099-b63b-c242d656c26a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398851(v=OCS.15)
ms:contentKeyID: 48185644
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0a72bfcf9facfeaa3ca943275d9cdcb3b1ac7705
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48512039"
---
# <a name="re-activate-server-after-security-configuration-wizard-closes-ports-in-iis"></a>安全配置向导在 IIS 中关闭端口后重新激活服务器

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-10-01_

某些 Lync Server 2013 角色在 Internet 信息服务上运行 Web 服务 (IIS) 端口4443。 运行 Lync Server 部署向导、Bootstrapper.exe 或使用 **CsComputer** cmdlet 会在防火墙中创建一个例外，并打开该端口。 如果随后运行 Windows Server 2008 R2 安全配置向导 (或其他强化脚本) ，端口4443将被阻止，并且外部客户端将无法联系 Web 服务。 要重新打开该端口，可以直接修改防火墙例外，也可以重新激活服务器。

<div>

## <a name="to-re-activate-the-server-by-using-the-deployment-wizard"></a>通过使用部署向导重新激活服务器

1.  在 "Lync Server 部署向导" 页上，单击 "**步骤2：安装或删除 Lync Server 组件**" 旁边的 "**运行**"。

2.  在“设置 Lync Server 组件”**** 页上，单击“下一步”****。

3.  在“正在执行命令”**** 页上，任务状态显示为已完成时，单击“完成”****。
    
    <div>
    

    > [!NOTE]
    > 还可以使用 bootstrapper.exe 或 <STRONG>Enable-CsComputer</STRONG> 来重新激活服务器。

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

