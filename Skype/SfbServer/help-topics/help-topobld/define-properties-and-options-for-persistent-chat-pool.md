---
title: 定义持久聊天池的属性和选项
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/27/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddPersistentChatOptionsPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: f4914a44-2113-48f1-8299-4645fc7011b6
description: 通过定义以下属性为持久聊天服务器或持久聊天服务器池配置选项：
ms.openlocfilehash: acc80c76e79364be730ec56a2b64e5dcd001f661
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49818422"
---
# <a name="define-properties-and-options-for-persistent-chat-pool"></a><span data-ttu-id="4ecd9-103">定义持久聊天池的属性和选项</span><span class="sxs-lookup"><span data-stu-id="4ecd9-103">Define Properties and Options for Persistent Chat Pool</span></span>
 
<span data-ttu-id="4ecd9-104">通过定义以下属性为持久聊天服务器或持久聊天服务器池配置选项：</span><span class="sxs-lookup"><span data-stu-id="4ecd9-104">You configure options for your Persistent Chat Server or Persistent Chat Server pool by defining the following properties:</span></span>
  
 <span data-ttu-id="4ecd9-105">**持久聊天池的** 显示名称：定义将为此持久聊天服务器或持久聊天服务器池显示的用户友好名称的必需属性。</span><span class="sxs-lookup"><span data-stu-id="4ecd9-105">**Display name of the Persistent Chat pool**: A required property that defines a user friendly name that will be displayed for this Persistent Chat Server or Persistent Chat Server pool.</span></span>
  
 <span data-ttu-id="4ecd9-106">**持久聊天端口**：定义此持久聊天服务器或持久聊天服务器池将侦听的端口号的必需属性。</span><span class="sxs-lookup"><span data-stu-id="4ecd9-106">**Persistent Chat port**: A required property that will define the port number that this Persistent Chat Server or Persistent Chat Server pool will listen on.</span></span>
  
 <span data-ttu-id="4ecd9-107">**启用合规性**：如果计划部署和实施可选的持久聊天合规性功能及数据库，请选中此复选框。</span><span class="sxs-lookup"><span data-stu-id="4ecd9-107">**Enable compliance**: Select the check box if you plan to deploy and implement the optional Persistent Chat compliance feature and database.</span></span>
  
 <span data-ttu-id="4ecd9-108">使用 **SQL Server** 存储启用灾难恢复：如果计划从另一个存储上配置的备份存储集部署和实施持久聊天 SQL Server 存储的灾难恢复，请选中此SQL Server。</span><span class="sxs-lookup"><span data-stu-id="4ecd9-108">**Use backup SQL Server stores to enable disaster recovery**: Select this check box if you plan to deploy and implement disaster recovery of the Persistent Chat SQL Server stores from a configured backup set of stores on another SQL Server.</span></span> <span data-ttu-id="4ecd9-109">有关详细信息，请参阅 [在 Skype for Business Server 2015](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md)中为持久聊天服务器配置高可用性和灾难恢复。</span><span class="sxs-lookup"><span data-stu-id="4ecd9-109">For details, see [Configure high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="4ecd9-110">此选项仅适用于具有多台服务器的池。</span><span class="sxs-lookup"><span data-stu-id="4ecd9-110">This option is available only for pools with multiple servers.</span></span> 
  
 <span data-ttu-id="4ecd9-111">**使用此池作为站点 \<site that this server or pool is being configured in\>** 的默认池：如果此池是站点的默认持久聊天服务器或持久聊天服务器池，则选中此复选框。</span><span class="sxs-lookup"><span data-stu-id="4ecd9-111">**Use this pool as default for the site \<site that this server or pool is being configured in\>**: Select this check box if this will be the default Persistent Chat Server or Persistent Chat Server pool for the site.</span></span> <span data-ttu-id="4ecd9-112">每个站点必须具有一个默认的持久聊天服务器或 pol。</span><span class="sxs-lookup"><span data-stu-id="4ecd9-112">You must have one default Persistent Chat server or pol per site.</span></span>
  
> [!NOTE]
> <span data-ttu-id="4ecd9-113">如果拓扑包括多个站点，则还会显示“使用此池作为所有站点的默认池”复选框。</span><span class="sxs-lookup"><span data-stu-id="4ecd9-113">If your topology includes multiple sites, a checkbox for **Use this pool as default for all sites** is also displayed.</span></span>
  
<span data-ttu-id="4ecd9-114">单击“上一步”以回到上一个池定义对话框。</span><span class="sxs-lookup"><span data-stu-id="4ecd9-114">Click **Back** to go back to the previous pool definition dialog.</span></span>
  
<span data-ttu-id="4ecd9-115">完成 **为此** 池输入选项后单击"下一步"，继续执行持久聊天服务器池定义。</span><span class="sxs-lookup"><span data-stu-id="4ecd9-115">Click **Next** after you have finished entering the options for this pool to proceed with the Persistent Chat Server pool definition.</span></span>
  
<span data-ttu-id="4ecd9-116">单击“取消”以放弃所有更改并退出“定义新的持久聊天池”向导。</span><span class="sxs-lookup"><span data-stu-id="4ecd9-116">Click **Cancel** to discard all changes and end the **Define New Persistent Chat Pool** wizard.</span></span>
  
<span data-ttu-id="4ecd9-117">单击“帮助”以访问上下文相关帮助，例如此页面。</span><span class="sxs-lookup"><span data-stu-id="4ecd9-117">Click **Help** to access context sensitive help, such as this page.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="4ecd9-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="4ecd9-118">See also</span></span>

[<span data-ttu-id="4ecd9-119">在 Skype for Business Server 2015 中规划持久聊天服务器</span><span class="sxs-lookup"><span data-stu-id="4ecd9-119">Plan for Persistent Chat Server in Skype for Business Server 2015</span></span>](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)
  
[<span data-ttu-id="4ecd9-120">将持久聊天服务器添加到 Skype for Business Server 2015 拓扑</span><span class="sxs-lookup"><span data-stu-id="4ecd9-120">Add Persistent Chat Server to your Skype for Business Server 2015 topology</span></span>](../../deploy/deploy-persistent-chat-server/add-persistent-chat-server.md)
