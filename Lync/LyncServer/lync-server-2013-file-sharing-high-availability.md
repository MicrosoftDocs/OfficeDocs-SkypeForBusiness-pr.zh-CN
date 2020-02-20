---
title: Lync Server 2013：文件共享高可用性
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: File sharing high availability
ms:assetid: b8c8d5ec-9397-4128-8d1e-8ec6c30fade7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205203(v=OCS.15)
ms:contentKeyID: 48185238
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bf27a7316494d24127f65309bdef347b558fade5
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42153694"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="file-sharing-high-availability-in-lync-server-2013"></a>Lync Server 2013 中的文件共享高可用性

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-03-30_

为确保单个数据中心内的 Lync Server 文件共享具有高可用性，您可以使用分布式文件系统（DFS）。 DFS 支持同一个数据中心内从一个文件服务器到另一个文件服务器的故障转移。 对于大型部署，建议您使用通过 DFS 配对的专用文件服务器。

根据您的网络规模和所需的恢复工作量，可以使用一对服务器来承载一个站点中的所有文件共享，也可以为每个前端池使用一对服务器。

DFS 是一个最有效的文件复制机制，未发布任何恢复时间目标 (RTO) 或恢复点目标 (RPO) 承诺。DFS 服务器之间的故障转移应快速完成，但在出现故障转移时，数据复制延迟可能会阻止用户继续工作。

如果需要在文件共享上使用 DFS 和数据存储，则应经常备份文件共享，如每 4 小时到 8 小时备份一次。如果某个文件共享不可用且复制的状态不是最新，则可使用该备份将故障服务器上的内容还原到与此时不可用的服务器配对的另一台服务器上。

</div>

<span> </span>

</div>

</div>

</div>

