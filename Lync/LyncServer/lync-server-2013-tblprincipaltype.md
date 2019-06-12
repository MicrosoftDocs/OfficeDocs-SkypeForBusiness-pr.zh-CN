---
title: Lync Server 2013：tblPrincipalType
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: tblPrincipalType
ms:assetid: 32e1c1d6-80f4-4624-bf4e-b4c77d3982fa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558633(v=OCS.15)
ms:contentKeyID: 48183787
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 725d097e1e2e75b6430974a4f133cb5fa4130346
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34845719"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tblprincipaltype-in-lync-server-2013"></a><span data-ttu-id="b022e-102">Lync Server 2013 中的 tblPrincipalType</span><span class="sxs-lookup"><span data-stu-id="b022e-102">tblPrincipalType in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b022e-103">_**主题上次修改时间:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="b022e-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="b022e-104">tblPrincipalType 包含用于对 tblPrincipal 表中的内容进行分类的主体类型。</span><span class="sxs-lookup"><span data-stu-id="b022e-104">tblPrincipalType contains principal types to categorize what is in the tblPrincipal table.</span></span>

### <a name="columns"></a><span data-ttu-id="b022e-105">多</span><span class="sxs-lookup"><span data-stu-id="b022e-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b022e-106">列</span><span class="sxs-lookup"><span data-stu-id="b022e-106">Column</span></span></th>
<th><span data-ttu-id="b022e-107">类型</span><span class="sxs-lookup"><span data-stu-id="b022e-107">Type</span></span></th>
<th><span data-ttu-id="b022e-108">描述</span><span class="sxs-lookup"><span data-stu-id="b022e-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b022e-109">ptypeID</span><span class="sxs-lookup"><span data-stu-id="b022e-109">ptypeID</span></span></p></td>
<td><p><span data-ttu-id="b022e-110">smallint, not null</span><span class="sxs-lookup"><span data-stu-id="b022e-110">smallint, not null</span></span></p></td>
<td><p><span data-ttu-id="b022e-111">主体类型 ID。</span><span class="sxs-lookup"><span data-stu-id="b022e-111">Principal type ID.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b022e-112">ptypeDesc</span><span class="sxs-lookup"><span data-stu-id="b022e-112">ptypeDesc</span></span></p></td>
<td><p><span data-ttu-id="b022e-113">nvarchar (256), not null</span><span class="sxs-lookup"><span data-stu-id="b022e-113">nvarchar (256), not null</span></span></p></td>
<td><p><span data-ttu-id="b022e-114">类型的说明。</span><span class="sxs-lookup"><span data-stu-id="b022e-114">Description of the type.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b022e-115">ptypeIsSystemUser</span><span class="sxs-lookup"><span data-stu-id="b022e-115">ptypeIsSystemUser</span></span></p></td>
<td><p><span data-ttu-id="b022e-116">位, not null</span><span class="sxs-lookup"><span data-stu-id="b022e-116">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="b022e-117">如果类型对应于用于内部用途的主体, 则为 True。</span><span class="sxs-lookup"><span data-stu-id="b022e-117">True if the type corresponds to the principals that are used for internal purposes.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b022e-118">ptypeIsUser</span><span class="sxs-lookup"><span data-stu-id="b022e-118">ptypeIsUser</span></span></p></td>
<td><p><span data-ttu-id="b022e-119">位, not null</span><span class="sxs-lookup"><span data-stu-id="b022e-119">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="b022e-120">如果类型为用户类型, 则为 True。</span><span class="sxs-lookup"><span data-stu-id="b022e-120">True if the type is a user type.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="key"></a><span data-ttu-id="b022e-121">关键字</span><span class="sxs-lookup"><span data-stu-id="b022e-121">Key</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b022e-122">列</span><span class="sxs-lookup"><span data-stu-id="b022e-122">Column</span></span></th>
<th><span data-ttu-id="b022e-123">说明</span><span class="sxs-lookup"><span data-stu-id="b022e-123">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b022e-124">ptypeID</span><span class="sxs-lookup"><span data-stu-id="b022e-124">ptypeID</span></span></p></td>
<td><p><span data-ttu-id="b022e-125">主键。</span><span class="sxs-lookup"><span data-stu-id="b022e-125">Primary key.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="principal-values"></a><span data-ttu-id="b022e-126">主体值</span><span class="sxs-lookup"><span data-stu-id="b022e-126">Principal Values</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b022e-127">ID</span><span class="sxs-lookup"><span data-stu-id="b022e-127">ID</span></span></th>
<th><span data-ttu-id="b022e-128">角色</span><span class="sxs-lookup"><span data-stu-id="b022e-128">Role</span></span></th>
<th><span data-ttu-id="b022e-129">说明</span><span class="sxs-lookup"><span data-stu-id="b022e-129">Description</span></span></th>
<th><span data-ttu-id="b022e-130">用户</span><span class="sxs-lookup"><span data-stu-id="b022e-130">User</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b022e-131">1</span><span class="sxs-lookup"><span data-stu-id="b022e-131">1</span></span></p></td>
<td><p><span data-ttu-id="b022e-132">任意</span><span class="sxs-lookup"><span data-stu-id="b022e-132">Any</span></span></p></td>
<td><p><span data-ttu-id="b022e-133">没有已知类型的泛型主体。</span><span class="sxs-lookup"><span data-stu-id="b022e-133">Generic principal with no known type.</span></span> <span data-ttu-id="b022e-134">未在 tblPrincipal 表中使用。</span><span class="sxs-lookup"><span data-stu-id="b022e-134">Not used in tblPrincipal table.</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b022e-135">2</span><span class="sxs-lookup"><span data-stu-id="b022e-135">2</span></span></p></td>
<td><p><span data-ttu-id="b022e-136">AnyUser</span><span class="sxs-lookup"><span data-stu-id="b022e-136">AnyUser</span></span></p></td>
<td><p><span data-ttu-id="b022e-137">用户类型的一般主体。</span><span class="sxs-lookup"><span data-stu-id="b022e-137">Generic principal of user type.</span></span> <span data-ttu-id="b022e-138">未在 tblPrincipal 表中使用。</span><span class="sxs-lookup"><span data-stu-id="b022e-138">Not used in tblPrincipal table.</span></span></p></td>
<td><p><span data-ttu-id="b022e-139">是</span><span class="sxs-lookup"><span data-stu-id="b022e-139">Yes</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b022e-140">3</span><span class="sxs-lookup"><span data-stu-id="b022e-140">3</span></span></p></td>
<td><p><span data-ttu-id="b022e-141">AnyGroup</span><span class="sxs-lookup"><span data-stu-id="b022e-141">AnyGroup</span></span></p></td>
<td><p><span data-ttu-id="b022e-142">具有组语义的常规主体。</span><span class="sxs-lookup"><span data-stu-id="b022e-142">Generic principal with group semantic.</span></span> <span data-ttu-id="b022e-143">未在 tblPrincipal 表中使用。</span><span class="sxs-lookup"><span data-stu-id="b022e-143">Not used in tblPrincipal table.</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b022e-144">4</span><span class="sxs-lookup"><span data-stu-id="b022e-144">4</span></span></p></td>
<td><p><span data-ttu-id="b022e-145">SystemUser</span><span class="sxs-lookup"><span data-stu-id="b022e-145">SystemUser</span></span></p></td>
<td><p><span data-ttu-id="b022e-146">持久聊天服务器在内部使用的主体。</span><span class="sxs-lookup"><span data-stu-id="b022e-146">Principal used internally by Persistent Chat Server.</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b022e-147">5</span><span class="sxs-lookup"><span data-stu-id="b022e-147">5</span></span></p></td>
<td><p><span data-ttu-id="b022e-148">用户</span><span class="sxs-lookup"><span data-stu-id="b022e-148">User</span></span></p></td>
<td><p><span data-ttu-id="b022e-149">普通用户。</span><span class="sxs-lookup"><span data-stu-id="b022e-149">Regular user.</span></span></p></td>
<td><p><span data-ttu-id="b022e-150">是</span><span class="sxs-lookup"><span data-stu-id="b022e-150">Yes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b022e-151">个</span><span class="sxs-lookup"><span data-stu-id="b022e-151">8</span></span></p></td>
<td><p><span data-ttu-id="b022e-152">电源</span><span class="sxs-lookup"><span data-stu-id="b022e-152">DC</span></span></p></td>
<td><p><span data-ttu-id="b022e-153">Active Directory 域服务域控制器。</span><span class="sxs-lookup"><span data-stu-id="b022e-153">Active Directory Domain Services domain controller.</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b022e-154">db-9</span><span class="sxs-lookup"><span data-stu-id="b022e-154">9</span></span></p></td>
<td><p><span data-ttu-id="b022e-155">团队</span><span class="sxs-lookup"><span data-stu-id="b022e-155">Group</span></span></p></td>
<td><p><span data-ttu-id="b022e-156">Active Directory 安全组。</span><span class="sxs-lookup"><span data-stu-id="b022e-156">Active Directory security group.</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b022e-157">10</span><span class="sxs-lookup"><span data-stu-id="b022e-157">10</span></span></p></td>
<td><p><span data-ttu-id="b022e-158">收藏夹</span><span class="sxs-lookup"><span data-stu-id="b022e-158">Folder</span></span></p></td>
<td><p><span data-ttu-id="b022e-159">Active Directory 容器或组织单位。</span><span class="sxs-lookup"><span data-stu-id="b022e-159">Active Directory container or organizational unit.</span></span></p></td>
<td></td>
</tr>
</tbody>
</table>


<div>

## <a name="see-also"></a><span data-ttu-id="b022e-160">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b022e-160">See Also</span></span>


[<span data-ttu-id="b022e-161">Lync Server 2013 中的 tblPrincipal</span><span class="sxs-lookup"><span data-stu-id="b022e-161">tblPrincipal in Lync Server 2013</span></span>](lync-server-2013-tblprincipal.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

