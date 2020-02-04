---
title: Lync Server 2013：支持的 Active Directory 拓扑
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Supported Active Directory topologies
ms:assetid: 0c76b778-7652-4eb0-b161-86f2d4a94ccf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398173(v=OCS.15)
ms:contentKeyID: 48183391
ms.date: 10/02/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3e4aca368f6ea7d5b31a1cfe74273dfbd42a6594
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764358"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="supported-active-directory-topologies-in-lync-server-2013"></a>Lync Server 2013 中支持的 Active Directory 拓扑

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2014-10-02_

Lync Server 2013 支持与 Microsoft Lync Server 2010 和 Microsoft Office 通信服务器 2007 R2 相同的 Active Directory 域服务拓扑。 支持下列拓扑：

  - 具有单个域的单林

  - 具有单个树和多个域的单林

  - 具有多个树和互不连接的命名空间的单林

  - 中央林拓扑中的多林

  - 资源林拓扑中的多林

  - 使用 Exchange Online 的 Lync 资源林拓扑中的多个林

下图标识了本部分中的插图中使用的图标。

**拓扑图的关键**

![拓扑图的关键](images/Gg398173.0c3cc89f-6c43-4bc8-b2ec-61d89e391ee9(OCS.15).jpg "拓扑图的关键")

<div>

## <a name="single-forest-single-domain"></a>单林、单个域

Lync Server （单个域林）支持的最简单的活动目录拓扑是常见拓扑。

下图显示了单个域 Active Directory 拓扑中的 Lync Server 部署。

**支持的 MA 与 SFB，启用了 MA 的 SFBO，加 EXCH 和 SFB。**

![支持的 MA 与 SFB，启用了 MA 的 SFBO，加 EXCH 和 SFB。](images/Gg398173.258b3b3f-0558-4a36-a4c2-031be7299668(OCS.15).jpg "支持的 MA 与 SFB，启用了 MA 的 SFBO，加 EXCH 和 SFB。")

</div>

<div>

## <a name="single-forest-multiple-domains"></a>单个林、多个域

Lync Server 支持的其他 Active Directory 拓扑是一个由根域和一个或多个子域组成的单个林。 在此类型的 Active Directory 拓扑中，你创建用户的域可能不同于你在其中部署 Lync Server 的域。 但是，如果你部署前端池，则必须在单个域内部署池中的所有前端服务器。 Lync Server 支持 Windows 通用管理员组支持跨域管理。

下图显示了具有多个域的单个林中的部署。 在此图中，用户图标显示用户帐户所驻留的域，箭头指向 Lync 服务器池所在的域。 用户帐户包括以下内容：

  - 与 Lync Server 池位于同一域中的用户帐户

  - Lync Server 池中的其他域中的用户帐户

  - 使用 Lync Server 池的域的子域中的用户帐户

**具有多个域的单个林**

![具有多个域的单个林](images/Gg398173.2b809c72-c3cd-4fad-afe6-8c2dae779750(OCS.15).jpg "具有多个域的单个林")

</div>

<div>

## <a name="single-forest-multiple-trees"></a>单林、多个树

多树林拓扑由两个或多个域组成，这些域定义独立的树结构和单独的 Active Directory 命名空间。

下图显示了具有多个树的单个目录林。 在此图中，用户图标显示用户帐户所在的域、实线指向位于同一域或不同域的 Lync Server 池，并且虚线指向位于不同树中的 Lync Server 池。 用户帐户包括以下内容：

  - 与 Lync Server 池位于同一域中的用户帐户

  - 不同域中的用户帐户（但同一个树与 Lync 服务器池相同）

  - Lync Server 池中的不同树中的用户帐户

**具有多个树的单林**

![具有多个树的单林](images/Gg398173.db30fa49-174a-4974-8695-41dd78e39432(OCS.15).jpg "具有多个树的单林")

</div>

<div>

## <a name="multiple-forests-central-forest"></a>多个林，中央林

Lync Server 支持在中央林拓扑中配置的多个林。 中央林拓扑使用中央林中的联系人对象来表示其他林中的用户。 中央林还为此林中的任何用户托管用户帐户。 目录同步产品（如 Microsoft 身份集成服务器（MIIS）、Microsoft Forefront Identity Manager （FIM）2010或 Microsoft Identity 生命周期管理器（ILM）2007功能包1（FP1）在中管理用户帐户的生命周期组织：当在其中一个目录林中创建新用户帐户或从目录林中删除用户帐户时，目录同步产品将同步中央林中的相应联系人。

