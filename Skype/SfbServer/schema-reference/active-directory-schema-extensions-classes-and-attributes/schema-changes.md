---
title: Skype for Business 服务器中的架构更改
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 10/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: d760cb93-77d4-4d64-adb7-416b808f36f8
description: 在部署和操作 Skype for Business 服务器之前, 必须通过扩展架构来准备 Active Directory 域服务。 架构扩展添加 Skype for Business 服务器所需的类和属性。
ms.openlocfilehash: 34f97f7a37adc23635f938fb12c9a72e22429538
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34296656"
---
# <a name="schema-changes-in-skype-for-business-server"></a><span data-ttu-id="ce24d-104">Skype for Business 服务器中的架构更改</span><span class="sxs-lookup"><span data-stu-id="ce24d-104">Schema changes in Skype for Business Server</span></span>
 
<span data-ttu-id="ce24d-105">在部署和操作 Skype for Business 服务器之前, 必须通过扩展架构来准备 Active Directory 域服务。</span><span class="sxs-lookup"><span data-stu-id="ce24d-105">Before you deploy and operate Skype for Business Server, you must prepare Active Directory Domain Services by extending the schema.</span></span> <span data-ttu-id="ce24d-106">架构扩展添加 Skype for Business 服务器所需的类和属性。</span><span class="sxs-lookup"><span data-stu-id="ce24d-106">The schema extensions add the classes and attributes that are required by Skype for Business Server.</span></span>

> [!NOTE]
> <span data-ttu-id="ce24d-107">如果要从 Lync Server 2013 升级到 Skype for business Server 2015, 则不会进行任何架构更改, 因此本文不适用。</span><span class="sxs-lookup"><span data-stu-id="ce24d-107">If you are upgrading from Lync Server 2013 to Skype for Business Server 2015, no schema changes are made and therefore this article does not apply.</span></span>
  
<span data-ttu-id="ce24d-108">Skype for business 服务器需要多个新的类和属性, 并修改一些现有的类和属性。</span><span class="sxs-lookup"><span data-stu-id="ce24d-108">Skype for Business Server requires several new classes and attributes and modifies some existing classes and attributes.</span></span> <span data-ttu-id="ce24d-109">此外, Skype for business 服务器的许多配置信息存储在中央管理存储中, 而不是在 AD DS 中, 就像在以前的版本中一样。</span><span class="sxs-lookup"><span data-stu-id="ce24d-109">In addition, much configuration information for Skype for Business Server is stored in the Central Management store instead of in AD DS as in previous versions.</span></span> <span data-ttu-id="ce24d-110">以下信息仍存储在 Skype for business Server 的 AD DS 中:</span><span class="sxs-lookup"><span data-stu-id="ce24d-110">The following information is still stored in AD DS in Skype for Business Server:</span></span>
  
- <span data-ttu-id="ce24d-111">**架构扩展**:</span><span class="sxs-lookup"><span data-stu-id="ce24d-111">**Schema extensions**:</span></span>
    
  - <span data-ttu-id="ce24d-112">用户对象扩展</span><span class="sxs-lookup"><span data-stu-id="ce24d-112">User object extensions</span></span>
    
  - <span data-ttu-id="ce24d-113">用于维护与受支持的早期版本 Lync Server 的向后兼容性的类扩展。</span><span class="sxs-lookup"><span data-stu-id="ce24d-113">Extensions for classes to maintain backward compatibility with supported previous versions of Lync Server.</span></span>
    
- <span data-ttu-id="ce24d-114">**数据**(存储在 Skype for business Server 扩展架构和现有架构类中):</span><span class="sxs-lookup"><span data-stu-id="ce24d-114">**Data** (stored in Skype for Business Server extended schema and in existing schema classes):</span></span>
    
  - <span data-ttu-id="ce24d-115">用户 SIP 统一资源标识符 (URI) 和其他用户设置</span><span class="sxs-lookup"><span data-stu-id="ce24d-115">User SIP Uniform Resource Identifier (URI) and other user settings</span></span>
    
  - <span data-ttu-id="ce24d-116">响应组和会议助理等应用程序的联系人对象</span><span class="sxs-lookup"><span data-stu-id="ce24d-116">Contact objects for applications such as Response Group and Conferencing Attendant</span></span>
    
  - <span data-ttu-id="ce24d-117">指向中央管理存储的指针</span><span class="sxs-lookup"><span data-stu-id="ce24d-117">A pointer to the Central Management store</span></span>
    
  - <span data-ttu-id="ce24d-118">Kerberos 身份验证帐户 (可选的计算机对象)</span><span class="sxs-lookup"><span data-stu-id="ce24d-118">Kerberos Authentication Account (an optional computer object)</span></span>
    
