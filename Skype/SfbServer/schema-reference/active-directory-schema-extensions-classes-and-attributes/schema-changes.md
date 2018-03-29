---
title: 在 Skype 业务服务器的架构更改
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 10/20/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: d760cb93-77d4-4d64-adb7-416b808f36f8
description: 在部署和运行 Skype 业务服务器之前，您必须通过扩展架构准备 Active Directory 域服务。 架构扩展添加的类和属性所需的 Skype 业务服务器。
ms.openlocfilehash: 42b4417311c557323535aa03053ccb03d95cc840
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="schema-changes-in-skype-for-business-server"></a><span data-ttu-id="c99b8-104">在 Skype 业务服务器的架构更改</span><span class="sxs-lookup"><span data-stu-id="c99b8-104">Schema changes in Skype for Business Server</span></span>
 
<span data-ttu-id="c99b8-105">在部署和运行 Skype 业务服务器之前，您必须通过扩展架构准备 Active Directory 域服务。</span><span class="sxs-lookup"><span data-stu-id="c99b8-105">Before you deploy and operate Skype for Business Server, you must prepare Active Directory Domain Services by extending the schema.</span></span> <span data-ttu-id="c99b8-106">架构扩展添加的类和属性所需的 Skype 业务服务器。</span><span class="sxs-lookup"><span data-stu-id="c99b8-106">The schema extensions add the classes and attributes that are required by Skype for Business Server.</span></span> 
  
<span data-ttu-id="c99b8-107">Skype 业务服务器需要多个新类和属性和修改一些现有的类和属性。</span><span class="sxs-lookup"><span data-stu-id="c99b8-107">Skype for Business Server requires several new classes and attributes and modifies some existing classes and attributes.</span></span> <span data-ttu-id="c99b8-108">此外，多为 Skype 业务服务器的配置信息存储在 AD DS 中而不是中央管理存储以前版本中。</span><span class="sxs-lookup"><span data-stu-id="c99b8-108">In addition, much configuration information for Skype for Business Server is stored in the Central Management store instead of in AD DS as in previous versions.</span></span> <span data-ttu-id="c99b8-109">以下信息仍在 Skype 在 AD DS 中存储业务服务器：</span><span class="sxs-lookup"><span data-stu-id="c99b8-109">The following information is still stored in AD DS in Skype for Business Server:</span></span>
  
- <span data-ttu-id="c99b8-110">**架构扩展**：</span><span class="sxs-lookup"><span data-stu-id="c99b8-110">**Schema extensions**:</span></span>
    
  - <span data-ttu-id="c99b8-111">用户对象扩展</span><span class="sxs-lookup"><span data-stu-id="c99b8-111">User object extensions</span></span>
    
  - <span data-ttu-id="c99b8-112">类维护向后兼容 Lync Server 支持以前版本的扩展。</span><span class="sxs-lookup"><span data-stu-id="c99b8-112">Extensions for classes to maintain backward compatibility with supported previous versions of Lync Server.</span></span>
    
- <span data-ttu-id="c99b8-113">**数据**（存储在业务服务器扩展架构的 Skype 和现有架构类）：</span><span class="sxs-lookup"><span data-stu-id="c99b8-113">**Data** (stored in Skype for Business Server extended schema and in existing schema classes):</span></span>
    
  - <span data-ttu-id="c99b8-114">用户的 SIP 统一资源标识符 (URI) 和其他用户设置</span><span class="sxs-lookup"><span data-stu-id="c99b8-114">User SIP Uniform Resource Identifier (URI) and other user settings</span></span>
    
  - <span data-ttu-id="c99b8-115">联系人对象的应用程序响应组和会议助理等</span><span class="sxs-lookup"><span data-stu-id="c99b8-115">Contact objects for applications such as Response Group and Conferencing Attendant</span></span>
    
  - <span data-ttu-id="c99b8-116">一个指针，指向中央管理存储</span><span class="sxs-lookup"><span data-stu-id="c99b8-116">A pointer to the Central Management store</span></span>
    
  - <span data-ttu-id="c99b8-117">Kerberos 身份验证帐户 （可选计算机对象）</span><span class="sxs-lookup"><span data-stu-id="c99b8-117">Kerberos Authentication Account (an optional computer object)</span></span>
    
