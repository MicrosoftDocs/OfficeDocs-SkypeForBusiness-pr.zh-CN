---
title: Skype 业务服务器中的架构更改
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 10/20/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: d760cb93-77d4-4d64-adb7-416b808f36f8
description: 在部署和操作 Skype 业务服务器之前，您必须通过扩展架构准备 Active Directory 域服务。 架构扩展添加的类和 Skype 业务服务器所需的属性。
ms.openlocfilehash: ba76f57197e9cd812163c8abac5f51005933eace
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/27/2019
ms.locfileid: "30874638"
---
# <a name="schema-changes-in-skype-for-business-server"></a><span data-ttu-id="fe1d7-104">Skype 业务服务器中的架构更改</span><span class="sxs-lookup"><span data-stu-id="fe1d7-104">Schema changes in Skype for Business Server</span></span>
 
<span data-ttu-id="fe1d7-105">在部署和操作 Skype 业务服务器之前，您必须通过扩展架构准备 Active Directory 域服务。</span><span class="sxs-lookup"><span data-stu-id="fe1d7-105">Before you deploy and operate Skype for Business Server, you must prepare Active Directory Domain Services by extending the schema.</span></span> <span data-ttu-id="fe1d7-106">架构扩展添加的类和 Skype 业务服务器所需的属性。</span><span class="sxs-lookup"><span data-stu-id="fe1d7-106">The schema extensions add the classes and attributes that are required by Skype for Business Server.</span></span>

> [!NOTE]
> <span data-ttu-id="fe1d7-107">如果您要为业务服务器 2015年来升级到 Skype 从 Lync Server 2013，不架构更改，因此这篇文章不适用于。</span><span class="sxs-lookup"><span data-stu-id="fe1d7-107">If you are upgrading from Lync Server 2013 to Skype for Business Server 2015, no schema changes are made and therefore this article does not apply.</span></span>
  
<span data-ttu-id="fe1d7-108">Skype 业务服务器需要多个新类和属性，并修改某些现有类和属性。</span><span class="sxs-lookup"><span data-stu-id="fe1d7-108">Skype for Business Server requires several new classes and attributes and modifies some existing classes and attributes.</span></span> <span data-ttu-id="fe1d7-109">此外，多的 Skype 业务服务器的配置信息存储在 AD DS 中而不是中央管理存储中早期版本中。</span><span class="sxs-lookup"><span data-stu-id="fe1d7-109">In addition, much configuration information for Skype for Business Server is stored in the Central Management store instead of in AD DS as in previous versions.</span></span> <span data-ttu-id="fe1d7-110">以下信息仍 Skype 中的 AD DS 中存储的业务服务器：</span><span class="sxs-lookup"><span data-stu-id="fe1d7-110">The following information is still stored in AD DS in Skype for Business Server:</span></span>
  
- <span data-ttu-id="fe1d7-111">**架构扩展**：</span><span class="sxs-lookup"><span data-stu-id="fe1d7-111">**Schema extensions**:</span></span>
    
  - <span data-ttu-id="fe1d7-112">用户对象扩展</span><span class="sxs-lookup"><span data-stu-id="fe1d7-112">User object extensions</span></span>
    
  - <span data-ttu-id="fe1d7-113">用于维护与支持的 Lync Server 的早期版本向后兼容的类的扩展。</span><span class="sxs-lookup"><span data-stu-id="fe1d7-113">Extensions for classes to maintain backward compatibility with supported previous versions of Lync Server.</span></span>
    
- <span data-ttu-id="fe1d7-114">**数据**（存储在 Skype Business Server 扩展架构和现有架构类中）：</span><span class="sxs-lookup"><span data-stu-id="fe1d7-114">**Data** (stored in Skype for Business Server extended schema and in existing schema classes):</span></span>
    
  - <span data-ttu-id="fe1d7-115">用户 SIP 统一资源标识符 (URI) 和其他用户设置</span><span class="sxs-lookup"><span data-stu-id="fe1d7-115">User SIP Uniform Resource Identifier (URI) and other user settings</span></span>
    
  - <span data-ttu-id="fe1d7-116">例如，响应组和会议助理应用程序的联系对象</span><span class="sxs-lookup"><span data-stu-id="fe1d7-116">Contact objects for applications such as Response Group and Conferencing Attendant</span></span>
    
  - <span data-ttu-id="fe1d7-117">指向中央管理存储的指针</span><span class="sxs-lookup"><span data-stu-id="fe1d7-117">A pointer to the Central Management store</span></span>
    
  - <span data-ttu-id="fe1d7-118">Kerberos 身份验证帐户 （可选计算机对象）</span><span class="sxs-lookup"><span data-stu-id="fe1d7-118">Kerberos Authentication Account (an optional computer object)</span></span>
    
