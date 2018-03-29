---
title: 定义持久聊天池的属性和选项
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/27/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddPersistentChatOptionsPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: f4914a44-2113-48f1-8299-4645fc7011b6
description: 您可以通过定义下列属性配置选项持久聊天服务器或持久聊天服务器池：
ms.openlocfilehash: 445e84b4be0567b63b9a56a7bc130e584a826430
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="define-properties-and-options-for-persistent-chat-pool"></a><span data-ttu-id="542ce-103">定义持久聊天池的属性和选项</span><span class="sxs-lookup"><span data-stu-id="542ce-103">Define Properties and Options for Persistent Chat Pool</span></span>
 
<span data-ttu-id="542ce-104">您可以通过定义下列属性配置选项持久聊天服务器或持久聊天服务器池：</span><span class="sxs-lookup"><span data-stu-id="542ce-104">You configure options for your Persistent Chat Server or Persistent Chat Server pool by defining the following properties:</span></span>
  
 <span data-ttu-id="542ce-105">**持续聊天池显示名称**： 必需的属性，定义将显示为此持续聊天服务器或持久聊天服务器池的用户友好名称。</span><span class="sxs-lookup"><span data-stu-id="542ce-105">**Display name of the Persistent Chat pool**: A required property that defines a user friendly name that will be displayed for this Persistent Chat Server or Persistent Chat Server pool.</span></span>
  
 <span data-ttu-id="542ce-106">**持续聊天端口**： 所需的属性将定义端口号持久聊天服务器或持久聊天服务器池将侦听。</span><span class="sxs-lookup"><span data-stu-id="542ce-106">**Persistent Chat port**: A required property that will define the port number that this Persistent Chat Server or Persistent Chat Server pool will listen on.</span></span>
  
 <span data-ttu-id="542ce-107">**实现法规遵从性**： 如果您打算部署和实现的可选持久聊天的法规遵从性功能和数据库中选择复选框。</span><span class="sxs-lookup"><span data-stu-id="542ce-107">**Enable compliance**: Select the check box if you plan to deploy and implement the optional Persistent Chat compliance feature and database.</span></span>
  
 <span data-ttu-id="542ce-108">**使用备份 SQL Server 存储以实现灾难恢复**： 选中此复选框，如果您打算部署和实现灾难恢复的持续讨论 SQL Server 存储从另一个 SQL Server 上的存储配置的备份集。</span><span class="sxs-lookup"><span data-stu-id="542ce-108">**Use backup SQL Server stores to enable disaster recovery**: Select this check box if you plan to deploy and implement disaster recovery of the Persistent Chat SQL Server stores from a configured backup set of stores on another SQL Server.</span></span> <span data-ttu-id="542ce-109">有关详细信息，请参阅[配置高可用性和业务服务器 2015年的 Skype 的持久聊天服务器的灾难恢复](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md)。</span><span class="sxs-lookup"><span data-stu-id="542ce-109">For details, see [Configure high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="542ce-110">此选项仅适用于具有多台服务器的池。</span><span class="sxs-lookup"><span data-stu-id="542ce-110">This option is available only for pools with multiple servers.</span></span> 
  
 <span data-ttu-id="542ce-111">**该池的默认值用于该网站\<在中配置此服务器或池的网站\>**： 如果这将是默认持久性聊天服务器或站点的持久聊天服务器池，请选中此复选框。</span><span class="sxs-lookup"><span data-stu-id="542ce-111">**Use this pool as default for the site \<site that this server or pool is being configured in\>**: Select this check box if this will be the default Persistent Chat Server or Persistent Chat Server pool for the site.</span></span> <span data-ttu-id="542ce-112">每个站点必须有一个默认的持久性聊天服务器或 pol。</span><span class="sxs-lookup"><span data-stu-id="542ce-112">You must have one default Persistent Chat server or pol per site.</span></span>
  
> [!NOTE]
> <span data-ttu-id="542ce-113">如果拓扑包括多个站点，则还会显示“**使用此池作为所有站点的默认池**”复选框。</span><span class="sxs-lookup"><span data-stu-id="542ce-113">If your topology includes multiple sites, a checkbox for **Use this pool as default for all sites** is also displayed.</span></span>
  
<span data-ttu-id="542ce-114">单击“**上一步**”以回到上一个池定义对话框。</span><span class="sxs-lookup"><span data-stu-id="542ce-114">Click **Back** to go back to the previous pool definition dialog.</span></span>
  
<span data-ttu-id="542ce-115">输入此池继续进行持续聊天服务器池定义的选项之后，请单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="542ce-115">Click **Next** after you have finished entering the options for this pool to proceed with the Persistent Chat Server pool definition.</span></span>
  
<span data-ttu-id="542ce-116">单击“**取消**”以放弃所有更改并退出“**定义新的持久聊天池**”向导。</span><span class="sxs-lookup"><span data-stu-id="542ce-116">Click **Cancel** to discard all changes and end the **Define New Persistent Chat Pool** wizard.</span></span>
  
<span data-ttu-id="542ce-117">单击“**帮助**”以访问上下文相关帮助，例如此页面。</span><span class="sxs-lookup"><span data-stu-id="542ce-117">Click **Help** to access context sensitive help, such as this page.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="542ce-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="542ce-118">See also</span></span>

#### 

[<span data-ttu-id="542ce-119">在 Skype 的持久聊天服务器业务服务器 2015年计划</span><span class="sxs-lookup"><span data-stu-id="542ce-119">Plan for Persistent Chat Server in Skype for Business Server 2015</span></span>](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)
  
[<span data-ttu-id="542ce-120">持久的聊天服务器添加到您的 Skype 业务服务器 2015年拓扑</span><span class="sxs-lookup"><span data-stu-id="542ce-120">Add Persistent Chat Server to your Skype for Business Server 2015 topology</span></span>](../../deploy/deploy-persistent-chat-server/add-persistent-chat-server.md)

