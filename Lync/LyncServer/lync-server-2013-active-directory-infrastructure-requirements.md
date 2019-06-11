---
title: Lync Server 2013：Active Directory 基础结构要求
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Active Directory infrastructure requirements
ms:assetid: c2086f7b-662f-4179-ab99-2c0311ebd903
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412955(v=OCS.15)
ms:contentKeyID: 48185318
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2c583fd751bf70814f9aa2fae5f6cfe08bec0202
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34837959"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="active-directory-infrastructure-requirements-for-lync-server-2013"></a>Lync Server 2013 的 Active Directory 基础结构要求

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2013-11-07_

开始为 Lync Server 2013 准备 Active Directory 域服务的过程之前, 请确保你的 Active Directory 基础结构满足以下先决条件:

  - 您在其中部署 Lync 服务器的林中的所有域控制器 (包括所有全局编录服务器) 都运行下列操作系统之一:
    
      - Windows Server 2012 R2 操作系统
    
      - Windows Server 2012 操作系统
    
      - Windows Server 2008 R2 操作系统
    
      - Windows Server 2008 操作系统
    
      - Windows Server 2008 企业版32位
    
      - 32位或64位版本的 Windows Server 2003 R2 操作系统
    
      - 32位或64位版本的 Windows Server 2003 操作系统

  - 将在其中部署 Lync Server 的所有域都将提升为 Windows Server 2012 R2、Windows Server 2012、Windows Server 2008 R2、Windows Server 2008 或至少 Windows Server 2003 的域功能级别。

  - 将 Lync Server 部署到的林将提升为 Windows Server 2012 R2、Windows Server 2012、Windows Server 2008 R2、Windows Server 2008 或至少 Windows Server 2003 的林功能级别。
    
    <div>
    

    > [!NOTE]  
    > 若要更改域或林功能级别, 请参阅 TechNet 库中的 "提升域和林功能级别" <A href="http://go.microsoft.com/fwlink/p/?linkid=263775">http://go.microsoft.com/fwlink/p/?LinkId=263775</A>。

    
    </div>

  - 全局编录在每个部署 Lync Server 计算机或用户的域中部署。

Lync Server 2013 支持 Windows Server 2012 R2、Windows Server 2012、Windows Server 2008 R2、Windows Server 2008 和 Windows Server 2003 操作系统中的通用组。 通用组的成员可包括域树或林中的任何域中的其他组和帐户，并且可将域树或林中的任何域中的权限分配给这些成员。 通用组支持, 与管理员委派结合使用, 简化了 Lync 服务器部署的管理。 例如，不必将一个域添加到另一个域，管理员即可同时管理这两个域。

</div>

<span> </span>

</div>

</div>

</div>

