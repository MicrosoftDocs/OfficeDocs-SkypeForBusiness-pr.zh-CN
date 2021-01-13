---
title: Skype for Business Server 中的架构更改
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 10/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: d760cb93-77d4-4d64-adb7-416b808f36f8
description: 在部署和运行 Skype for Business Server 之前，必须通过扩展架构来准备 Active Directory 域服务。 架构扩展将添加 Skype for Business Server 所需的类和属性。
ms.openlocfilehash: 4ca18b0ccfde6b247f1c29e140004804462d0f56
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813572"
---
# <a name="schema-changes-in-skype-for-business-server"></a><span data-ttu-id="f9000-104">Skype for Business Server 中的架构更改</span><span class="sxs-lookup"><span data-stu-id="f9000-104">Schema changes in Skype for Business Server</span></span>
 
<span data-ttu-id="f9000-105">在部署和运行 Skype for Business Server 之前，必须通过扩展架构来准备 Active Directory 域服务。</span><span class="sxs-lookup"><span data-stu-id="f9000-105">Before you deploy and operate Skype for Business Server, you must prepare Active Directory Domain Services by extending the schema.</span></span> <span data-ttu-id="f9000-106">架构扩展将添加 Skype for Business Server 所需的类和属性。</span><span class="sxs-lookup"><span data-stu-id="f9000-106">The schema extensions add the classes and attributes that are required by Skype for Business Server.</span></span>

> [!NOTE]
> <span data-ttu-id="f9000-107">如果要从 Lync Server 2013 升级到 Skype for Business Server 2015，则不进行架构更改，因此本文不适用。</span><span class="sxs-lookup"><span data-stu-id="f9000-107">If you are upgrading from Lync Server 2013 to Skype for Business Server 2015, no schema changes are made and therefore this article does not apply.</span></span>
  
<span data-ttu-id="f9000-108">Skype for Business Server 需要几个新的类和属性，并修改一些现有的类和属性。</span><span class="sxs-lookup"><span data-stu-id="f9000-108">Skype for Business Server requires several new classes and attributes and modifies some existing classes and attributes.</span></span> <span data-ttu-id="f9000-109">此外，Skype for Business Server 的很多配置信息都存储在中央管理存储中，而不是像以前版本一样存储在 AD DS 中。</span><span class="sxs-lookup"><span data-stu-id="f9000-109">In addition, much configuration information for Skype for Business Server is stored in the Central Management store instead of in AD DS as in previous versions.</span></span> <span data-ttu-id="f9000-110">以下信息仍存储在 Skype for Business Server 中的 AD DS 中：</span><span class="sxs-lookup"><span data-stu-id="f9000-110">The following information is still stored in AD DS in Skype for Business Server:</span></span>
  
- <span data-ttu-id="f9000-111">**架构扩展**：</span><span class="sxs-lookup"><span data-stu-id="f9000-111">**Schema extensions**:</span></span>
    
  - <span data-ttu-id="f9000-112">用户对象扩展</span><span class="sxs-lookup"><span data-stu-id="f9000-112">User object extensions</span></span>
    
  - <span data-ttu-id="f9000-113">用于维护与受支持的早期版本的 Lync Server 的向后兼容性的类扩展。</span><span class="sxs-lookup"><span data-stu-id="f9000-113">Extensions for classes to maintain backward compatibility with supported previous versions of Lync Server.</span></span>
    
- <span data-ttu-id="f9000-114">**数据存储** (Skype for Business Server 扩展架构和现有架构类) ：</span><span class="sxs-lookup"><span data-stu-id="f9000-114">**Data** (stored in Skype for Business Server extended schema and in existing schema classes):</span></span>
    
  - <span data-ttu-id="f9000-115">用户 SIP 统一资源标识符 (URI) 和其他用户设置</span><span class="sxs-lookup"><span data-stu-id="f9000-115">User SIP Uniform Resource Identifier (URI) and other user settings</span></span>
    
  - <span data-ttu-id="f9000-116">应用程序（如响应组和会议助理）的联系人对象</span><span class="sxs-lookup"><span data-stu-id="f9000-116">Contact objects for applications such as Response Group and Conferencing Attendant</span></span>
    
  - <span data-ttu-id="f9000-117">指向中央管理存储的指针</span><span class="sxs-lookup"><span data-stu-id="f9000-117">A pointer to the Central Management store</span></span>
    
  - <span data-ttu-id="f9000-118">Kerberos 身份验证帐户（可选计算机对象）</span><span class="sxs-lookup"><span data-stu-id="f9000-118">Kerberos Authentication Account (an optional computer object)</span></span>
    