<span data-ttu-id="ce24d-119">本主题介绍了 Skype for Business 服务器所需的 Active Directory 架构更改。</span><span class="sxs-lookup"><span data-stu-id="ce24d-119">This topic describes the Active Directory schema changes required by Skype for Business Server.</span></span> <span data-ttu-id="ce24d-120">它不会描述以前版本的 Office 通信服务器引入的架构更改。</span><span class="sxs-lookup"><span data-stu-id="ce24d-120">It does not describe schema changes that were introduced by previous versions of Office Communications Server.</span></span> <span data-ttu-id="ce24d-121">有关类及其说明的列表, 请参阅[Skype For Business 服务器中的架构类和说明](schema-classes-and-descriptions.md)。</span><span class="sxs-lookup"><span data-stu-id="ce24d-121">For a list of classes and their descriptions, see [Schema classes and descriptions in Skype for Business Server](schema-classes-and-descriptions.md).</span></span> <span data-ttu-id="ce24d-122">有关属性及其说明的列表, 请参阅[Skype For Business 服务器中的架构属性和说明](schema-attributes-and-descriptions.md)。</span><span class="sxs-lookup"><span data-stu-id="ce24d-122">For a list of attributes and their descriptions, see [Schema attributes and descriptions in Skype for Business Server](schema-attributes-and-descriptions.md).</span></span> <span data-ttu-id="ce24d-123">有关它们可能包含的属性的类的列表, 请参阅[Skype For Business 服务器中按类列出的架构属性](schema-attributes-by-class.md)。</span><span class="sxs-lookup"><span data-stu-id="ce24d-123">For a list of classes with the attributes they may contain, see [Schema attributes by class in Skype for Business Server](schema-attributes-by-class.md).</span></span>
  
<span data-ttu-id="ce24d-124">MsRTCSIP 前缀标识特定于 Skype for Business 服务器的类和属性。</span><span class="sxs-lookup"><span data-stu-id="ce24d-124">The msRTCSIP prefix identifies classes and attributes that are specific to Skype for Business Server.</span></span>
  
## <a name="new-active-directory-attributes"></a><span data-ttu-id="ce24d-125">新的 Active Directory 属性</span><span class="sxs-lookup"><span data-stu-id="ce24d-125">New Active Directory Attributes</span></span>

<span data-ttu-id="ce24d-126">下表介绍了由 Skype for Business 服务器添加的 Active Directory 属性。</span><span class="sxs-lookup"><span data-stu-id="ce24d-126">The following table describes the Active Directory attributes that are added by Skype for Business Server.</span></span>
  
<span data-ttu-id="ce24d-127">**Skype for Business 服务器添加的属性**</span><span class="sxs-lookup"><span data-stu-id="ce24d-127">**Attributes Added by Skype for Business Server**</span></span>

|<span data-ttu-id="ce24d-128">**属性**</span><span class="sxs-lookup"><span data-stu-id="ce24d-128">**Attribute**</span></span>|<span data-ttu-id="ce24d-129">**说明**</span><span class="sxs-lookup"><span data-stu-id="ce24d-129">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="ce24d-130">msExchUserHoldPolicies</span><span class="sxs-lookup"><span data-stu-id="ce24d-130">msExchUserHoldPolicies</span></span>  <br/> |<span data-ttu-id="ce24d-131">此多值属性包含适用于用户的保留策略的标识符。</span><span class="sxs-lookup"><span data-stu-id="ce24d-131">This multi-value attribute holds identifiers for hold policies that apply to the user.</span></span> <span data-ttu-id="ce24d-132">保留策略在保留期间保留用户的邮箱项目。</span><span class="sxs-lookup"><span data-stu-id="ce24d-132">Hold policies preserve mailbox items for the user for the duration of the hold.</span></span> <span data-ttu-id="ce24d-133">此属性是与 Exchange 2013 共享的。</span><span class="sxs-lookup"><span data-stu-id="ce24d-133">This attribute is shared with Exchange 2013.</span></span>  <br/> |
|<span data-ttu-id="ce24d-134">msRTCSIP-UserRoutingGroupId</span><span class="sxs-lookup"><span data-stu-id="ce24d-134">msRTCSIP-UserRoutingGroupId</span></span>  <br/> |<span data-ttu-id="ce24d-135">这是 SIP 路由组 ID。</span><span class="sxs-lookup"><span data-stu-id="ce24d-135">This is the SIP routing group ID.</span></span> <span data-ttu-id="ce24d-136">同一组中的用户将注册到同一前端服务器。</span><span class="sxs-lookup"><span data-stu-id="ce24d-136">Users in the same group will register to the same Front End Server.</span></span>  <br/> |
|<span data-ttu-id="ce24d-137">msRTCSIP-MirrorBackEndServer</span><span class="sxs-lookup"><span data-stu-id="ce24d-137">msRTCSIP-MirrorBackEndServer</span></span>  <br/> |<span data-ttu-id="ce24d-138">此属性用于存储前端池使用的镜像 SQL Server 后端。</span><span class="sxs-lookup"><span data-stu-id="ce24d-138">This attribute is used to store the mirrored SQL Server backend used by the Front End pool.</span></span>  <br/> |
   
