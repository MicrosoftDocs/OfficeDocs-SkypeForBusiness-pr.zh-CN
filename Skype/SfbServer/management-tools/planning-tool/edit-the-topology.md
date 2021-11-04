---
title: 在 Skype for Business Server 2015 中编辑拓扑
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
ms.date: 4/5/2016
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: 47425ab1-5645-4d6f-b202-64bcce43e3ef
description: 完成初始访谈问题后，可以编辑站点的 FQDN (FQDN) IP 地址的完全限定域名。 要执行此操作，请在“全局拓扑”页上双击要编辑的站点。
ms.openlocfilehash: 2276f2959329c77744054976e3a49f5ad72778ae
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/04/2021
ms.locfileid: "60776162"
---
# <a name="edit-the-topology-in-skype-for-business-server-2015"></a>在 Skype for Business Server 2015 中编辑拓扑

完成初始访谈问题后，可以编辑站点的 FQDN (FQDN) IP 地址的完全限定域名。 要执行此操作，请在 **“全局拓扑”** 页上双击要编辑的站点。

规划工具显示所选站点的站点拓扑。 在站点页面的底部有四个选项卡：

![规划工具站点拓扑。](../../media/Planning_Tool_Site_Topology.png)

- 站点拓扑 - 当前显示的页面，其中直观概述了建议拓扑。

- 边缘网络图 - "边缘网络图"页是设计师在规划工具中执行大部分工作的位置。 该图显示了推荐的 Skype for Business Server 2015 拓扑的网络配置，以及服务器、池以及硬件和域名系统 (DNS) 负载平衡器 IP 地址和 FQDN 的可编辑条目。

- 边缘管理员报告 - 边缘管理员报告共包含四个报告：

     !["边缘管理员报告"页。](../../media/Planning_Tool_Summary_Report.png)

  - 摘要报告 - 边缘网络配置的常规设置报告。 如果将"边缘网络图"页上的值编辑为将在实际部署中使用的拓扑 TCP/IP 和 FQDN 值，则此处将表示这些地址和名称。 否则，将显示默认文本。

  - 证书报告 - 证书报告将列出拓扑所需的证书的主题名称和主题替代名称。

  - 防火墙报告 - 防火墙报告列出了在基础结构中配置外围防火墙所必需的信息。 这包括默认或编辑 (IP 地址) 、服务器角色、源 IP 和端口、目标 IP 和端口、传输协议、应用程序协议和相关注释。

  - DNS 报告 - DNS 报告列出了您必须创建的 DNS 条目的相关信息。 其中包括相应操作所需的记录类型、FQDN、IP 地址和备注。

- 网站摘要 - 网站摘要概述了通过回答初始访谈式问题或填写"设计网站" **中的值而做出的选择**。 还显示容量信息。

    > [!NOTE]
    > “站点摘要”页上的信息可针对每个设计进行自定义，可能不包含此处详细介绍的所有内容或信息。

## <a name="edit-the-network-configuration-diagram"></a>编辑网络配置图
<a name="Edit_Network_diagram"> </a>

设计师在 Skype for Business Server 2015 规划工具中执行大部分工作包括定义网络图上条目的 IP 地址和完全限定域名 (FQDN) 条目。 在此页上输入的信息将进入报告以及规划工具中包含的其他信息。

![规划工具网络图。](../../media/Planning_Tool_Network_Diagram.png)

规划工具为 IP 地址和 FQDN 创建一个包含默认文本的网络图。

编辑网络图和输入值：

1. 选择起始网络段。 例如，双击文本，然后单击 **"access1.contoso.com"。** 在打开的对话框中，键入服务器服务器的实际 FQDN access1.contoso.com 实际的 IP 地址，以替换 131.107.155.3。

2. 单击 **“确定”** 以保存条目。

3. 继续编辑 IP 地址和 FQDN，从而为硬件负载平衡器提供虚拟 IP 地址或者为池中服务器的域名系统 (DNS) 负载平衡提供服务器条目。

规划工具的一个有用功能是可以递增地分配一系列 IP 地址和服务器主机名称，而不是要求设计师编辑池中的单台服务器。例如：

1. 双击池化的前端服务器。 对话框打开后，选中 **“是否要将 IP 和 FQDN 用作此群集中所有等效服务器的起始点?”**。

2. 例如，第一台服务器的起始值为 fe0101.contoso.com IP 地址为 192.168.21.122。

3. 在 fe0.contoso.com **FQDN** 中键入 fe0.contoso.com，在前端服务器 **IP** 地址中键入 192.168.21.131，然后单击"确定 **"。**

4. 自动递增功能将池中的所有服务器更新为fe01至fe06，将所有 IP 地址从 192.168.21.131 更新为 136。

完成所有编辑后，通过完成以下步骤保存拓扑：

若要保存规划工具设计，请单击"**文件**"，然后单击"保存 **拓扑**"或"**将拓扑另存为"。** 如果出现 **“将规划工具另存为”** 对话框，请在 **“文件名”** 中键入文件的名称，然后单击 **“保存”**。

## <a name="see-also"></a>另请参阅
<a name="Edit_Network_diagram"> </a>

[编辑设计](/previous-versions/office/lync-server-2013/lync-server-2013-editing-the-design)