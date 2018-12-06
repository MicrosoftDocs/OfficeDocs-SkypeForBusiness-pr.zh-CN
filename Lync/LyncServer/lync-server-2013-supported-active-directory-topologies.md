---
title: Lync Server 2013：支持的 Active Directory 拓扑
TOCTitle: 支持的 Active Directory 拓扑
ms:assetid: 0c76b778-7652-4eb0-b161-86f2d4a94ccf
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg398173(v=OCS.15)
ms:contentKeyID: 49311981
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 中支持的 Active Directory 拓扑

 

_**上一次修改主题：** 2016-12-08_

Lync Server 2013 支持与 Microsoft Lync Server 2010 和 Microsoft Office Communications Server 2007 R2 相同的 Active Directory 域服务 拓扑。支持以下拓扑：

  - 具有单个域的单林

  - 具有单个树和多个域的单林

  - 具有多个树和互不连接的命名空间的单林

  - 中央林拓扑中的多林

  - 资源林拓扑中的多林

  - 具有 Exchange Online 的 Lync 资源林拓扑中的多个林

下图标识了在本节插图中使用的图标。

**拓扑插图图例**

![拓扑插图图例](images/Gg398173.0c3cc89f-6c43-4bc8-b2ec-61d89e391ee9(OCS.15).jpg "拓扑插图图例")

## 单林单域

Lync Server 支持的最简单的 Active Directory 拓扑是单域林，这是一种常用的拓扑。

下图显示了单域 Active Directory 拓扑中的 Lync Server 部署。

**单个域拓扑**

![单个域拓扑](images/Gg398173.258b3b3f-0558-4a36-a4c2-031be7299668(OCS.15).jpg "单个域拓扑")

## 单林多域

Lync Server 支持的另一种 Active Directory 拓扑是，由一个根域和一个或多个子域组成的单个林。在这种类型的 Active Directory 拓扑中，用来创建用户的域与将 Lync Server 部署到的域可以不同。但是，如果部署前端池，则必须在单个域的池中部署所有前端服务器。 Lync Server 对 Windows 通用管理员组的支持实现了跨域管理。

下图显示了具有多个域的单林中的部署。在此图中，用户图标表示用户帐户所在的域，箭头指向 Lync Server 池所在的域。用户帐户包括下列类型：

  - 与 Lync Server 池位于同一域中的用户帐户

  - 与 Lync Server 池位于不同域中的用户帐户

  - 位于 Lync Server 池所在域的子域中的用户帐户

**具有多个域的单个林**

![具有多个域的单个林](images/Gg398173.2b809c72-c3cd-4fad-afe6-8c2dae779750(OCS.15).jpg "具有多个域的单个林")

## 单林多树

多树林拓扑由两个或更多域组成，这些域定义了独立的树结构和互不相同的 Active Directory 命名空间。

下图显示了含多个树的单个林。在此图中，用户图标表示用户帐户所在的域，实线指向位于相同或不同域中的 Lync Server 池，虚线指向位于不同树中的 Lync Server 池。用户帐户包括下列类型：

  - 与 Lync Server 池位于同一域中的用户帐户

  - 与 Lync Server 池位于不同域（但在同一个树）中的用户帐户

  - 与 Lync Server 池位于不同树中的用户帐户

**具有多个树的单个林**

![具有多个树的单个林](images/Gg398173.db30fa49-174a-4974-8695-41dd78e39432(OCS.15).jpg "具有多个树的单个林")

## 含有多个林的中央林拓扑

Lync Server 支持中央林拓扑中配置的多个林。中央林拓扑使用中央林中的联系对象来表示其他林中的用户。中央林还为此林中的任何用户承载用户帐户。由 Microsoft Identity Integration Server (MIIS)、Microsoft Forefront Identity Manager (FIM) 2010 或 Microsoft Identity Lifecycle Manager (ILM) 2007 功能包 1 (FP1) 等目录同步产品来管理组织内用户帐户的生命周期：在其中的一个林中创建新用户帐户或从林中删除用户帐户时，目录同步产品便会同步中央林中对应的联系人。

中央林具有以下优点：

  - 将运行 Lync Server 的服务器集中在一个林中。

  - 用户可搜索任何林中的其他用户并与之通信。

  - 用户可查看任何林中其他用户的状态。

  - 在创建或删除用户帐户时，目录同步产品会自动向中央林中添加联系对象或从林中删除联系对象。

下图显示了一个中央林拓扑。在此图中，承载 Lync Server 的域（位于中央林中）与每个仅用户域（位于单独的域中）之间存在双向信任关系。不需要扩展单独的用户域中的架构。

**中央林拓扑**

![中央林拓扑](images/Gg398173.7feb049a-453b-4134-9128-873b83ee1755(OCS.15).jpg "中央林拓扑")

## 含多个林的资源林拓扑

在资源林拓扑中，一个林专用于运行服务器应用程序，如 Microsoft Exchange Server 和 Lync Server。资源林承载服务器应用程序以及活动用户对象的同步表示形式，但不包含启用了登录的用户帐户。资源林用作用户对象所在的其他林的共享服务环境。用户林与资源林之间存在林级信任关系。在这种类型的拓扑中部署 Lync Server 时，需在资源林中为用户林中的每个用户帐户创建一个禁用用户对象。如果已在资源林中部署了 Microsoft Exchange，则禁用的用户帐户可能已存在。由 MIIS、Microsoft Forefront Identity Manager (FIM) 2010 或 Microsoft Identity Lifecycle Manager (ILM) 2007 功能包 1 (FP1) 等目录同步产品来管理用户帐户的生命周期。在其中的一个用户林中创建新用户帐户或从林中删除用户帐户时，目录同步产品便会同步资源林中对应的用户表示形式。

此拓扑可用于为管理多个林的组织中的服务提供共享基础结构，或用于将 Active Directory 对象的管理与其他管理相分离。出于安全考虑而需要隔离 Active Directory 管理的公司通常选用这种拓扑。

这种拓扑带来的好处是，只需为单个林（即资源林）扩展 Active Directory 架构。

下图显示了资源林拓扑。

**资源林拓扑**

![Active Directory 资源林拓扑](images/Gg398173.54ab82f1-e9e5-40f0-a54e-86e340b65c2a(OCS.15).jpg "Active Directory 资源林拓扑")

## 具有 Exchange Online 的 Lync 资源林拓扑中的多个林

在此拓扑中，一个或多个林位于本地，专用于托管 Active Directory 用户帐户。资源林位于外部，由第三方托管提供商维护。资源林仅包含 Lync Server 部署以及来自本地用户帐户林的用户帐户的同步复制。它不包含启用了登录的用户帐户。Exchange 部署在与 Exchange Online（混合）集成的本地用户帐户林中，或者本地用户帐户的电子邮件服务专门由 Exchange Online 提供。

资源林用作用户对象所在的本地 Active Directory 林的共享服务环境。用户帐户林与资源林之间存在单向林级信任关系。在这种类型的拓扑中部署 Lync Server 时，需在资源林中为用户林中的每个用户帐户创建一个禁用用户对象。由 MIIS、Microsoft Forefront Identity Manager (FIM) 2010 或 Microsoft Identity Lifecycle Manager (ILM) 2007 功能包 1 (FP1) 等目录同步产品来管理用户帐户的生命周期。在其中的一个用户林中创建新用户帐户或从林中删除用户帐户时，目录同步产品便会同步资源林中对应的用户表示形式。有关配置多林部署的详细信息，请参阅[在多林体系结构中部署 Lync（合作伙伴使用 Exchange 混合托管 Lync）](http://go.microsoft.com/fwlink/p/?linkid=513216)。

