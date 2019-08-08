---
title: 配置客户端以进行迁移
ms.reviewer: ''
ms.author: kenwith
author: kenwith
audience: Admin
TOCTitle: Configure clients for migration
ms:assetid: 8f17862b-d9d1-47f6-b248-51f4710f5030
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688130(v=OCS.15)
ms:contentKeyID: 49733729
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 710a5cf6cb23b91431b340c44ebe6ff2738b0822
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/07/2019
ms.locfileid: "36233066"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-clients-for-migration"></a>配置客户端以进行迁移

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2013-11-21_

本主题包含在迁移到 Lync Server 2013 之前应执行的推荐的客户端部署步骤。 应在 Office 通信服务器 2007 R2 上进行这些配置更改。 在迁移之前执行这些步骤非常重要。 有关详细信息, 请参阅[在 Lync Server 2013 中规划客户端和设备](lync-server-2013-planning-for-clients-and-devices.md)。

<div>

## <a name="to-configure-clients-prior-to-migration"></a>在迁移之前配置客户端

1.  部署最新的 Office 通信服务器 2007 R2 服务器、客户端和设备更新 (修补程序):
    
      - [应用 Office 通信服务器 2007 R2 更新](apply-office-communications-server-2007-r2-updates.md)
    
      - [有关 Communicator 2007 R2 的累积更新包的说明](http://go.microsoft.com/fwlink/p/?linkid=335808)
    
      - [获取设备的软件更新](http://go.microsoft.com/fwlink/?linkid=335809)

2.  在 Office 通信服务器 2007 R2 上, 使用客户端版本筛选仅允许具有已安装最新更新的 Office 通信服务器 2007 R2 客户端登录。

3.  在 Office 通信服务器 2007 R2 上, 使用客户端版本筛选阻止 Lync Server 2013 客户端登录。 按照**配置客户端版本筛选** [http://go.microsoft.com/fwlink/p/?linkId=202488](http://go.microsoft.com/fwlink/p/?linkid=202488)中介绍的步骤添加下表中列出的版本筛选器。 对于每个版本筛选器, 分配操作**块**。
    
    
    <table>
    <colgroup>
    <col style="width: 33%" />
    <col style="width: 33%" />
    <col style="width: 33%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th>客户端</th>
    <th>用户代理标题</th>
    <th>版本</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p>Lync 2013</p></td>
    <td><p>OC</p></td>
    <td><p>15 ...***</p></td>
    </tr>
    <tr class="even">
    <td><p>Lync Web App</p></td>
    <td><p>CWA</p></td>
    <td><p>5 ...***</p></td>
    </tr>
    <tr class="odd">
    <td><p>Lync Phone Edition</p></td>
    <td><p>OCPhone</p></td>
    <td><p>4 ...***</p></td>
    </tr>
    </tbody>
    </table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

