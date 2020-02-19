---
title: Lync Server 2013：使用 cmdlet 还原域准备
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Using cmdlets to reverse domain preparation
ms:assetid: 014dba5d-fcb3-44c9-9d63-ae0755276dac
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398071(v=OCS.15)
ms:contentKeyID: 48183227
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c1d1f2bd6d285e57c1db9bdac756685d3c24bd1b
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42138733"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="using-cmdlets-to-reverse-domain-preparation-for-lync-server-2013"></a>使用 cmdlet 对 Lync Server 2013 执行反向域准备

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-10-29_

使用 **Disable-CsAdDomain** cmdlet 可反向执行域准备步骤。

<div>

## <a name="to-use-cmdlets-to-reverse-domain-preparation"></a>使用 cmdlet 反向执行域准备

1.  以 Domain Admins 组成员的身份登录域中的任何服务器。

2.  启动 Lync Server 命令行管理程序：依次单击“开始”****、“所有程序”****、“Microsoft Lync Server 2013”**** 和“Lync Server 命令行管理程序”****。

3.  以
    
        Disable-CsAdDomain [-Domain <Fqdn>] [-DomainController <Fqdn>] [-Force <SwitchParameter>] 
        [-GlobalCatalog <Fqdn>] [-GlobalSettingsDomainController <Fqdn>] 
    
    例如：
    
        Disable-CsAdDomain -Domain domain1.contoso.net -GlobalSettingsDomainController dc01.domain1.contoso.net -Force
    
    如果 Force 参数存在，即使激活了域中的一个或多个前端服务器或 A/V 会议服务器，也会回滚域准备。 如果 Force 参数不存在，则在域中的任何前端服务器或 A/V 会议服务器处于激活状态时，将终止域准备回滚。
    
    <div>
    

    > [!NOTE]  
    > 参数 GlobalSettingsDomainController 用于指出存储全局设置的位置。 如果设置存储在“系统”容器中（通常在全局设置尚未迁移到“配置”容器的升级部署中是这种情况），则定义 Active Directory 林的根中的某个域控制器。 如果全局设置存储在“配置”容器中（通常在新部署或设置已迁移到“配置”容器的升级部署中是这种情况），则定义林中的任何域控制器。 如果不指定此参数，则 cmdlet 假定设置存储在配置容器中，并引用 AD&nbsp;DS 中的任何域控制器。

    
    </div>

</div>

<div>

## <a name="see-also"></a>另请参阅


[为 Lync Server 2013 运行域准备](lync-server-2013-running-domain-preparation.md)  


[准备 Lync Server 2013 的域](lync-server-2013-preparing-domains.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

