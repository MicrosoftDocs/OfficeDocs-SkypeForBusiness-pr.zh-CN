---
title: 安装 WMI 向后兼容程序包
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Install WMI Backward Compatibility package
ms:assetid: 38797fbd-06a0-4008-b099-158e7b5d7703
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204816(v=OCS.15)
ms:contentKeyID: 48183893
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3b61d34ce8809f06156f4d4dca61c39cc4aff0f1
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34837982"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="install-wmi-backward-compatibility-package"></a>安装 WMI 向后兼容程序包

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2012-10-02_

如果您尝试运行拓扑生成器合并向导而不安装 WMI 向后兼容性程序包, 则会看到以下错误:

![WMI 错误消息](images/JJ204816.a007d2f2-fc85-430c-91eb-382b032469af(OCS.15).jpg "WMI 错误消息")

如果尝试在不安装 WMI 向后兼容程序包的情况下运行**CsLegacytopology** cmdlet, 则会看到以下错误:

![Windows POWERSHELL WMI 提供程序错误](images/JJ204816.c510824e-1807-4c7e-bb28-c6cfea2eac1d(OCS.15).jpg "Windows POWERSHELL WMI 提供程序错误")

安装 WMI 向后兼容包

1.  从安装媒体中, 导航到\\"\\设置\\AMD64\\设置 OCSWMIBC"。MSI.

2.  安装 OCSWMIBC。MSI.
    
    <div>
    

    > [!IMPORTANT]  
    > OCSWMIBC 必须安装在运行拓扑生成器合并向导的计算机上。 但是, 我们建议在拓扑中的所有前端服务器上安装 OCSWMIBC。

    
    </div>
    
    <div>
    

    > [!IMPORTANT]  
    > OCSWMIBC 可以安装在具有 Lync Server 2013 核心组件和安装了 Lync Server 2013 管理外壳的域中的任何计算机上, 并且有权访问 Office 通信服务器 2007 R2 拓扑 (WMI 提供程序到 Active Directory 域)服务 (AD DS) 和 SQL Server)。

    
    </div>

</div>

<span> </span>

</div>

</div>

</div>