<span data-ttu-id="fe1d7-119">本主题介绍 Skype 业务服务器所需的 Active Directory 架构更改。</span><span class="sxs-lookup"><span data-stu-id="fe1d7-119">This topic describes the Active Directory schema changes required by Skype for Business Server.</span></span> <span data-ttu-id="fe1d7-120">它不介绍引入由早期版本的 Office Communications Server 的架构更改。</span><span class="sxs-lookup"><span data-stu-id="fe1d7-120">It does not describe schema changes that were introduced by previous versions of Office Communications Server.</span></span> <span data-ttu-id="fe1d7-121">类及其说明的列表，请参阅[架构类和 Skype 业务服务器中的说明](schema-classes-and-descriptions.md)。</span><span class="sxs-lookup"><span data-stu-id="fe1d7-121">For a list of classes and their descriptions, see [Schema classes and descriptions in Skype for Business Server](schema-classes-and-descriptions.md).</span></span> <span data-ttu-id="fe1d7-122">有关属性及其说明的列表，请参阅[架构属性和 Skype 业务服务器中的说明](schema-attributes-and-descriptions.md)。</span><span class="sxs-lookup"><span data-stu-id="fe1d7-122">For a list of attributes and their descriptions, see [Schema attributes and descriptions in Skype for Business Server](schema-attributes-and-descriptions.md).</span></span> <span data-ttu-id="fe1d7-123">类的属性的列表，它们可能包含，请参阅[Skype 业务服务器中的类的架构属性](schema-attributes-by-class.md)。</span><span class="sxs-lookup"><span data-stu-id="fe1d7-123">For a list of classes with the attributes they may contain, see [Schema attributes by class in Skype for Business Server](schema-attributes-by-class.md).</span></span>
  
<span data-ttu-id="fe1d7-124">MsRTCSIP 前缀标识类和特定于 Skype 业务服务器的属性。</span><span class="sxs-lookup"><span data-stu-id="fe1d7-124">The msRTCSIP prefix identifies classes and attributes that are specific to Skype for Business Server.</span></span>
  
## <a name="new-active-directory-attributes"></a><span data-ttu-id="fe1d7-125">新的 Active Directory 属性</span><span class="sxs-lookup"><span data-stu-id="fe1d7-125">New Active Directory Attributes</span></span>

<span data-ttu-id="fe1d7-126">下表介绍由 Skype 业务服务器添加的 Active Directory 属性。</span><span class="sxs-lookup"><span data-stu-id="fe1d7-126">The following table describes the Active Directory attributes that are added by Skype for Business Server.</span></span>
  
<span data-ttu-id="fe1d7-127">**由 Skype 添加业务服务器的属性**</span><span class="sxs-lookup"><span data-stu-id="fe1d7-127">**Attributes Added by Skype for Business Server**</span></span>

|<span data-ttu-id="fe1d7-128">**属性**</span><span class="sxs-lookup"><span data-stu-id="fe1d7-128">**Attribute**</span></span>|<span data-ttu-id="fe1d7-129">**说明**</span><span class="sxs-lookup"><span data-stu-id="fe1d7-129">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="fe1d7-130">msExchUserHoldPolicies</span><span class="sxs-lookup"><span data-stu-id="fe1d7-130">msExchUserHoldPolicies</span></span>  <br/> |<span data-ttu-id="fe1d7-131">此多值属性包含标识符保留应用于用户的策略。</span><span class="sxs-lookup"><span data-stu-id="fe1d7-131">This multi-value attribute holds identifiers for hold policies that apply to the user.</span></span> <span data-ttu-id="fe1d7-132">保留策略保留的持续时间内保留用户的邮箱项目。</span><span class="sxs-lookup"><span data-stu-id="fe1d7-132">Hold policies preserve mailbox items for the user for the duration of the hold.</span></span> <span data-ttu-id="fe1d7-133">此属性与 Exchange 2013 共享。</span><span class="sxs-lookup"><span data-stu-id="fe1d7-133">This attribute is shared with Exchange 2013.</span></span>  <br/> |
|<span data-ttu-id="fe1d7-134">msRTCSIP UserRoutingGroupId</span><span class="sxs-lookup"><span data-stu-id="fe1d7-134">msRTCSIP-UserRoutingGroupId</span></span>  <br/> |<span data-ttu-id="fe1d7-135">这是 SIP 路由组 id。</span><span class="sxs-lookup"><span data-stu-id="fe1d7-135">This is the SIP routing group ID.</span></span> <span data-ttu-id="fe1d7-136">同一组中的用户将注册到同一个前端服务器。</span><span class="sxs-lookup"><span data-stu-id="fe1d7-136">Users in the same group will register to the same Front End Server.</span></span>  <br/> |
|<span data-ttu-id="fe1d7-137">msRTCSIP MirrorBackEndServer</span><span class="sxs-lookup"><span data-stu-id="fe1d7-137">msRTCSIP-MirrorBackEndServer</span></span>  <br/> |<span data-ttu-id="fe1d7-138">此属性用于存储的前端池使用的镜像的 SQL Server 后端。</span><span class="sxs-lookup"><span data-stu-id="fe1d7-138">This attribute is used to store the mirrored SQL Server backend used by the Front End pool.</span></span>  <br/> |
   