<span data-ttu-id="c99b8-118">本主题介绍通过 Skype 所需业务服务器的 Active Directory 架构变化。</span><span class="sxs-lookup"><span data-stu-id="c99b8-118">This topic describes the Active Directory schema changes required by Skype for Business Server.</span></span> <span data-ttu-id="c99b8-119">它不描述引入的以前版本的 Office 通信服务器的架构更改。</span><span class="sxs-lookup"><span data-stu-id="c99b8-119">It does not describe schema changes that were introduced by previous versions of Office Communications Server.</span></span> <span data-ttu-id="c99b8-120">类及其说明的列表，请参阅[架构类和 Skype 业务服务器中的说明](schema-classes-and-descriptions.md)。</span><span class="sxs-lookup"><span data-stu-id="c99b8-120">For a list of classes and their descriptions, see [Schema classes and descriptions in Skype for Business Server](schema-classes-and-descriptions.md).</span></span> <span data-ttu-id="c99b8-121">有关属性及其说明的列表，请参阅[架构属性和 Skype 业务服务器中的说明](schema-attributes-and-descriptions.md)。</span><span class="sxs-lookup"><span data-stu-id="c99b8-121">For a list of attributes and their descriptions, see [Schema attributes and descriptions in Skype for Business Server](schema-attributes-and-descriptions.md).</span></span> <span data-ttu-id="c99b8-122">具有属性的类的列表，它们可能包含，请参阅[通过 Skype 业务服务器中类的架构属性](schema-attributes-by-class.md)。</span><span class="sxs-lookup"><span data-stu-id="c99b8-122">For a list of classes with the attributes they may contain, see [Schema attributes by class in Skype for Business Server](schema-attributes-by-class.md).</span></span>
  
<span data-ttu-id="c99b8-123">MsRTCSIP 前缀标识类别和特定于 Skype 业务服务器的属性。</span><span class="sxs-lookup"><span data-stu-id="c99b8-123">The msRTCSIP prefix identifies classes and attributes that are specific to Skype for Business Server.</span></span>
  
## <a name="new-active-directory-attributes"></a><span data-ttu-id="c99b8-124">新的活动目录属性</span><span class="sxs-lookup"><span data-stu-id="c99b8-124">New Active Directory Attributes</span></span>

<span data-ttu-id="c99b8-125">下表介绍了通过 Skype 来添加业务服务器的 Active Directory 特性。</span><span class="sxs-lookup"><span data-stu-id="c99b8-125">The following table describes the Active Directory attributes that are added by Skype for Business Server.</span></span>
  
<span data-ttu-id="c99b8-126">**添加通过 Skype 业务服务器的属性**</span><span class="sxs-lookup"><span data-stu-id="c99b8-126">**Attributes Added by Skype for Business Server**</span></span>

|<span data-ttu-id="c99b8-127">**属性**</span><span class="sxs-lookup"><span data-stu-id="c99b8-127">**Attribute**</span></span>|<span data-ttu-id="c99b8-128">**说明**</span><span class="sxs-lookup"><span data-stu-id="c99b8-128">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="c99b8-129">msExchUserHoldPolicies</span><span class="sxs-lookup"><span data-stu-id="c99b8-129">msExchUserHoldPolicies</span></span>  <br/> |<span data-ttu-id="c99b8-130">此多值属性包含标识符的保留适用于用户的策略。</span><span class="sxs-lookup"><span data-stu-id="c99b8-130">This multi-value attribute holds identifiers for hold policies that apply to the user.</span></span> <span data-ttu-id="c99b8-131">保留策略的暂停的持续时间内保留该用户的邮箱项目。</span><span class="sxs-lookup"><span data-stu-id="c99b8-131">Hold policies preserve mailbox items for the user for the duration of the hold.</span></span> <span data-ttu-id="c99b8-132">此属性是与 Exchange 2013 共享。</span><span class="sxs-lookup"><span data-stu-id="c99b8-132">This attribute is shared with Exchange 2013.</span></span>  <br/> |
|<span data-ttu-id="c99b8-133">msRTCSIP UserRoutingGroupId</span><span class="sxs-lookup"><span data-stu-id="c99b8-133">msRTCSIP-UserRoutingGroupId</span></span>  <br/> |<span data-ttu-id="c99b8-134">这是 SIP 路由组 id。</span><span class="sxs-lookup"><span data-stu-id="c99b8-134">This is the SIP routing group ID.</span></span> <span data-ttu-id="c99b8-135">同一组中的用户将注册到同一前端服务器。</span><span class="sxs-lookup"><span data-stu-id="c99b8-135">Users in the same group will register to the same Front End Server.</span></span>  <br/> |
|<span data-ttu-id="c99b8-136">msRTCSIP MirrorBackEndServer</span><span class="sxs-lookup"><span data-stu-id="c99b8-136">msRTCSIP-MirrorBackEndServer</span></span>  <br/> |<span data-ttu-id="c99b8-137">此属性用于存储镜像的 SQL Server 后端前端池使用。</span><span class="sxs-lookup"><span data-stu-id="c99b8-137">This attribute is used to store the mirrored SQL Server backend used by the Front End pool.</span></span>  <br/> |
   
