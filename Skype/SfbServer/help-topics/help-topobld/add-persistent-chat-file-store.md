---
title: 添加持久聊天文件存储
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 2/8/2018
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddPersistentChatFileStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e1068706-ff61-4a98-8e51-4202111d936a
description: 必须为 Standard Edition Server 或 Enterprise Edition 前端池指定用作文件存储的文件共享。可以将现有的文件共享用作文件存储，也可以通过指定文件共享所在的文件服务器的完全限定域名 (FQDN) 和新文件共享的文件夹名称来指定新的文件共享。
ms.openlocfilehash: 76b116d469bf6369174815d6b396a64149518f17
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="add-persistent-chat-file-store"></a><span data-ttu-id="77473-104">添加持久聊天文件存储</span><span class="sxs-lookup"><span data-stu-id="77473-104">Add Persistent Chat File Store</span></span>
 
<span data-ttu-id="77473-p102">必须为 Standard Edition Server 或 Enterprise Edition 前端池指定用作文件存储的文件共享。可以将现有的文件共享用作文件存储，也可以通过指定文件共享所在的文件服务器的完全限定域名 (FQDN) 和新文件共享的文件夹名称来指定新的文件共享。</span><span class="sxs-lookup"><span data-stu-id="77473-p102">You must specify a file share to be used as the file store for the Standard Edition server or Enterprise Edition Front End pool. You can use an existing file share for the file store or you can specify a new file share by specifying the fully qualified domain name (FQDN) of the file server on which the file share is to be located and a folder name for the new file share.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="77473-107">Skype 业务服务器的文件共享不能位于企业版前端服务器，但可以位于标准版服务器上。</span><span class="sxs-lookup"><span data-stu-id="77473-107">The file share for Skype for Business Server cannot be located on the Enterprise Edition Front End Server, but can be located on a Standard Edition server.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="77473-108">可以先在拓扑生成器中定义文件共享，再创建文件共享，但是必须在发布拓扑前在定义的位置创建文件共享。</span><span class="sxs-lookup"><span data-stu-id="77473-108">You can define the file share in Topology Builder before you create the file share, but you must create the file share in the defined location you define before you publish the topology.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="77473-109">当添加持久性的聊天服务器或池对拓扑，拓扑生成器必须能够设置文件的持久聊天服务器存储和配置自由访问控制列表 (Dacl) 用于文件存储的文件共享上。</span><span class="sxs-lookup"><span data-stu-id="77473-109">When you add a Persistent Chat Server or Persistent Chat Server pool to your topology, Topology Builder must be able to set up the file store and configure discretionary access control lists (DACLs) on the file share to be used for the file store.</span></span> <span data-ttu-id="77473-110">这就要求在运行拓扑生成器以发布新拓扑时，需使用对文件共享具有完全控制权限（读/写/修改）的帐户登录。</span><span class="sxs-lookup"><span data-stu-id="77473-110">This requires that, when you run Topology Builder to publish the new topology, you are logged on with an account that has full control permissions (read/write/modify) for the file share.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="77473-111">另请参阅</span><span class="sxs-lookup"><span data-stu-id="77473-111">See also</span></span>

#### 

[<span data-ttu-id="77473-112">在 Skype 的持久聊天服务器业务服务器 2015年计划</span><span class="sxs-lookup"><span data-stu-id="77473-112">Plan for Persistent Chat Server in Skype for Business Server 2015</span></span>](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)
  
[<span data-ttu-id="77473-113">持久的聊天服务器添加到您的 Skype 业务服务器 2015年拓扑</span><span class="sxs-lookup"><span data-stu-id="77473-113">Add Persistent Chat Server to your Skype for Business Server 2015 topology</span></span>](../../deploy/deploy-persistent-chat-server/add-persistent-chat-server.md)
  
[<span data-ttu-id="77473-114">硬件和软件要求在 Skype 的持久聊天服务器的业务服务器 2015</span><span class="sxs-lookup"><span data-stu-id="77473-114">Hardware and software requirements for Persistent Chat Server in Skype for Business Server 2015</span></span>](../../plan-your-deployment/persistent-chat-server/hardware-and-software-requirements.md)
  
[<span data-ttu-id="77473-115">业务服务器 2015 Skype 的的服务要求</span><span class="sxs-lookup"><span data-stu-id="77473-115">Server requirements for Skype for Business Server 2015</span></span>](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)
  
[<span data-ttu-id="77473-116">Skype 业务服务器 2015年拓扑结构基础知识</span><span class="sxs-lookup"><span data-stu-id="77473-116">Topology Basics for Skype for Business Server 2015</span></span>](../../plan-your-deployment/topology-basics/topology-basics.md)