中央林具有以下优点：

  - 运行 Lync Server 的服务器集中在单个林中。

  - 用户可以搜索任何林中的其他用户并与之通信。

  - 用户可以查看任何林中的其他用户的状态。

  - 目录同步产品可在创建或删除用户帐户时自动添加和删除中央林中的联系人对象。

下图显示了中央林拓扑。 在此图中，托管 Lync Server 的域之间有双向信任关系（位于中央林）和每个仅用户域（位于单独的林中）之间。 单独用户目录林中的架构无需扩展。

**中央林拓扑**

![中央林拓扑](images/Gg398173.7feb049a-453b-4134-9128-873b83ee1755(OCS.15).jpg "中央林拓扑")

</div>

<div>

## <a name="multiple-forests-resource-forest"></a>多个林，资源林

在资源林拓扑中，一个林专用于运行服务器应用程序，例如 Microsoft Exchange Server 和 Lync Server。 资源林托管服务器应用程序和活动用户对象的同步表示形式，但不包含启用登录的用户帐户。 资源林充当用户对象所在的其他林的共享服务环境。 用户林与资源林具有林级别的信任关系。 在此类型的拓扑中部署 Lync Server 时，在资源目录林中为用户目录林中的每个用户帐户创建一个已禁用的用户对象。 如果 Microsoft Exchange 已部署在资源目录林中，则已禁用的用户帐户可能已存在。 目录同步产品（如 MIIS、Microsoft Forefront Identity Manager （FIM）2010或 Microsoft Identity 生命周期管理器（ILM）2007功能包1（FP1））管理用户帐户的生命周期。 当在其中一个用户林中创建新的用户帐户，或者从目录林中删除用户帐户时，目录同步产品将同步资源林中对应的用户表示形式。

此拓扑可用于为组织中管理多个林的服务提供共享基础结构，或将 Active Directory 对象的管理与其他管理分开。 出于安全原因需要隔离 Active Directory 管理的公司通常会选择此拓扑。

此拓扑提供了限制将 Active Directory 架构扩展到单个林（即资源林）的需要的好处。

下图显示了一个资源林拓扑。

**资源林拓扑**

![Active Directory 资源林拓扑](images/Gg398173.54ab82f1-e9e5-40f0-a54e-86e340b65c2a(OCS.15).jpg "Active Directory 资源林拓扑")

</div>

<div>

## <a name="multiple-forests-in-a-lync-resource-forest-topology-with-exchange-online"></a>使用 Exchange Online 的 Lync 资源林拓扑中的多个林

在此拓扑中，一个或多个林位于本地，并且专用于托管 Active Directory 用户帐户。 资源林位于本地，由第三方托管提供商维护。 资源林仅包含本地用户帐户林中的 Lync Server 部署和用户帐户的同步复制。 它不包含启用登录的用户帐户。 Exchange 是在集成的本地用户帐户目录林中（与 Exchange Online （混合）一起部署的）中部署的，或者本地用户帐户的电子邮件服务专门由 Exchange Online 提供。

资源林充当用户对象所在的本地 Active Directory 林的共享服务环境。 用户帐户林与资源林有一种方式的林级信任关系。 在此类型的拓扑中部署 Lync Server 时，在资源目录林中为用户目录林中的每个用户帐户创建一个已禁用的用户对象。 目录同步产品（如 MIIS、Microsoft Forefront Identity Manager （FIM）2010或 Microsoft Identity 生命周期管理器（ILM）2007功能包1（FP1））管理用户帐户的生命周期。 当在其中一个用户林中创建新的用户帐户，或者从目录林中删除用户帐户时，目录同步产品将同步资源林中对应的用户表示形式。 有关配置多目录林部署的详细信息，请参阅[在多林结构（具有 Exchange 混合的合作伙伴托管 lync）中部署 Lync](http://go.microsoft.com/fwlink/p/?linkid=513216)。

</div>

</div>

<span> </span>

</div>

</div>

</div>