## <a name="modified-active-directory-classes"></a><span data-ttu-id="fe1d7-139">已修改的 Active Directory 类</span><span class="sxs-lookup"><span data-stu-id="fe1d7-139">Modified Active Directory Classes</span></span>

<span data-ttu-id="fe1d7-140">下表介绍由 Skype 修改业务服务器的 Active Directory 类。</span><span class="sxs-lookup"><span data-stu-id="fe1d7-140">The following table describes the Active Directory classes that are modified by Skype for Business Server.</span></span>
  
<span data-ttu-id="fe1d7-141">**为业务 Server 由 Skype 修改的类**</span><span class="sxs-lookup"><span data-stu-id="fe1d7-141">**Classes Modified by Skype for Business Server**</span></span>

|<span data-ttu-id="fe1d7-142">**类**</span><span class="sxs-lookup"><span data-stu-id="fe1d7-142">**Class**</span></span>|<span data-ttu-id="fe1d7-143">**更改**</span><span class="sxs-lookup"><span data-stu-id="fe1d7-143">**Change**</span></span>|<span data-ttu-id="fe1d7-144">**类或属性**</span><span class="sxs-lookup"><span data-stu-id="fe1d7-144">**Class or Attribute**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="fe1d7-145">用户</span><span class="sxs-lookup"><span data-stu-id="fe1d7-145">User</span></span>  <br/> |<span data-ttu-id="fe1d7-146">添加： mayContain</span><span class="sxs-lookup"><span data-stu-id="fe1d7-146">add: mayContain</span></span>  <br/> <span data-ttu-id="fe1d7-147">添加： mayContain</span><span class="sxs-lookup"><span data-stu-id="fe1d7-147">add: mayContain</span></span>  <br/> |<span data-ttu-id="fe1d7-148">ProxyAddresses</span><span class="sxs-lookup"><span data-stu-id="fe1d7-148">ProxyAddresses</span></span>  <br/> <span data-ttu-id="fe1d7-149">msRTCSIP UserRoutingGroupId</span><span class="sxs-lookup"><span data-stu-id="fe1d7-149">msRTCSIP-UserRoutingGroupId</span></span>  <br/> |
|<span data-ttu-id="fe1d7-150">联系人</span><span class="sxs-lookup"><span data-stu-id="fe1d7-150">Contact</span></span>  <br/> |<span data-ttu-id="fe1d7-151">添加： mayContain</span><span class="sxs-lookup"><span data-stu-id="fe1d7-151">add: mayContain</span></span>  <br/> <span data-ttu-id="fe1d7-152">添加： mayContain</span><span class="sxs-lookup"><span data-stu-id="fe1d7-152">add: mayContain</span></span>  <br/> |<span data-ttu-id="fe1d7-153">ProxyAddresses</span><span class="sxs-lookup"><span data-stu-id="fe1d7-153">ProxyAddresses</span></span>  <br/> <span data-ttu-id="fe1d7-154">msRTCSIP UserRoutingGroupId</span><span class="sxs-lookup"><span data-stu-id="fe1d7-154">msRTCSIP-UserRoutingGroupId</span></span>  <br/> |
|<span data-ttu-id="fe1d7-155">邮件收件人</span><span class="sxs-lookup"><span data-stu-id="fe1d7-155">Mail-Recipient</span></span>  <br/> |<span data-ttu-id="fe1d7-156">添加： mayContain</span><span class="sxs-lookup"><span data-stu-id="fe1d7-156">add: mayContain</span></span>  <br/> |<span data-ttu-id="fe1d7-157">msExchUserHoldPolicies</span><span class="sxs-lookup"><span data-stu-id="fe1d7-157">msExchUserHoldPolicies</span></span>  <br/> |
|<span data-ttu-id="fe1d7-158">msRTCSIP GlobalTopologySetting</span><span class="sxs-lookup"><span data-stu-id="fe1d7-158">msRTCSIP-GlobalTopologySetting</span></span>  <br/> |<span data-ttu-id="fe1d7-159">添加： mayContain</span><span class="sxs-lookup"><span data-stu-id="fe1d7-159">add: mayContain</span></span>  <br/> |<span data-ttu-id="fe1d7-160">msRTCSIP MirrorBackEndServer</span><span class="sxs-lookup"><span data-stu-id="fe1d7-160">msRTCSIP-MirrorBackEndServer</span></span>  <br/> |
   

