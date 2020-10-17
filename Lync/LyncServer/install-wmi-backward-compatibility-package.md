---
title: 安装 WMI 向后兼容包
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Install WMI Backward Compatibility package
ms:assetid: 38797fbd-06a0-4008-b099-158e7b5d7703
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204816(v=OCS.15)
ms:contentKeyID: 48183893
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 655d72b2362c6b31d6fc15fd3af0ec14716b13c4
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48523359"
---
# <a name="install-wmi-backward-compatibility-package"></a><span data-ttu-id="dbe93-102">安装 WMI 向后兼容包</span><span class="sxs-lookup"><span data-stu-id="dbe93-102">Install WMI Backward Compatibility package</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="dbe93-103">_**上次修改的主题：** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="dbe93-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="dbe93-104">如果试图在没有安装 WMI 向后兼容包的情况下运行拓扑生成器合并向导，将会出现以下错误：</span><span class="sxs-lookup"><span data-stu-id="dbe93-104">If you attempt to run the Topology Builder Merge wizard without installing the WMI Backward Compatibility package, you will see the following error:</span></span>

<span data-ttu-id="dbe93-105">![WMI 错误消息](images/JJ204816.a007d2f2-fc85-430c-91eb-382b032469af(OCS.15).jpg "WMI 错误消息")</span><span class="sxs-lookup"><span data-stu-id="dbe93-105">![WMI error message](images/JJ204816.a007d2f2-fc85-430c-91eb-382b032469af(OCS.15).jpg "WMI error message")</span></span>

<span data-ttu-id="dbe93-106">如果试图在没有安装 WMI 向后兼容包的情况下运行 **Merge-CsLegacytopology** cmdlet，将会出现以下错误：</span><span class="sxs-lookup"><span data-stu-id="dbe93-106">If you attempt to run the **Merge-CsLegacytopology** cmdlet without installing the WMI Backward Compatibility package, you will see the following error:</span></span>

<span data-ttu-id="dbe93-107">![Windows PowerShell WMI 提供程序错误](images/JJ204816.c510824e-1807-4c7e-bb28-c6cfea2eac1d(OCS.15).jpg "Windows PowerShell WMI 提供程序错误")</span><span class="sxs-lookup"><span data-stu-id="dbe93-107">![Windows PowerShell WMI Provider Error](images/JJ204816.c510824e-1807-4c7e-bb28-c6cfea2eac1d(OCS.15).jpg "Windows PowerShell WMI Provider Error")</span></span>

<span data-ttu-id="dbe93-108">安装 WMI 向后兼容包</span><span class="sxs-lookup"><span data-stu-id="dbe93-108">To install the WMI Backward Compatibility Package</span></span>

1.  <span data-ttu-id="dbe93-109">从安装媒体中，导航到 " \\ 安装 \\ AMD64 安装程序" \\ \\OCSWMIBC.MSI。</span><span class="sxs-lookup"><span data-stu-id="dbe93-109">From your installation media, navigate to \\SETUP\\AMD64\\SETUP\\OCSWMIBC.MSI.</span></span>

2.  <span data-ttu-id="dbe93-110">安装 OCSWMIBC.MSI。</span><span class="sxs-lookup"><span data-stu-id="dbe93-110">Install OCSWMIBC.MSI.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="dbe93-p101">OCSWMIBC.msi 必须安装在运行拓扑生成器合并向导的计算机上。不过，建议将 OCSWMIBC.msi 安装在拓扑中的所有前端服务器上。</span><span class="sxs-lookup"><span data-stu-id="dbe93-p101">OCSWMIBC.msi must be installed on the computer where the Topology Builder Merge wizard is run. However, we recommend installing OCSWMIBC.msi on all Front End servers in your topology.</span></span>

    
    </div>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="dbe93-113">可以在安装了 Lync Server 2013 Core 组件和 Lync Server 2013 命令行管理程序的域中的任何计算机上安装 OCSWMIBC.msi，并能够访问 Active Directory 域服务 (AD DS) 和 SQL Server) 中的 Office 通信服务器 2007 R2 拓扑 (WMI 提供程序。</span><span class="sxs-lookup"><span data-stu-id="dbe93-113">OCSWMIBC.msi can be installed on any computer in the domain that has the Lync Server 2013 Core Components and the Lync Server 2013 Management Shell installed, and has access to the Office Communications Server 2007 R2 topology (WMI provider to Active Directory Domain Services (AD DS) and SQL Server).</span></span>

    
    </div>

</div>

<span> </span>

</div>

</div>

</div>

