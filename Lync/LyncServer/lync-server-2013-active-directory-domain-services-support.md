---
title: Lync Server 2013：Active Directory 域服务支持
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
ms.openlocfilehash: 32e1bce2546512900efb0b5ecd1256a97adde41e
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41737012"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="active-directory-domain-services-support-in-lync-server-2013"></a>Lync Server 2013 中的 Active Directory 域服务支持

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2013-11-07_

Lync Server 2013 使用中央管理存储来存储服务器和服务的配置数据，而不是依赖于 Active Directory 域服务处理此信息，就像过去一样。 Lync Server 2013 仍在 AD DS 中存储以下内容：

  - **架构扩展**
    
      - 用户对象扩展
    
      - Lync Server 2010 和 Office 通信服务器 2007 R2 类的扩展，可保持与以前支持的版本的向后兼容性

  - **数据**（存储在 Lync Server 2013 扩展架构和现有类中）
    
      - 用户 SIP URI 和其他用户设置
    
      - 应用程序的联系人对象（例如，"响应组" 应用程序和 "会议助理" 应用程序）
    
      - 为实现向后兼容而发布的数据
    
      - 中央管理存储的服务控制点 (SCP)
    
      - Kerberos 身份验证帐户（可选计算机对象）

本部分介绍 Lync Server 2013 的 AD DS 支持要求。 有关拓扑支持的详细信息，请参阅支持文档中的[Lync Server 2013 中支持的 Active Directory 拓扑](lync-server-2013-supported-active-directory-topologies.md)。

<div>

## <a name="supported-domain-controller-operating-systems"></a>支持的域控制器操作系统

Lync Server 2013 支持运行以下操作系统的域控制器：

  - Windows Server 2012 R2 操作系统

  - Windows Server 2012 操作系统

  - Windows Server 2008 R2 操作系统

  - Windows Server 2008 操作系统

  - Windows Server 2008 企业版32位

  - 32位或64位版本的窗口服务器 2003 R2 操作系统

  - 32位或64位版本的 Windows Server 2003 操作系统

</div>

<div>

## <a name="forest-and-domain-functional-level"></a>林和域功能级别

你必须将 Lync Server 2013 部署到的所有域都提升为 Windows Server 2012 R2、Windows Server 2012、Windows Server 2008 R2、Windows Server 2008 或 Windows Server 2003 至少的域功能级别。

必须将部署 Lync Server 2013 的所有林都提升为 Windows Server 2012 R2、Windows Server 2012、Windows Server 2008 R2、Windows Server 2008 或至少 Windows Server 2003 的林功能级别。

</div>

<div>

## <a name="support-for-read-only-domain-controllers"></a>对只读域控制器的支持

Lync Server 2013 支持包含只读域控制器或只读全局编录服务器的 Active Directory 域服务部署（只要有可写域控制器可用）。

</div>

<div>

## <a name="domain-names"></a>域名

Lync 服务器不支持单标记的域。 例如，支持一个名为 " **contoso. local** " 的根域的林，但不支持名为**local**的根域。 有关详细信息，请参阅 Microsoft 知识库文章 300684 "有关为具有单标签 DNS 名称的域配置 Windows 的信息" [http://go.microsoft.com/fwlink/p/?linkId=143752](http://go.microsoft.com/fwlink/p/?linkid=143752)。

<div>


> [!NOTE]  
> Lync Server 不支持重命名域。 如果需要重命名 Lync Server 部署到的域，你需要先卸载 Lync Server，然后重命名域，然后重新安装 Lync Server。



</div>

</div>

<div>

## <a name="locked-down-adds-environments"></a>锁定的 AD DS 环境

在锁定的 AD DS 环境中，用户和计算机对象通常放置在具有权限继承的特定组织单位（Ou）中，以帮助保护管理委派和允许使用组策略对象（Gpo）实施安全策略。 可以在锁定的活动目录环境中部署 Lync Server 2013。 有关在锁定环境中部署 Lync Server 所需内容的详细信息，请参阅部署文档中的[在 Lync server 2013 中准备锁定的 Active Directory 域服务](lync-server-2013-preparing-a-locked-down-active-directory-domain-services.md)。

</div>

</div>

<span> </span>

</div>

</div>

</div>