<span data-ttu-id="f9000-119">本主题介绍 Skype for Business Server 所需的 Active Directory 架构更改。</span><span class="sxs-lookup"><span data-stu-id="f9000-119">This topic describes the Active Directory schema changes required by Skype for Business Server.</span></span> <span data-ttu-id="f9000-120">它未介绍 Office Communications Server 早期版本引入的架构更改。</span><span class="sxs-lookup"><span data-stu-id="f9000-120">It does not describe schema changes that were introduced by previous versions of Office Communications Server.</span></span> <span data-ttu-id="f9000-121">有关类及其说明的列表，请参阅 Skype for Business Server 中的架构 [类和说明](schema-classes-and-descriptions.md)。</span><span class="sxs-lookup"><span data-stu-id="f9000-121">For a list of classes and their descriptions, see [Schema classes and descriptions in Skype for Business Server](schema-classes-and-descriptions.md).</span></span> <span data-ttu-id="f9000-122">有关属性及其说明的列表，请参阅 Skype for Business Server 中的架构属性 [和说明](schema-attributes-and-descriptions.md)。</span><span class="sxs-lookup"><span data-stu-id="f9000-122">For a list of attributes and their descriptions, see [Schema attributes and descriptions in Skype for Business Server](schema-attributes-and-descriptions.md).</span></span> <span data-ttu-id="f9000-123">有关包含其可能包含的属性的类的列表，请参阅 Skype for Business Server 中按 [类分类的架构属性](schema-attributes-by-class.md)。</span><span class="sxs-lookup"><span data-stu-id="f9000-123">For a list of classes with the attributes they may contain, see [Schema attributes by class in Skype for Business Server](schema-attributes-by-class.md).</span></span>
  
<span data-ttu-id="f9000-124">msRTCSIP 前缀标识特定于 Skype for Business Server 的类和属性。</span><span class="sxs-lookup"><span data-stu-id="f9000-124">The msRTCSIP prefix identifies classes and attributes that are specific to Skype for Business Server.</span></span>
  
## <a name="new-active-directory-attributes"></a><span data-ttu-id="f9000-125">新增 Active Directory 属性</span><span class="sxs-lookup"><span data-stu-id="f9000-125">New Active Directory Attributes</span></span>

<span data-ttu-id="f9000-126">下表介绍了由 Skype for Business Server 添加的 Active Directory 属性。</span><span class="sxs-lookup"><span data-stu-id="f9000-126">The following table describes the Active Directory attributes that are added by Skype for Business Server.</span></span>
  
<span data-ttu-id="f9000-127">**由 Skype for Business Server 添加的属性**</span><span class="sxs-lookup"><span data-stu-id="f9000-127">**Attributes Added by Skype for Business Server**</span></span>

|<span data-ttu-id="f9000-128">**属性**</span><span class="sxs-lookup"><span data-stu-id="f9000-128">**Attribute**</span></span>|<span data-ttu-id="f9000-129">**说明**</span><span class="sxs-lookup"><span data-stu-id="f9000-129">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="f9000-130">msExchUserHoldPolicies</span><span class="sxs-lookup"><span data-stu-id="f9000-130">msExchUserHoldPolicies</span></span>  <br/> |<span data-ttu-id="f9000-131">此多值属性可保存应用于用户的保留策略的标识符。</span><span class="sxs-lookup"><span data-stu-id="f9000-131">This multi-value attribute holds identifiers for hold policies that apply to the user.</span></span> <span data-ttu-id="f9000-132">保留策略会在保留持续时间内保留用户的邮箱项目。</span><span class="sxs-lookup"><span data-stu-id="f9000-132">Hold policies preserve mailbox items for the user for the duration of the hold.</span></span> <span data-ttu-id="f9000-133">此属性与 Exchange 2013 共享。</span><span class="sxs-lookup"><span data-stu-id="f9000-133">This attribute is shared with Exchange 2013.</span></span>  <br/> |
|<span data-ttu-id="f9000-134">msRTCSIP-UserRoutingGroupId</span><span class="sxs-lookup"><span data-stu-id="f9000-134">msRTCSIP-UserRoutingGroupId</span></span>  <br/> |<span data-ttu-id="f9000-p106">这是 SIP 路由组 ID。同一组中的用户将注册到同一前端服务器。</span><span class="sxs-lookup"><span data-stu-id="f9000-p106">This is the SIP routing group ID. Users in the same group will register to the same Front End Server.</span></span>  <br/> |
|<span data-ttu-id="f9000-137">msRTCSIP-MirrorBackEndServer</span><span class="sxs-lookup"><span data-stu-id="f9000-137">msRTCSIP-MirrorBackEndServer</span></span>  <br/> |<span data-ttu-id="f9000-138">此属性用于存储前端池SQL Server后端的镜像池。</span><span class="sxs-lookup"><span data-stu-id="f9000-138">This attribute is used to store the mirrored SQL Server backend used by the Front End pool.</span></span>  <br/> |
   
