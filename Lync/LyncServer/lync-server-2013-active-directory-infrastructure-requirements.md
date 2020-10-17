---
title: Lync Server 2013： Active Directory 基础结构要求
description: Lync Server 2013： Active Directory 基础结构要求。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Active Directory infrastructure requirements
ms:assetid: c2086f7b-662f-4179-ab99-2c0311ebd903
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412955(v=OCS.15)
ms:contentKeyID: 48185318
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 62218605c9b3fac20743d0b6bb475515c9498f9a
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48552358"
---
# <a name="active-directory-infrastructure-requirements-for-lync-server-2013"></a>Lync Server 2013 的 Active Directory 基础结构要求

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2013-11-07_

在开始为 Lync Server 2013 准备 Active Directory 域服务的过程之前，请确保您的 Active Directory 基础结构满足以下先决条件：

  - 所有域控制器 (包括在其中部署 Lync Server 的林中) 所有全局编录服务器运行以下操作系统之一：
    
      - Windows Server 2012 R2 操作系统
    
      - Windows Server 2012 操作系统
    
      - Windows Server 2008 R2 操作系统
    
      - Windows Server 2008 操作系统
    
      - Windows Server 2008 企业版32位
    
      - 32 位或 64 位版本的 Windows Server 2003 R2 操作系统
    
      - 32位或64位版本的 Windows Server 2003 操作系统

  - 将在其中部署 Lync Server 的所有域都将提升为 Windows Server 2012 R2、Windows Server 2012、Windows Server 2008 R2、Windows Server 2008 或至少为 Windows Server 2003 的域功能级别。

  - 将在其中部署 Lync Server 的林提升为 Windows Server 2012 R2、Windows Server 2012、Windows Server 2008 R2、Windows Server 2008 或至少为 Windows Server 2003 的林功能级别。
    
    <div>
    

    > [!NOTE]  
    > 若要更改您的域或林功能级别，请参阅 TechNet Library 中的 "提升域和林功能级别" <A href="https://go.microsoft.com/fwlink/p/?linkid=263775">https://go.microsoft.com/fwlink/p/?LinkId=263775</A> 。

    
    </div>

  - 在部署 Lync Server 计算机或用户的每个域中都会部署一个全局编录。

Lync Server 2013 支持 Windows Server 2012 R2、Windows Server 2012、Windows Server 2008 R2、Windows Server 2008 和 Windows Server 2003 操作系统中的通用组。 通用组的成员可包括域树或林中的任何域中的其他组和帐户，并且可将域树或林中的任何域中的权限分配给这些成员。 通用组支持（与管理员委派结合使用）简化了 Lync Server 部署的管理。 例如，不必将一个域添加到另一个域，管理员即可同时管理这两个域。

</div>

<span> </span>

</div>

</div>

</div>

