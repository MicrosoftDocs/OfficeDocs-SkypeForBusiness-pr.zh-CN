---
title: 使用安全配置向导在 IIS 中关闭端口后重新激活服务器
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Re-activate server after Security Configuration Wizard closes ports in IIS
ms:assetid: cb8e17cf-f8c1-4099-b63b-c242d656c26a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398851(v=OCS.15)
ms:contentKeyID: 48185644
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9c939996c10c85141d3c3751ce84b0cf642007b9
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34823607"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="re-activate-server-after-security-configuration-wizard-closes-ports-in-iis"></a>使用安全配置向导在 IIS 中关闭端口后重新激活服务器

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2012-10-01_

某些 Lync Server 2013 角色在 Internet Information Services (IIS) 端口4443上运行 Web 服务。 运行 Lync Server 部署向导、setup.exe 或使用**Enable-CsComputer** cmdlet 会在防火墙中创建一个例外, 并打开该端口。 如果您随后运行 Windows Server 2008 R2 安全配置向导 (或其他强化脚本), 则将阻止端口 4443, 并且外部客户端将无法联系 Web 服务。 若要重新打开该端口, 可以直接修改防火墙例外或重新激活服务器。

<div>

## <a name="to-re-activate-the-server-by-using-the-deployment-wizard"></a>使用部署向导重新激活服务器

1.  在 "Lync Server 部署向导" 页面上, 单击**步骤 2: 设置或删除 Lync Server 组件**旁边的 "**运行**"。

2.  在 "**安装 Lync 服务器组件**" 页面上, 单击 "**下一步**"。

3.  在 "**执行命令**" 页面上, 当 "任务状态" 显示为 "已完成" 时, 单击 "**完成**"。
    
    <div>
    

    > [!NOTE]
    > 您也可以使用<STRONG>CsComputer 或 Enable-</STRONG>重新激活服务器。

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

