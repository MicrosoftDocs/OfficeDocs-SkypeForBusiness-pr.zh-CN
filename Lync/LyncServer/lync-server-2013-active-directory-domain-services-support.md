---
title: Lync Server 2013： Active Directory 域服务支持
description: Lync Server 2013： Active Directory 域服务支持。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Active Directory Domain Services support
ms:assetid: aeb62d5e-e424-473a-b795-9452150c98dd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412831(v=OCS.15)
ms:contentKeyID: 48185136
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bb2a85bab90557c28c4802721d4202f6188cb3f1
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48558678"
---
# <a name="active-directory-domain-services-support-in-lync-server-2013"></a>Lync Server 2013 中的 Active Directory 域服务支持

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2013-11-07_

Lync Server 2013 使用中央管理存储来存储服务器和服务的配置数据，而不是依靠 Active Directory 域服务获取此信息，如过去所述。 Lync Server 2013 仍在 AD DS 中存储以下内容：

  - **架构扩展**
    
      - 用户对象扩展
    
      - Lync Server 2010 和 Office 通信服务器 2007 R2 类的扩展，以保持与以前支持的版本的向后兼容性

  - 存储在 Lync Server 2013 扩展架构和现有类中的**数据** () 
    
      - 用户 SIP URI 和其他用户设置
    
      - 应用程序的 Contact 对象 (例如，响应组应用程序和会议助理应用程序) 
    
      - 为实现向后兼容而发布的数据
    
      - 对中央管理存储 (SCP) 的服务控制点
    
      - Kerberos 身份验证帐户（可选计算机对象）

本节介绍 Lync Server 2013 的 AD DS 支持要求。 有关拓扑支持的详细信息，请参阅可支持性文档中的 [Lync Server 2013 中的受支持的 Active Directory 拓扑](lync-server-2013-supported-active-directory-topologies.md) 。

<div>

## <a name="supported-domain-controller-operating-systems"></a>支持的域控制器操作系统

Lync Server 2013 支持运行以下操作系统的域控制器：

  - Windows Server 2012 R2 操作系统

  - Windows Server 2012 操作系统

  - Windows Server 2008 R2 操作系统

  - Windows Server 2008 操作系统

  - Windows Server 2008 企业版32位

  - 32 位或 64 位版本的 Window Server 2003 R2 操作系统

  - 32位或64位版本的 Windows Server 2003 操作系统

</div>

<div>

## <a name="forest-and-domain-functional-level"></a>林和域功能级别

您必须将您将 Lync Server 2013 部署到 Windows Server 2012 R2、Windows Server 2012、Windows Server 2008 R2、Windows Server 2008 或至少为 Windows Server 2003 的域功能级别的所有域进行提升。

必须将部署 Lync Server 2013 的所有林都提升为 Windows Server 2012 R2、Windows Server 2012、Windows Server 2008 R2、Windows Server 2008 或至少为 Windows Server 2003 的林功能级别。

</div>

<div>

## <a name="support-for-read-only-domain-controllers"></a>对只读域控制器的支持

Lync Server 2013 支持包含只读域控制器或只读全局编录服务器的 Active Directory 域服务部署（只要有可写域控制器可用）。

</div>

<div>

## <a name="domain-names"></a>域名

Lync Server 不支持单标签域。 例如，支持具有名为 **contoso.local** 的根域的林，但不支持名为 **local** 的根域。 有关详细信息，请参阅 Microsoft 知识库文章 300684 "有关为带有单标签 DNS 名称的域配置 Windows 的信息" [https://go.microsoft.com/fwlink/p/?linkId=143752](https://go.microsoft.com/fwlink/p/?linkid=143752) 。

<div>


> [!NOTE]  
> Lync Server 不支持对域进行重命名。 如果需要重命名已在其中部署 Lync Server 的域，则需要先卸载 Lync Server，再重命名域，然后重新安装 Lync Server。



</div>

</div>

<div>

## <a name="locked-down-adds-environments"></a>锁定的 AD DS 环境

在锁定的 AD DS 环境中，通常将用户对象和计算机对象放置在禁用了权限继承的特定组织单位 (OU) 中，以帮助确保管理委派的安全以及允许使用组策略对象 (GPO) 实施安全策略。 可以在锁定的 Active Directory 环境中部署 Lync Server 2013。 有关在锁定环境中部署 Lync Server 所需的内容的详细信息，请参阅部署文档中的在 [Lync server 2013 中准备锁定的 Active Directory 域服务](lync-server-2013-preparing-a-locked-down-active-directory-domain-services.md) 。

</div>

</div>

<span> </span>

</div>

</div>

</div>

