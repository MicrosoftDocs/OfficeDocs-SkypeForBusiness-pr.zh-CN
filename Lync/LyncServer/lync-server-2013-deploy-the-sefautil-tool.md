---
title: Lync Server 2013：部署 SEFAUtil 工具
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploy the SEFAUtil tool
ms:assetid: fb556e50-88dd-4404-a3d5-be36f5ba41e6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945659(v=OCS.15)
ms:contentKeyID: 51541534
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dcd995a99514fa54a221e17f1ea556565cbebdcb
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41729612"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploy-the-sefautil-tool-in-lync-server-2013"></a>Deploy the SEFAUtil tool in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2013-01-30_

若要部署和管理组呼叫装货，需要使用 SEFAUtil 资源工具包工具。 该工具是 Lync Server 2013 资源工具包工具的一部分。 在安装 SEFAUtil 之前，你必须在拓扑中拥有受信任的应用程序池，将 SEFAUtil 指定为受信任的应用程序，并启用拓扑。

<div>


> [!IMPORTANT]  
> Microsoft 统一通信托管 API (UCMA) 3.0 核心 SDK 必须安装在您计划运行 SEFAUtil 工具的任何计算机上。



</div>

你可以在部署中的任何前端池中运行 SEFAUtil。

<div>


> [!NOTE]  
> 有关运行 SEFAUtil 的更多详细信息，请参阅 Technet 博客文章 "如何获取 SEFAutil 运行？" <A href="http://go.microsoft.com/fwlink/?linkid=278940">http://go.microsoft.com/fwlink/?LinkId=278940</A>。



</div>

<div>

## <a name="to-deploy-sefautil"></a>部署 SEFAUtil

1.  以 RTCUniversalServerAdmins 组成员的身份或必要的用户权限登录到安装了 Lync Server 管理外壳的计算机，如在[Lync Server 2013 中的 "委派设置权限](lync-server-2013-delegate-setup-permissions.md)" 中所述。

2.  启动 Lync Server 命令行管理程序：依次单击 "**开始**"、"**所有程序**"、" **Microsoft Lync server 2013**"，然后单击 " **Lync server Management shell**"。

3.  SEFAUtil 工具只能在属于受信任应用程序池的一部分的计算机上运行。 如果需要，请为计划运行 SEFAUtil 的前端池定义受信任的应用程序池。 在命令行中运行：
    
        New-CsTrustedApplicationPool -id <Pool FQDN> -Registrar <Pool Registrar FQDN> -site Site:<Pool Site>

4.  将 SEFAUtil 工具定义为受信任应用程序。在命令行中运行：
    
        New-CsTrustedApplication -ApplicationId sefautil -TrustedApplicationPoolFqdn <Pool FQDN>  -Port 7489
    
    <div>
    

    > [!NOTE]  
    > 如有需要，您可以使用其他端口。

    
    </div>

5.  启用包含您的更改的拓扑。在命令行中运行：
    
        Enable-CsTopology

6.  在您在步骤3中创建的受信任的应用程序池中的前端服务器上安装 Lync Server 2013 资源工具包工具。

7.  验证 SEFAUtil 工具是否正常运行，如下所示：
    
    1.  使用管理员权限从 Windows 命令提示符处运行该工具以在您的部署中显示用户的呼叫转接设置。
        
        <div>
        

        > [!NOTE]  
        > 该工具位于 \Program Files\Microsoft Lync Server 2013 \ Reskit。

        
        </div>
    
    2.  显示用户的呼叫转接设置。在命令行中运行：
        
            SEFAUtil.exe <user SIP address> /server:<Lync Server/Pool FQDN>
        
        将显示用户的呼叫转接设置。

</div>

</div>

<span> </span>

</div>

</div>

</div>

