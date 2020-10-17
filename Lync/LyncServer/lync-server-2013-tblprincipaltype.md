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
ms.openlocfilehash: 60fa841f7f88e0da2c428ae68c5007fb79e6c69d
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48536319"
---
# <a name="tblprincipaltype-in-lync-server-2013"></a><span data-ttu-id="b7983-102">Lync Server 2013 中的 tblPrincipalType</span><span class="sxs-lookup"><span data-stu-id="b7983-102">tblPrincipalType in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b7983-103">_**上次修改的主题：** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="b7983-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="b7983-104">tblPrincipalType 包含用于对 tblPrincipal 表中的内容进行分类的主体类型。</span><span class="sxs-lookup"><span data-stu-id="b7983-104">tblPrincipalType contains principal types to categorize what is in the tblPrincipal table.</span></span>

### <a name="columns"></a><span data-ttu-id="b7983-105">列数</span><span class="sxs-lookup"><span data-stu-id="b7983-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b7983-106">列</span><span class="sxs-lookup"><span data-stu-id="b7983-106">Column</span></span></th>
<th><span data-ttu-id="b7983-107">类型</span><span class="sxs-lookup"><span data-stu-id="b7983-107">Type</span></span></th>
<th><span data-ttu-id="b7983-108">说明</span><span class="sxs-lookup"><span data-stu-id="b7983-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b7983-109">ptypeID</span><span class="sxs-lookup"><span data-stu-id="b7983-109">ptypeID</span></span></p></td>
<td><p><span data-ttu-id="b7983-110">smallint，不为 null</span><span class="sxs-lookup"><span data-stu-id="b7983-110">smallint, not null</span></span></p></td>
<td><p><span data-ttu-id="b7983-111">主体类型 ID。</span><span class="sxs-lookup"><span data-stu-id="b7983-111">Principal type ID.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b7983-112">ptypeDesc</span><span class="sxs-lookup"><span data-stu-id="b7983-112">ptypeDesc</span></span></p></td>
<td><p><span data-ttu-id="b7983-113">nvarchar (256)，不为 null</span><span class="sxs-lookup"><span data-stu-id="b7983-113">nvarchar (256), not null</span></span></p></td>
<td><p><span data-ttu-id="b7983-114">类型描述。</span><span class="sxs-lookup"><span data-stu-id="b7983-114">Description of the type.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b7983-115">ptypeIsSystemUser</span><span class="sxs-lookup"><span data-stu-id="b7983-115">ptypeIsSystemUser</span></span></p></td>
<td><p><span data-ttu-id="b7983-116">bit，不为 null</span><span class="sxs-lookup"><span data-stu-id="b7983-116">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="b7983-117">在类型与供内部使用的主体对应时为 True。</span><span class="sxs-lookup"><span data-stu-id="b7983-117">True if the type corresponds to the principals that are used for internal purposes.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b7983-118">ptypeIsUser</span><span class="sxs-lookup"><span data-stu-id="b7983-118">ptypeIsUser</span></span></p></td>
<td><p><span data-ttu-id="b7983-119">bit，不为 null</span><span class="sxs-lookup"><span data-stu-id="b7983-119">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="b7983-120">在类型为用户类型时为 True。</span><span class="sxs-lookup"><span data-stu-id="b7983-120">True if the type is a user type.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="key"></a><span data-ttu-id="b7983-121">键</span><span class="sxs-lookup"><span data-stu-id="b7983-121">Key</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b7983-122">列</span><span class="sxs-lookup"><span data-stu-id="b7983-122">Column</span></span></th>
<th><span data-ttu-id="b7983-123">说明</span><span class="sxs-lookup"><span data-stu-id="b7983-123">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b7983-124">ptypeID</span><span class="sxs-lookup"><span data-stu-id="b7983-124">ptypeID</span></span></p></td>
<td><p><span data-ttu-id="b7983-125">主键。</span><span class="sxs-lookup"><span data-stu-id="b7983-125">Primary key.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="principal-values"></a><span data-ttu-id="b7983-126">主体值</span><span class="sxs-lookup"><span data-stu-id="b7983-126">Principal Values</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b7983-127">ID</span><span class="sxs-lookup"><span data-stu-id="b7983-127">ID</span></span></th>
<th><span data-ttu-id="b7983-128">Role</span><span class="sxs-lookup"><span data-stu-id="b7983-128">Role</span></span></th>
<th><span data-ttu-id="b7983-129">说明</span><span class="sxs-lookup"><span data-stu-id="b7983-129">Description</span></span></th>
<th><span data-ttu-id="b7983-130">用户</span><span class="sxs-lookup"><span data-stu-id="b7983-130">User</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b7983-131">1</span><span class="sxs-lookup"><span data-stu-id="b7983-131">1</span></span></p></td>
<td><p><span data-ttu-id="b7983-132">任何</span><span class="sxs-lookup"><span data-stu-id="b7983-132">Any</span></span></p></td>
<td><p><span data-ttu-id="b7983-p101">未知类型的通用主体。不用于 tblPrincipal 表。</span><span class="sxs-lookup"><span data-stu-id="b7983-p101">Generic principal with no known type. Not used in tblPrincipal table.</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b7983-135">双面</span><span class="sxs-lookup"><span data-stu-id="b7983-135">2</span></span></p></td>
<td><p><span data-ttu-id="b7983-136">AnyUser</span><span class="sxs-lookup"><span data-stu-id="b7983-136">AnyUser</span></span></p></td>
<td><p><span data-ttu-id="b7983-p102">用户类型的通用主体。不用于 tblPrincipal 表。</span><span class="sxs-lookup"><span data-stu-id="b7983-p102">Generic principal of user type. Not used in tblPrincipal table.</span></span></p></td>
<td><p><span data-ttu-id="b7983-139">是</span><span class="sxs-lookup"><span data-stu-id="b7983-139">Yes</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b7983-140">第三章</span><span class="sxs-lookup"><span data-stu-id="b7983-140">3</span></span></p></td>
<td><p><span data-ttu-id="b7983-141">AnyGroup</span><span class="sxs-lookup"><span data-stu-id="b7983-141">AnyGroup</span></span></p></td>
<td><p><span data-ttu-id="b7983-p103">组语义的通用主体。不用于 tblPrincipal 表。</span><span class="sxs-lookup"><span data-stu-id="b7983-p103">Generic principal with group semantic. Not used in tblPrincipal table.</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b7983-144">4 </span><span class="sxs-lookup"><span data-stu-id="b7983-144">4</span></span></p></td>
<td><p><span data-ttu-id="b7983-145">SystemUser</span><span class="sxs-lookup"><span data-stu-id="b7983-145">SystemUser</span></span></p></td>
<td><p><span data-ttu-id="b7983-146">持久聊天服务器在内部使用的主体。</span><span class="sxs-lookup"><span data-stu-id="b7983-146">Principal used internally by Persistent Chat Server.</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b7983-147">5 </span><span class="sxs-lookup"><span data-stu-id="b7983-147">5</span></span></p></td>
<td><p><span data-ttu-id="b7983-148">用户</span><span class="sxs-lookup"><span data-stu-id="b7983-148">User</span></span></p></td>
<td><p><span data-ttu-id="b7983-149">常规用户。</span><span class="sxs-lookup"><span data-stu-id="b7983-149">Regular user.</span></span></p></td>
<td><p><span data-ttu-id="b7983-150">是</span><span class="sxs-lookup"><span data-stu-id="b7983-150">Yes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b7983-151">8 </span><span class="sxs-lookup"><span data-stu-id="b7983-151">8</span></span></p></td>
<td><p><span data-ttu-id="b7983-152">DC</span><span class="sxs-lookup"><span data-stu-id="b7983-152">DC</span></span></p></td>
<td><p><span data-ttu-id="b7983-153">Active Directory 域服务域控制器。</span><span class="sxs-lookup"><span data-stu-id="b7983-153">Active Directory Domain Services domain controller.</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b7983-154">9 </span><span class="sxs-lookup"><span data-stu-id="b7983-154">9</span></span></p></td>
<td><p><span data-ttu-id="b7983-155">Group</span><span class="sxs-lookup"><span data-stu-id="b7983-155">Group</span></span></p></td>
<td><p><span data-ttu-id="b7983-156">Active Directory 安全组。</span><span class="sxs-lookup"><span data-stu-id="b7983-156">Active Directory security group.</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b7983-157">10  </span><span class="sxs-lookup"><span data-stu-id="b7983-157">10</span></span></p></td>
<td><p><span data-ttu-id="b7983-158">Folder</span><span class="sxs-lookup"><span data-stu-id="b7983-158">Folder</span></span></p></td>
<td><p><span data-ttu-id="b7983-159">Active Directory 容器或组织单位。</span><span class="sxs-lookup"><span data-stu-id="b7983-159">Active Directory container or organizational unit.</span></span></p></td>
<td></td>
</tr>
</tbody>
</table>


<div>

## <a name="see-also"></a><span data-ttu-id="b7983-160">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b7983-160">See Also</span></span>


[<span data-ttu-id="b7983-161">Lync Server 2013 中的 tblPrincipal</span><span class="sxs-lookup"><span data-stu-id="b7983-161">tblPrincipal in Lync Server 2013</span></span>](lync-server-2013-tblprincipal.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

