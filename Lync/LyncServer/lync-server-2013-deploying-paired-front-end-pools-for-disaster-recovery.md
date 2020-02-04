---
title: Lync Server 2013：针对灾难恢复部署配对的前端池
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploying paired Front End pools for disaster recovery
ms:assetid: 2f12467c-8b90-43e6-831b-a0b096427f17
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204773(v=OCS.15)
ms:contentKeyID: 48183727
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d264128a7fef38fd220d2527772d6065dca7c964
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41740912"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploying-paired-front-end-pools-for-disaster-recovery-in-lync-server-2013"></a>在 Lync Server 2013 中针对灾难恢复部署配对的前端池

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2013-02-21_

你可以使用拓扑生成器轻松部署配对的前端池的灾难恢复拓扑。

<div>

## <a name="to-deploy-a-pair-of-front-end-pools"></a>部署配对前端池

1.  如果池是新的且尚未定义，请使用拓扑生成器创建池。

2.  在拓扑生成器中，右键单击两个池之一，然后单击 "**编辑属性**"。

3.  在左侧窗格中单击“**复原**”，然后在右侧窗格中选择“**关联的备份池**”。

4.  在“**关联的备份池**”下方的框中，选择要与该池配对的池。仅可以选择尚未与其他池配对的现有池。
    
    ![36080581-db76-497d-bf9e-f02b39574d0e](images/JJ204773.36080581-db76-497d-bf9e-f02b39574d0e(OCS.15).png "36080581-db76-497d-bf9e-f02b39574d0e")  

5.  选择“**语音的自动故障转移和故障回复**”，然后单击“**确定**”。
    
    当你查看该池的详细信息时，此时关联的池显示在“**复原**”下的右窗格中。

6.  使用拓扑生成器发布拓扑。

7.  如果尚未部署两个池，请立即部署它们，配置随即完成。你可以跳过此过程的最后两步。
    
    但是，如果在定义配对关系之前已部署池，那么必须完成以下两个最终步骤。

8.  在两个池的每个前端服务器上，运行以下命令：
    ```console
    <system drive>\Program Files\Microsoft Lync Server 2013\Deployment\Bootstrapper.exe 
    ```
    这将配置确保备份配对正常运行所需的其他服务。

9.  从 Lync Server Management Shell 命令提示符处，运行以下命令：
    ```powershell
    Start-CsWindowsService -Name LYNCBACKUP
    ```
10. 使用以下 cmdlet 强制两个池的用户和会议数据相互同步：
    
       ```powershell
        Invoke-CsBackupServiceSync -PoolFqdn <Pool1 FQDN>
       ```
    
       ```powershell
        Invoke-CsBackupServiceSync -PoolFqdn <Pool2 FQDN>
       ```
    
    同步数据可能需要一些时间。你可以使用以下 cmdlet 检查同步状态。确保两个方向的状态均保持稳定。
    
       ```powershell
        Get-CsBackupServiceStatus -PoolFqdn <Pool1 FQDN>
       ```
    
       ```powershell
        Get-CsBackupServiceStatus -PoolFqdn <Pool2 FQDN>
       ```

<div class="">


> [!NOTE]  
> 语音选项和拓扑生成器中的相关时间间隔的<STRONG>自动故障转移和故障</STRONG>切换仅适用于 Lync Server 2010 中引入的语音复原功能。 选择此选项并不意味着会自动执行本文档中讨论的池故障转移。 池故障转移和故障回复始终需要管理员手动且分别调用故障转移和故障回复 cmdlet。



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

