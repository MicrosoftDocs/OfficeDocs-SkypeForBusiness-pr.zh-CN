---
title: 存档服务器常规设置扩展器
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.ArchivingGeneralSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0b820af7-8d00-42e2-979c-dbae17159a08
description: 在拓扑生成器中，您可以编辑各个可以通过右键单击存档运行在控制台树中，单击操作，在工具栏中，或通过单击操作窗格中的任务，然后单击编辑的服务器的存档服务器的属性属性和更改以下选项之一：
ms.openlocfilehash: 9ccad6b4808bc5ffe2066576eff9b2e298f9c236
ms.sourcegitcommit: 08cf97296fb9ba6fbc4d68c3e380c8f37e86dd02
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/20/2018
ms.locfileid: "19978172"
---
# <a name="archiving-server-general-settings-expander"></a><span data-ttu-id="07323-103">存档服务器常规设置扩展器</span><span class="sxs-lookup"><span data-stu-id="07323-103">Archiving Server General Settings Expander</span></span>
 
<span data-ttu-id="07323-104">在拓扑生成器中，可以通过右键单击控制台树中的“存档服务器”，再单击工具栏中的“**操作**”，或单击“操作”窗格中的任务，然后单击“**编辑属性**”并更改以下任意选项来编辑各个存档服务器的属性：</span><span class="sxs-lookup"><span data-stu-id="07323-104">In Topology Builder, you can edit the properties for an individual server running Archiving either by right-clicking the server running Archiving in the console tree and clicking **Action** in the toolbar, or by clicking a task in the Actions pane, and then clicking **Edit Properties** and changing any of the following options:</span></span>
  
- <span data-ttu-id="07323-105">**FQDN**，更改要部署为存档服务器的服务器的完全限定域名 (FQDN)。</span><span class="sxs-lookup"><span data-stu-id="07323-105">**FQDN**, to change the fully qualified domain name (FQDN) of the server that you want to deploy as an Server running Archiving.</span></span>
    
- <span data-ttu-id="07323-p101">**SQL 存储**，更改要用于存档 SQL Server 数据库的 SQL Server 实例。如果更改存档服务器的 SQL Server 数据库，则必须重新启动存档服务器以确保更改生效。</span><span class="sxs-lookup"><span data-stu-id="07323-p101">**SQL store**, to change the instance of SQL Server to be used for the archiving SQL Server database. If you change the SQL Server database of a server running Archiving, you must restart the server running Archiving to make sure that the change takes effect.</span></span>
    
- <span data-ttu-id="07323-p102">**文件共享**，更改要用于存档文件存储的文件夹。如果更改存档服务器的文件共享，则必须重新启动存档服务器以确保更改生效。此外，还必须将以前的会议文件移动到新的文件存储文件夹以避免丢失已存档的会议文件。</span><span class="sxs-lookup"><span data-stu-id="07323-p102">**File share**, to change the folder to be used for the archiving file store. If you change the file share of a Server running Archiving, you must restart the Server running Archiving to make sure that the change takes effect. Additionally, you must move previous conference files to the new file store folder to avoid loss of archived conference files.</span></span>
    
> [!NOTE]
> <span data-ttu-id="07323-111">若要更改与存档服务器关联的池，请为当前与存档服务器关联的单个前端池节点或 Survivable Branch Appliance 节点选择“**编辑属性**”选项。</span><span class="sxs-lookup"><span data-stu-id="07323-111">To change the pools associated with a server running Archiving, select the **Edit Properties** option for the individual Front End pool node or Survivable Branch Appliance node that is currently associated with the server running Archiving.</span></span>
  
> [!NOTE]
> <span data-ttu-id="07323-p103">如果之前将存档服务器添加到拓扑生成器中的拓扑，则存档节点包含存档服务器。可以编辑列表中所有存档服务器的属性。但是，无法存档即时消息或 Web 会议（消息传递），除非另外为存档服务器设置了服务。</span><span class="sxs-lookup"><span data-stu-id="07323-p103">The Archiving node contains a server running Archiving if you have previously added a server running Archiving to the topology in Topology Builder. You can edit properties for any server running Archiving in the list. However, instant messaging or web conferencing (messaging) cannot be archived until you also set up the service for the server running Archiving.</span></span> 
  

