---
title: 配置 SCOM 监控
ms.reviewer: ''
ms.author: kenwith
author: kenwith
audience: Admin
TOCTitle: Configure SCOM monitoring
ms:assetid: 4003d225-2a33-448c-abd9-571750661140
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688033(v=OCS.15)
ms:contentKeyID: 49733624
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8e114d3f18e482c11a8e83c9d4308f3c5712932c
ms.sourcegitcommit: 30ed4457d7004ba732372fee11a6f0b1baf48e05
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/08/2020
ms.locfileid: "40971154"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-scom-monitoring"></a>配置 SCOM 监控

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2012-10-04_

迁移到 Microsoft Lync Server 2013 后，必须完成一些任务，才能将 Lync Server 2013 配置为使用 System Center Operations Manager。

  - 将 Lync Server 2010 更新应用到选择的服务器以管理集中发现逻辑。

  - 更新中央发现候选服务器注册表项。

  - 将您的主 System Center Operations Manager 管理服务器配置为替代候选中央发现节点。

下面提供了有关执行其中每项任务的说明。

**将 Lync Server 2010 更新应用到选择的服务器以管理集中发现逻辑。**

1.  选择安装了 System Center Operations Manager 代理文件的服务器，并将其配置为候选发现节点。

2.  将 Lync Server 2010 更新应用于此服务器。 请参阅[应用 Lync Server 2010 更新](apply-lync-server-2010-updates.md)主题。

**更新中央发现候选服务器注册表项。**

1.  在选择了管理中心发现逻辑的服务器上，打开 Windows PowerShell 命令窗口。

2.  在命令行中键入：
    
       ```PowerShell
        New-Item -Path "HKLM:\Software\Microsoft\Real-Time Communications\Health"
       ```
    
       ```PowerShell
        New-Item -Path "HKLM:\Software\Microsoft\Real-Time Communications\Health\CentralDiscoveryCandidate"
       ```
    
    <div class="">
    

    > [!NOTE]  
    > 编辑注册表时，如果注册表项已存在，则可能会遇到错误：命令失败。 如果遇到这种情况，您可以安全地忽略该错误。

    
    </div>

**将您的主 System Center Operations Manager 管理服务器配置为替代候选中央发现观察程序节点。**

1.  在已安装 System Center Operations Manager 控制台的计算机上，展开 "**管理包对象**"，然后选择 "**对象发现**"。

2.  单击 "**更改范围 ...** "

3.  从 "**作用域管理包对象**" 页面中，选择 "**搜索候选**项"。

4.  将 "**发现候选**项" 的有效值替换为前面过程中所选择的候选服务器的名称。

最后，若要完成更改，请重新启动 System Center Operations Manager 根管理服务器上的运行状况服务。

</div>

<span> </span>

</div>

</div>

</div>

