---
title: 配置 SCOM 监控
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
audience: Admin
f1.keywords:
- NOCSH
TOCTitle: Configure SCOM monitoring
ms:assetid: 4003d225-2a33-448c-abd9-571750661140
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688033(v=OCS.15)
ms:contentKeyID: 49733624
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 95bc54defed596dfa8a8d801908b281abf06ead3
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/16/2020
ms.locfileid: "44754520"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-scom-monitoring"></a>配置 SCOM 监控

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-10-04_

迁移到 Microsoft Lync Server 2013 后，必须完成几个任务，才能配置 Lync Server 2013 以使用 System Center Operations Manager。

  - 将 Lync Server 2010 更新应用于选择的服务器以管理中央发现逻辑。

  - 更新中央发现候选服务器注册表项。

  - 将主 System Center Operations Manager 管理服务器配置为覆盖候选中央发现节点。

下面提供了有关执行所有这些任务的说明。

**将 Lync Server 2010 更新应用于选择的服务器以管理中央发现逻辑。**

1.  选择安装了 System Center Operations Manager 代理文件且配置为候选发现节点的服务器。

2.  将 Lync Server 2010 更新应用到此服务器。 请参阅[应用 Lync Server 2010 更新](apply-lync-server-2010-updates.md)主题。

**更新中央发现候选服务器注册表项。**

1.  在选择了管理中央发现逻辑的服务器上，打开 Windows PowerShell 命令窗口。

2.  在命令行中键入：
    
       ```PowerShell
        New-Item -Path "HKLM:\Software\Microsoft\Real-Time Communications\Health"
       ```
    
       ```PowerShell
        New-Item -Path "HKLM:\Software\Microsoft\Real-Time Communications\Health\CentralDiscoveryCandidate"
       ```
    
    <div class="">
    

    > [!NOTE]  
    > Whenever you edit the registry, you may experience an error that the command failed if the registry key already exists. If you experience this, you can safely ignore the error.

    
    </div>

**将您的主 System Center Operations Manager 管理服务器配置为覆盖候选中央发现观察程序节点。**

1.  在已安装 System Center Operations Manager 控制台的计算机上，展开“管理包对象”****，然后选择“对象发现”****。

2.  单击“更改范围”****。

3.  从“范围管理包对象”**** 页中，选择“LS 发现候选”****。

4.  将“LS 发现候选有效值”**** 覆盖为在之前的过程中选定的候选服务器的名称。

最后，若要最终完成您的更改，请重新启动 System Center Operations Manager Root Management Server 上的运行状况服务。

</div>

<span> </span>

</div>

</div>

</div>

