---
title: 定义持久聊天池的属性和选项
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/27/2015
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.tb.AddPersistentChatOptionsPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: f4914a44-2113-48f1-8299-4645fc7011b6
description: 可通过定义以下属性来配置持久聊天服务器或持久聊天服务器池的选项：
ms.openlocfilehash: 458e50ecc3ddd389a8e413e8f2dd368fc0f15369
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/03/2020
ms.locfileid: "41697547"
---
# <a name="define-properties-and-options-for-persistent-chat-pool"></a><span data-ttu-id="b7709-103">定义持久聊天池的属性和选项</span><span class="sxs-lookup"><span data-stu-id="b7709-103">Define Properties and Options for Persistent Chat Pool</span></span>
 
<span data-ttu-id="b7709-104">可通过定义以下属性来配置持久聊天服务器或持久聊天服务器池的选项：</span><span class="sxs-lookup"><span data-stu-id="b7709-104">You configure options for your Persistent Chat Server or Persistent Chat Server pool by defining the following properties:</span></span>
  
 <span data-ttu-id="b7709-105">**持久聊天池的显示名称**：一个必需属性，定义将为此持久聊天服务器或持久聊天服务器池显示的用户友好名称。</span><span class="sxs-lookup"><span data-stu-id="b7709-105">**Display name of the Persistent Chat pool**: A required property that defines a user friendly name that will be displayed for this Persistent Chat Server or Persistent Chat Server pool.</span></span>
  
 <span data-ttu-id="b7709-106">**持久聊天端口**：将定义此永久聊天服务器或持久聊天服务器池将侦听的端口号的 "必需" 属性。</span><span class="sxs-lookup"><span data-stu-id="b7709-106">**Persistent Chat port**: A required property that will define the port number that this Persistent Chat Server or Persistent Chat Server pool will listen on.</span></span>
  
 <span data-ttu-id="b7709-107">**启用合规性**：如果你计划部署和实现可选的持久聊天合规性功能和数据库，请选中该复选框。</span><span class="sxs-lookup"><span data-stu-id="b7709-107">**Enable compliance**: Select the check box if you plan to deploy and implement the optional Persistent Chat compliance feature and database.</span></span>
  
 <span data-ttu-id="b7709-108">**使用备份 SQL Server 存储来启用灾难恢复**：如果你计划从另一个 SQL Server 上配置的存储备份集部署和实现持久聊天 SQL Server 存储的灾难恢复，请选中此复选框。</span><span class="sxs-lookup"><span data-stu-id="b7709-108">**Use backup SQL Server stores to enable disaster recovery**: Select this check box if you plan to deploy and implement disaster recovery of the Persistent Chat SQL Server stores from a configured backup set of stores on another SQL Server.</span></span> <span data-ttu-id="b7709-109">有关详细信息，请参阅[在 Skype for Business server 2015 中配置持久聊天服务器的高可用性和灾难恢复](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md)。</span><span class="sxs-lookup"><span data-stu-id="b7709-109">For details, see [Configure high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="b7709-110">此选项仅适用于具有多台服务器的池。</span><span class="sxs-lookup"><span data-stu-id="b7709-110">This option is available only for pools with multiple servers.</span></span> 
  
 <span data-ttu-id="b7709-111">**将此池用作在\<\>其中配置此服务器或池的网站网站的默认值**：如果这将是该网站的默认持久聊天服务器或持久聊天服务器池，请选中此复选框。</span><span class="sxs-lookup"><span data-stu-id="b7709-111">**Use this pool as default for the site \<site that this server or pool is being configured in\>**: Select this check box if this will be the default Persistent Chat Server or Persistent Chat Server pool for the site.</span></span> <span data-ttu-id="b7709-112">每个网站必须有一个默认持久聊天服务器或 pol。</span><span class="sxs-lookup"><span data-stu-id="b7709-112">You must have one default Persistent Chat server or pol per site.</span></span>
  
> [!NOTE]
> <span data-ttu-id="b7709-113">如果拓扑包括多个站点，则还会显示“**使用此池作为所有站点的默认池**”复选框。</span><span class="sxs-lookup"><span data-stu-id="b7709-113">If your topology includes multiple sites, a checkbox for **Use this pool as default for all sites** is also displayed.</span></span>
  
<span data-ttu-id="b7709-114">单击“**上一步**”以回到上一个池定义对话框。</span><span class="sxs-lookup"><span data-stu-id="b7709-114">Click **Back** to go back to the previous pool definition dialog.</span></span>
  
<span data-ttu-id="b7709-115">输入此池的选项后，单击 "**下一步**" 以继续使用持久聊天服务器池定义。</span><span class="sxs-lookup"><span data-stu-id="b7709-115">Click **Next** after you have finished entering the options for this pool to proceed with the Persistent Chat Server pool definition.</span></span>
  
<span data-ttu-id="b7709-116">单击“**取消**”以放弃所有更改并退出“**定义新的持久聊天池**”向导。</span><span class="sxs-lookup"><span data-stu-id="b7709-116">Click **Cancel** to discard all changes and end the **Define New Persistent Chat Pool** wizard.</span></span>
  
<span data-ttu-id="b7709-117">单击“**帮助**”以访问上下文相关帮助，例如此页面。</span><span class="sxs-lookup"><span data-stu-id="b7709-117">Click **Help** to access context sensitive help, such as this page.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="b7709-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b7709-118">See also</span></span>

[<span data-ttu-id="b7709-119">规划 Skype for Business Server 2015 中的持久聊天服务器</span><span class="sxs-lookup"><span data-stu-id="b7709-119">Plan for Persistent Chat Server in Skype for Business Server 2015</span></span>](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)
  
[<span data-ttu-id="b7709-120">将持久聊天服务器添加到 Skype for business Server 2015 拓扑</span><span class="sxs-lookup"><span data-stu-id="b7709-120">Add Persistent Chat Server to your Skype for Business Server 2015 topology</span></span>](../../deploy/deploy-persistent-chat-server/add-persistent-chat-server.md)