## <a name="modified-active-directory-classes"></a><span data-ttu-id="c99b8-138">修改后的 Active Directory 类</span><span class="sxs-lookup"><span data-stu-id="c99b8-138">Modified Active Directory Classes</span></span>

<span data-ttu-id="c99b8-139">下表描述了通过 Skype 修改的业务服务器的 Active Directory 类。</span><span class="sxs-lookup"><span data-stu-id="c99b8-139">The following table describes the Active Directory classes that are modified by Skype for Business Server.</span></span>
  
<span data-ttu-id="c99b8-140">**通过 Skype 修改的业务服务器的类**</span><span class="sxs-lookup"><span data-stu-id="c99b8-140">**Classes Modified by Skype for Business Server**</span></span>

|<span data-ttu-id="c99b8-141">**类**</span><span class="sxs-lookup"><span data-stu-id="c99b8-141">**Class**</span></span>|<span data-ttu-id="c99b8-142">**更改**</span><span class="sxs-lookup"><span data-stu-id="c99b8-142">**Change**</span></span>|<span data-ttu-id="c99b8-143">**类或属性**</span><span class="sxs-lookup"><span data-stu-id="c99b8-143">**Class or Attribute**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="c99b8-144">用户</span><span class="sxs-lookup"><span data-stu-id="c99b8-144">User</span></span>  <br/> |<span data-ttu-id="c99b8-145">添加： mayContain</span><span class="sxs-lookup"><span data-stu-id="c99b8-145">add: mayContain</span></span>  <br/> <span data-ttu-id="c99b8-146">添加： mayContain</span><span class="sxs-lookup"><span data-stu-id="c99b8-146">add: mayContain</span></span>  <br/> |<span data-ttu-id="c99b8-147">代理地址</span><span class="sxs-lookup"><span data-stu-id="c99b8-147">ProxyAddresses</span></span>  <br/> <span data-ttu-id="c99b8-148">msRTCSIP UserRoutingGroupId</span><span class="sxs-lookup"><span data-stu-id="c99b8-148">msRTCSIP-UserRoutingGroupId</span></span>  <br/> |
|<span data-ttu-id="c99b8-149">联系人</span><span class="sxs-lookup"><span data-stu-id="c99b8-149">Contact</span></span>  <br/> |<span data-ttu-id="c99b8-150">添加： mayContain</span><span class="sxs-lookup"><span data-stu-id="c99b8-150">add: mayContain</span></span>  <br/> <span data-ttu-id="c99b8-151">添加： mayContain</span><span class="sxs-lookup"><span data-stu-id="c99b8-151">add: mayContain</span></span>  <br/> |<span data-ttu-id="c99b8-152">代理地址</span><span class="sxs-lookup"><span data-stu-id="c99b8-152">ProxyAddresses</span></span>  <br/> <span data-ttu-id="c99b8-153">msRTCSIP UserRoutingGroupId</span><span class="sxs-lookup"><span data-stu-id="c99b8-153">msRTCSIP-UserRoutingGroupId</span></span>  <br/> |
|<span data-ttu-id="c99b8-154">邮件收件人</span><span class="sxs-lookup"><span data-stu-id="c99b8-154">Mail-Recipient</span></span>  <br/> |<span data-ttu-id="c99b8-155">添加： mayContain</span><span class="sxs-lookup"><span data-stu-id="c99b8-155">add: mayContain</span></span>  <br/> |<span data-ttu-id="c99b8-156">msExchUserHoldPolicies</span><span class="sxs-lookup"><span data-stu-id="c99b8-156">msExchUserHoldPolicies</span></span>  <br/> |
|<span data-ttu-id="c99b8-157">msRTCSIP GlobalTopologySetting</span><span class="sxs-lookup"><span data-stu-id="c99b8-157">msRTCSIP-GlobalTopologySetting</span></span>  <br/> |<span data-ttu-id="c99b8-158">添加： mayContain</span><span class="sxs-lookup"><span data-stu-id="c99b8-158">add: mayContain</span></span>  <br/> |<span data-ttu-id="c99b8-159">msRTCSIP MirrorBackEndServer</span><span class="sxs-lookup"><span data-stu-id="c99b8-159">msRTCSIP-MirrorBackEndServer</span></span>  <br/> |
   