## <a name="modified-active-directory-classes"></a><span data-ttu-id="f9000-139">修改的 Active Directory 类</span><span class="sxs-lookup"><span data-stu-id="f9000-139">Modified Active Directory Classes</span></span>

<span data-ttu-id="f9000-140">下表介绍了由 Skype for Business Server 修改的 Active Directory 类。</span><span class="sxs-lookup"><span data-stu-id="f9000-140">The following table describes the Active Directory classes that are modified by Skype for Business Server.</span></span>
  
<span data-ttu-id="f9000-141">**由 Skype for Business Server 修改的类**</span><span class="sxs-lookup"><span data-stu-id="f9000-141">**Classes Modified by Skype for Business Server**</span></span>

|<span data-ttu-id="f9000-142">**类**</span><span class="sxs-lookup"><span data-stu-id="f9000-142">**Class**</span></span>|<span data-ttu-id="f9000-143">**更改**</span><span class="sxs-lookup"><span data-stu-id="f9000-143">**Change**</span></span>|<span data-ttu-id="f9000-144">**类或属性**</span><span class="sxs-lookup"><span data-stu-id="f9000-144">**Class or Attribute**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="f9000-145">用户</span><span class="sxs-lookup"><span data-stu-id="f9000-145">User</span></span>  <br/> |<span data-ttu-id="f9000-146">add:mayContain</span><span class="sxs-lookup"><span data-stu-id="f9000-146">add: mayContain</span></span>  <br/> <span data-ttu-id="f9000-147">add:mayContain</span><span class="sxs-lookup"><span data-stu-id="f9000-147">add: mayContain</span></span>  <br/> |<span data-ttu-id="f9000-148">ProxyAddresses</span><span class="sxs-lookup"><span data-stu-id="f9000-148">ProxyAddresses</span></span>  <br/> <span data-ttu-id="f9000-149">msRTCSIP-UserRoutingGroupId</span><span class="sxs-lookup"><span data-stu-id="f9000-149">msRTCSIP-UserRoutingGroupId</span></span>  <br/> |
|<span data-ttu-id="f9000-150">Contact</span><span class="sxs-lookup"><span data-stu-id="f9000-150">Contact</span></span>  <br/> |<span data-ttu-id="f9000-151">add:mayContain</span><span class="sxs-lookup"><span data-stu-id="f9000-151">add: mayContain</span></span>  <br/> <span data-ttu-id="f9000-152">add:mayContain</span><span class="sxs-lookup"><span data-stu-id="f9000-152">add: mayContain</span></span>  <br/> |<span data-ttu-id="f9000-153">ProxyAddresses</span><span class="sxs-lookup"><span data-stu-id="f9000-153">ProxyAddresses</span></span>  <br/> <span data-ttu-id="f9000-154">msRTCSIP-UserRoutingGroupId</span><span class="sxs-lookup"><span data-stu-id="f9000-154">msRTCSIP-UserRoutingGroupId</span></span>  <br/> |
|<span data-ttu-id="f9000-155">Mail-Recipient</span><span class="sxs-lookup"><span data-stu-id="f9000-155">Mail-Recipient</span></span>  <br/> |<span data-ttu-id="f9000-156">add:mayContain</span><span class="sxs-lookup"><span data-stu-id="f9000-156">add: mayContain</span></span>  <br/> |<span data-ttu-id="f9000-157">msExchUserHoldPolicies</span><span class="sxs-lookup"><span data-stu-id="f9000-157">msExchUserHoldPolicies</span></span>  <br/> |
|<span data-ttu-id="f9000-158">msRTCSIP-GlobalTopologySetting</span><span class="sxs-lookup"><span data-stu-id="f9000-158">msRTCSIP-GlobalTopologySetting</span></span>  <br/> |<span data-ttu-id="f9000-159">add:mayContain</span><span class="sxs-lookup"><span data-stu-id="f9000-159">add: mayContain</span></span>  <br/> |<span data-ttu-id="f9000-160">msRTCSIP-MirrorBackEndServer</span><span class="sxs-lookup"><span data-stu-id="f9000-160">msRTCSIP-MirrorBackEndServer</span></span>  <br/> |
   

