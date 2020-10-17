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
# <a name="re-activate-server-after-security-configuration-wizard-closes-ports-in-iis"></a><span data-ttu-id="0e5e7-102">安全配置向导在 IIS 中关闭端口后重新激活服务器</span><span class="sxs-lookup"><span data-stu-id="0e5e7-102">Re-activate server after Security Configuration Wizard closes ports in IIS</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0e5e7-103">_**上次修改的主题：** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="0e5e7-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="0e5e7-104">某些 Lync Server 2013 角色在 Internet 信息服务上运行 Web 服务 (IIS) 端口4443。</span><span class="sxs-lookup"><span data-stu-id="0e5e7-104">Some Lync Server 2013 roles run Web Services on Internet Information Services (IIS) port 4443.</span></span> <span data-ttu-id="0e5e7-105">运行 Lync Server 部署向导、Bootstrapper.exe 或使用 **CsComputer** cmdlet 会在防火墙中创建一个例外，并打开该端口。</span><span class="sxs-lookup"><span data-stu-id="0e5e7-105">Running the Lync Server Deployment Wizard, Bootstrapper.exe, or using the **Enable-CsComputer** cmdlet creates an exception in the firewall and opens the port.</span></span> <span data-ttu-id="0e5e7-106">如果随后运行 Windows Server 2008 R2 安全配置向导 (或其他强化脚本) ，端口4443将被阻止，并且外部客户端将无法联系 Web 服务。</span><span class="sxs-lookup"><span data-stu-id="0e5e7-106">If you then run the Windows Server 2008 R2 Security Configuration Wizard (or other hardening scripts), port 4443 will be blocked, and external clients will not be able to contact Web Services.</span></span> <span data-ttu-id="0e5e7-107">要重新打开该端口，可以直接修改防火墙例外，也可以重新激活服务器。</span><span class="sxs-lookup"><span data-stu-id="0e5e7-107">To reopen the port you can either modify the firewall exception directly or re-activate the server.</span></span>

<div>

## <a name="to-re-activate-the-server-by-using-the-deployment-wizard"></a><span data-ttu-id="0e5e7-108">通过使用部署向导重新激活服务器</span><span class="sxs-lookup"><span data-stu-id="0e5e7-108">To re-activate the server by using the Deployment Wizard</span></span>

1.  <span data-ttu-id="0e5e7-109">在 "Lync Server 部署向导" 页上，单击 "**步骤2：安装或删除 Lync Server 组件**" 旁边的 "**运行**"。</span><span class="sxs-lookup"><span data-stu-id="0e5e7-109">On the Lync Server Deployment Wizard page, click **Run** next to **Step 2: Setup or Remove Lync Server Components**.</span></span>

2.  <span data-ttu-id="0e5e7-110">在“设置 Lync Server 组件”\*\*\*\* 页上，单击“下一步”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="0e5e7-110">On **Setup Lync Server components** page, click **Next**.</span></span>

3.  <span data-ttu-id="0e5e7-111">在“正在执行命令”\*\*\*\* 页上，任务状态显示为已完成时，单击“完成”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="0e5e7-111">On the **Executing Commands** page, when the task status is shown as completed, click **Finish**.</span></span>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="0e5e7-112">还可以使用 bootstrapper.exe 或 <STRONG>Enable-CsComputer</STRONG> 来重新激活服务器。</span><span class="sxs-lookup"><span data-stu-id="0e5e7-112">You can also use bootstrapper.exe or <STRONG>Enable-CsComputer</STRONG> to re-activate the server.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

