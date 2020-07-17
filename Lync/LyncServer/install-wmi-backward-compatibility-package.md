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
ms.openlocfilehash: 35be17aa08cf26f93a9d4002b23dacdfb35c5143
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/16/2020
ms.locfileid: "44756591"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="install-wmi-backward-compatibility-package"></a>安装 WMI 向后兼容包

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-10-02_

如果试图在没有安装 WMI 向后兼容包的情况下运行拓扑生成器合并向导，将会出现以下错误：

![WMI 错误消息](images/JJ204816.a007d2f2-fc85-430c-91eb-382b032469af(OCS.15).jpg "WMI 错误消息")

如果试图在没有安装 WMI 向后兼容包的情况下运行 **Merge-CsLegacytopology** cmdlet，将会出现以下错误：

![Windows PowerShell WMI 提供程序错误](images/JJ204816.c510824e-1807-4c7e-bb28-c6cfea2eac1d(OCS.15).jpg "Windows PowerShell WMI 提供程序错误")

安装 WMI 向后兼容包

1.  从安装媒体中，导航到 " \\ 安装 \\ AMD64 安装程序" \\ \\OCSWMIBC.MSI。

2.  安装 OCSWMIBC.MSI。
    
    <div>
    

    > [!IMPORTANT]  
    > OCSWMIBC.msi 必须安装在运行拓扑生成器合并向导的计算机上。不过，建议将 OCSWMIBC.msi 安装在拓扑中的所有前端服务器上。

    
    </div>
    
    <div>
    

    > [!IMPORTANT]  
    > 可以在安装了 Lync Server 2013 Core 组件和 Lync Server 2013 命令行管理程序的域中的任何计算机上安装 OCSWMIBC.msi，并且可以访问 Office 通信服务器 2007 R2 拓扑（WMI 提供程序到 Active Directory 域服务（AD DS）和 SQL Server）。

    
    </div>

</div>

<span> </span>

</div>

</div>

</div>

