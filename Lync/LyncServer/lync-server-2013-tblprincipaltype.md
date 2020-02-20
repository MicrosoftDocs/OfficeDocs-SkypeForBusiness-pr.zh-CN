---
title: Lync Server 2013： tblPrincipalType
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblPrincipalType
ms:assetid: 32e1c1d6-80f4-4624-bf4e-b4c77d3982fa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558633(v=OCS.15)
ms:contentKeyID: 48183787
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6f1c43c0e000e0c8adc3516304b931a68111072d
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42141968"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="tblprincipaltype-in-lync-server-2013"></a><span data-ttu-id="80a56-102">Lync Server 2013 中的 tblPrincipalType</span><span class="sxs-lookup"><span data-stu-id="80a56-102">tblPrincipalType in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="80a56-103">_**上次修改的主题：** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="80a56-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="80a56-104">tblPrincipalType 包含用于对 tblPrincipal 表中的内容进行分类的主体类型。</span><span class="sxs-lookup"><span data-stu-id="80a56-104">tblPrincipalType contains principal types to categorize what is in the tblPrincipal table.</span></span>

### <a name="columns"></a><span data-ttu-id="80a56-105">Columns</span><span class="sxs-lookup"><span data-stu-id="80a56-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="80a56-106">列</span><span class="sxs-lookup"><span data-stu-id="80a56-106">Column</span></span></th>
<th><span data-ttu-id="80a56-107">类型</span><span class="sxs-lookup"><span data-stu-id="80a56-107">Type</span></span></th>
<th><span data-ttu-id="80a56-108">说明</span><span class="sxs-lookup"><span data-stu-id="80a56-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="80a56-109">ptypeID</span><span class="sxs-lookup"><span data-stu-id="80a56-109">ptypeID</span></span></p></td>
<td><p><span data-ttu-id="80a56-110">smallint，不为 null</span><span class="sxs-lookup"><span data-stu-id="80a56-110">smallint, not null</span></span></p></td>
<td><p><span data-ttu-id="80a56-111">主体类型 ID。</span><span class="sxs-lookup"><span data-stu-id="80a56-111">Principal type ID.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="80a56-112">ptypeDesc</span><span class="sxs-lookup"><span data-stu-id="80a56-112">ptypeDesc</span></span></p></td>
<td><p><span data-ttu-id="80a56-113">nvarchar (256)，不为 null</span><span class="sxs-lookup"><span data-stu-id="80a56-113">nvarchar (256), not null</span></span></p></td>
<td><p><span data-ttu-id="80a56-114">类型描述。</span><span class="sxs-lookup"><span data-stu-id="80a56-114">Description of the type.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="80a56-115">ptypeIsSystemUser</span><span class="sxs-lookup"><span data-stu-id="80a56-115">ptypeIsSystemUser</span></span></p></td>
<td><p><span data-ttu-id="80a56-116">bit，不为 null</span><span class="sxs-lookup"><span data-stu-id="80a56-116">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="80a56-117">在类型与供内部使用的主体对应时为 True。</span><span class="sxs-lookup"><span data-stu-id="80a56-117">True if the type corresponds to the principals that are used for internal purposes.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="80a56-118">ptypeIsUser</span><span class="sxs-lookup"><span data-stu-id="80a56-118">ptypeIsUser</span></span></p></td>
<td><p><span data-ttu-id="80a56-119">bit，不为 null</span><span class="sxs-lookup"><span data-stu-id="80a56-119">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="80a56-120">在类型为用户类型时为 True。</span><span class="sxs-lookup"><span data-stu-id="80a56-120">True if the type is a user type.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="key"></a><span data-ttu-id="80a56-121">键</span><span class="sxs-lookup"><span data-stu-id="80a56-121">Key</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="80a56-122">列</span><span class="sxs-lookup"><span data-stu-id="80a56-122">Column</span></span></th>
<th><span data-ttu-id="80a56-123">说明</span><span class="sxs-lookup"><span data-stu-id="80a56-123">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="80a56-124">ptypeID</span><span class="sxs-lookup"><span data-stu-id="80a56-124">ptypeID</span></span></p></td>
<td><p><span data-ttu-id="80a56-125">主键。</span><span class="sxs-lookup"><span data-stu-id="80a56-125">Primary key.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="principal-values"></a><span data-ttu-id="80a56-126">主体值</span><span class="sxs-lookup"><span data-stu-id="80a56-126">Principal Values</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="80a56-127">ID</span><span class="sxs-lookup"><span data-stu-id="80a56-127">ID</span></span></th>
<th><span data-ttu-id="80a56-128">Role</span><span class="sxs-lookup"><span data-stu-id="80a56-128">Role</span></span></th>
<th><span data-ttu-id="80a56-129">说明</span><span class="sxs-lookup"><span data-stu-id="80a56-129">Description</span></span></th>
<th><span data-ttu-id="80a56-130">用户</span><span class="sxs-lookup"><span data-stu-id="80a56-130">User</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="80a56-131">1</span><span class="sxs-lookup"><span data-stu-id="80a56-131">1</span></span></p></td>
<td><p><span data-ttu-id="80a56-132">任意</span><span class="sxs-lookup"><span data-stu-id="80a56-132">Any</span></span></p></td>
<td><p><span data-ttu-id="80a56-p101">未知类型的通用主体。不用于 tblPrincipal 表。</span><span class="sxs-lookup"><span data-stu-id="80a56-p101">Generic principal with no known type. Not used in tblPrincipal table.</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="80a56-135">双面</span><span class="sxs-lookup"><span data-stu-id="80a56-135">2</span></span></p></td>
<td><p><span data-ttu-id="80a56-136">AnyUser</span><span class="sxs-lookup"><span data-stu-id="80a56-136">AnyUser</span></span></p></td>
<td><p><span data-ttu-id="80a56-p102">用户类型的通用主体。不用于 tblPrincipal 表。</span><span class="sxs-lookup"><span data-stu-id="80a56-p102">Generic principal of user type. Not used in tblPrincipal table.</span></span></p></td>
<td><p><span data-ttu-id="80a56-139">是</span><span class="sxs-lookup"><span data-stu-id="80a56-139">Yes</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="80a56-140">第三章</span><span class="sxs-lookup"><span data-stu-id="80a56-140">3</span></span></p></td>
<td><p><span data-ttu-id="80a56-141">AnyGroup</span><span class="sxs-lookup"><span data-stu-id="80a56-141">AnyGroup</span></span></p></td>
<td><p><span data-ttu-id="80a56-p103">组语义的通用主体。不用于 tblPrincipal 表。</span><span class="sxs-lookup"><span data-stu-id="80a56-p103">Generic principal with group semantic. Not used in tblPrincipal table.</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="80a56-144">4</span><span class="sxs-lookup"><span data-stu-id="80a56-144">4</span></span></p></td>
<td><p><span data-ttu-id="80a56-145">SystemUser</span><span class="sxs-lookup"><span data-stu-id="80a56-145">SystemUser</span></span></p></td>
<td><p><span data-ttu-id="80a56-146">持久聊天服务器在内部使用的主体。</span><span class="sxs-lookup"><span data-stu-id="80a56-146">Principal used internally by Persistent Chat Server.</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="80a56-147">5</span><span class="sxs-lookup"><span data-stu-id="80a56-147">5</span></span></p></td>
<td><p><span data-ttu-id="80a56-148">用户</span><span class="sxs-lookup"><span data-stu-id="80a56-148">User</span></span></p></td>
<td><p><span data-ttu-id="80a56-149">常规用户。</span><span class="sxs-lookup"><span data-stu-id="80a56-149">Regular user.</span></span></p></td>
<td><p><span data-ttu-id="80a56-150">是</span><span class="sxs-lookup"><span data-stu-id="80a56-150">Yes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="80a56-151">8 </span><span class="sxs-lookup"><span data-stu-id="80a56-151">8</span></span></p></td>
<td><p><span data-ttu-id="80a56-152">DC</span><span class="sxs-lookup"><span data-stu-id="80a56-152">DC</span></span></p></td>
<td><p><span data-ttu-id="80a56-153">Active Directory 域服务域控制器。</span><span class="sxs-lookup"><span data-stu-id="80a56-153">Active Directory Domain Services domain controller.</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="80a56-154">9 </span><span class="sxs-lookup"><span data-stu-id="80a56-154">9</span></span></p></td>
<td><p><span data-ttu-id="80a56-155">Group</span><span class="sxs-lookup"><span data-stu-id="80a56-155">Group</span></span></p></td>
<td><p><span data-ttu-id="80a56-156">Active Directory 安全组。</span><span class="sxs-lookup"><span data-stu-id="80a56-156">Active Directory security group.</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="80a56-157">10 </span><span class="sxs-lookup"><span data-stu-id="80a56-157">10</span></span></p></td>
<td><p><span data-ttu-id="80a56-158">Folder</span><span class="sxs-lookup"><span data-stu-id="80a56-158">Folder</span></span></p></td>
<td><p><span data-ttu-id="80a56-159">Active Directory 容器或组织单位。</span><span class="sxs-lookup"><span data-stu-id="80a56-159">Active Directory container or organizational unit.</span></span></p></td>
<td></td>
</tr>
</tbody>
</table>


<div>

## <a name="see-also"></a><span data-ttu-id="80a56-160">另请参阅</span><span class="sxs-lookup"><span data-stu-id="80a56-160">See Also</span></span>


[<span data-ttu-id="80a56-161">Lync Server 2013 中的 tblPrincipal</span><span class="sxs-lookup"><span data-stu-id="80a56-161">tblPrincipal in Lync Server 2013</span></span>](lync-server-2013-tblprincipal.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