## <a name="modified-active-directory-classes"></a><span data-ttu-id="ce24d-139">已修改的 Active Directory 类</span><span class="sxs-lookup"><span data-stu-id="ce24d-139">Modified Active Directory Classes</span></span>

<span data-ttu-id="ce24d-140">下表介绍了由 Skype for Business Server 修改的 Active Directory 类。</span><span class="sxs-lookup"><span data-stu-id="ce24d-140">The following table describes the Active Directory classes that are modified by Skype for Business Server.</span></span>
  
<span data-ttu-id="ce24d-141">**Skype for Business Server 修改的类**</span><span class="sxs-lookup"><span data-stu-id="ce24d-141">**Classes Modified by Skype for Business Server**</span></span>

|<span data-ttu-id="ce24d-142">**种类**</span><span class="sxs-lookup"><span data-stu-id="ce24d-142">**Class**</span></span>|<span data-ttu-id="ce24d-143">**更改**</span><span class="sxs-lookup"><span data-stu-id="ce24d-143">**Change**</span></span>|<span data-ttu-id="ce24d-144">**类或属性**</span><span class="sxs-lookup"><span data-stu-id="ce24d-144">**Class or Attribute**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="ce24d-145">用户</span><span class="sxs-lookup"><span data-stu-id="ce24d-145">User</span></span>  <br/> |<span data-ttu-id="ce24d-146">add: mayContain</span><span class="sxs-lookup"><span data-stu-id="ce24d-146">add: mayContain</span></span>  <br/> <span data-ttu-id="ce24d-147">add: mayContain</span><span class="sxs-lookup"><span data-stu-id="ce24d-147">add: mayContain</span></span>  <br/> |<span data-ttu-id="ce24d-148">ProxyAddresses</span><span class="sxs-lookup"><span data-stu-id="ce24d-148">ProxyAddresses</span></span>  <br/> <span data-ttu-id="ce24d-149">msRTCSIP-UserRoutingGroupId</span><span class="sxs-lookup"><span data-stu-id="ce24d-149">msRTCSIP-UserRoutingGroupId</span></span>  <br/> |
|<span data-ttu-id="ce24d-150">联系人</span><span class="sxs-lookup"><span data-stu-id="ce24d-150">Contact</span></span>  <br/> |<span data-ttu-id="ce24d-151">add: mayContain</span><span class="sxs-lookup"><span data-stu-id="ce24d-151">add: mayContain</span></span>  <br/> <span data-ttu-id="ce24d-152">add: mayContain</span><span class="sxs-lookup"><span data-stu-id="ce24d-152">add: mayContain</span></span>  <br/> |<span data-ttu-id="ce24d-153">ProxyAddresses</span><span class="sxs-lookup"><span data-stu-id="ce24d-153">ProxyAddresses</span></span>  <br/> <span data-ttu-id="ce24d-154">msRTCSIP-UserRoutingGroupId</span><span class="sxs-lookup"><span data-stu-id="ce24d-154">msRTCSIP-UserRoutingGroupId</span></span>  <br/> |
|<span data-ttu-id="ce24d-155">邮件-收件人</span><span class="sxs-lookup"><span data-stu-id="ce24d-155">Mail-Recipient</span></span>  <br/> |<span data-ttu-id="ce24d-156">add: mayContain</span><span class="sxs-lookup"><span data-stu-id="ce24d-156">add: mayContain</span></span>  <br/> |<span data-ttu-id="ce24d-157">msExchUserHoldPolicies</span><span class="sxs-lookup"><span data-stu-id="ce24d-157">msExchUserHoldPolicies</span></span>  <br/> |
|<span data-ttu-id="ce24d-158">msRTCSIP-GlobalTopologySetting</span><span class="sxs-lookup"><span data-stu-id="ce24d-158">msRTCSIP-GlobalTopologySetting</span></span>  <br/> |<span data-ttu-id="ce24d-159">add: mayContain</span><span class="sxs-lookup"><span data-stu-id="ce24d-159">add: mayContain</span></span>  <br/> |<span data-ttu-id="ce24d-160">msRTCSIP-MirrorBackEndServer</span><span class="sxs-lookup"><span data-stu-id="ce24d-160">msRTCSIP-MirrorBackEndServer</span></span>  <br/> |
   

