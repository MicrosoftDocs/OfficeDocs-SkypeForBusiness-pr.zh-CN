---
title: Lync Server 2013：管理通讯簿服务
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Administering the Address Book Service
ms:assetid: 801e4243-9670-4477-aa2f-88b61ecf5351
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429711(v=OCS.15)
ms:contentKeyID: 48184649
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b72d08d786f41dc606b419f9452970d683b8da37
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "42188655"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="administering-the-address-book-service-in-lync-server-2013"></a><span data-ttu-id="c7d36-102">在 Lync Server 2013 中管理通讯簿服务</span><span class="sxs-lookup"><span data-stu-id="c7d36-102">Administering the Address Book Service in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c7d36-103">_**上次修改的主题：** 2014-02-05_</span><span class="sxs-lookup"><span data-stu-id="c7d36-103">_**Topic Last Modified:** 2014-02-05_</span></span>

<span data-ttu-id="c7d36-104">作为 Lync Server、Enterprise Edition 或 Standard Edition Server 部署的一部分，默认情况下会安装通讯簿服务。</span><span class="sxs-lookup"><span data-stu-id="c7d36-104">As a part of the deployment of Lync Server, Enterprise Edition or Standard Edition server, the Address Book Service is installed by default.</span></span> <span data-ttu-id="c7d36-105">通讯簿服务（RTCab）使用的数据库是在 SQL Server 上创建的（对于 Enterprise Edition，这是后端 SQL Server; 对于 Standard Edition server，则为并置 SQL Server）。</span><span class="sxs-lookup"><span data-stu-id="c7d36-105">The database used by the Address Book Service – RTCab – is created on the SQL Server (for Enterprise Edition, this is the back-end SQL Server; for Standard Edition server, the collocated SQL Server).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="c7d36-106">有关使用<STRONG>ADSI 编辑</STRONG>编辑 Active Directory 域服务对象属性的信息，请参阅<A href="https://go.microsoft.com/fwlink/?linkid=330427">ADSI edit</A>。</span><span class="sxs-lookup"><span data-stu-id="c7d36-106">For information about using <STRONG>ADSI Edit</STRONG> to edit Active Directory Domain Services object attributes, see <A href="https://go.microsoft.com/fwlink/?linkid=330427">ADSI Edit</A>.</span></span> <span data-ttu-id="c7d36-107">有关特定于通讯簿服务的资源工具包中的工具的信息，请参阅<A href="https://go.microsoft.com/fwlink/?linkid=330429">Microsoft Lync Server 2013 资源工具包工具</A>。</span><span class="sxs-lookup"><span data-stu-id="c7d36-107">For information about a tool in the Resource Kit specifically for the Address Book service, see <A href="https://go.microsoft.com/fwlink/?linkid=330429">Microsoft Lync Server 2013 Resource Kit Tools</A>.</span></span>



</div>

<div>

## <a name="address-book-server-phone-number-normalization"></a><span data-ttu-id="c7d36-108">通讯簿服务器电话号码规范化</span><span class="sxs-lookup"><span data-stu-id="c7d36-108">Address Book Server Phone Number Normalization</span></span>

<span data-ttu-id="c7d36-109">Lync Server 需要标准化 RFC 3966/e.164 电话号码。</span><span class="sxs-lookup"><span data-stu-id="c7d36-109">Lync Server requires standardized RFC 3966/E.164 phone numbers.</span></span> <span data-ttu-id="c7d36-110">若要使用非结构化或格式不一致的电话号码，Lync Server 依靠通讯簿服务器对电话号码进行预处理，然后再将其传递给规范化规则。</span><span class="sxs-lookup"><span data-stu-id="c7d36-110">To use phone numbers that are unstructured or inconsistently formatted, Lync Server relies on the Address Book Server to preprocess phone numbers before they are handed off to the normalization rules.</span></span> <span data-ttu-id="c7d36-111">当从通讯簿中使用电话号码且应用规范化规则时，客户端（如 Lync Phone Edition 和 Lync Mobile）可以使用这些规范化的数字。</span><span class="sxs-lookup"><span data-stu-id="c7d36-111">When a phone number is used from the address book and the normalization rule is applied, clients, such as Lync Phone Edition and Lync Mobile, can use these normalized numbers.</span></span>

<span data-ttu-id="c7d36-p104">对于以前版本中使用的规范化规则，如果不进行某些调整，可能无法正常使用。由于在规范化规则之前删除了空格和非必需的字符，因此如果正则表达式专门查找已删除的短划线或其他字符，则规范化规则可能失败。应检查规范化规则以确保它们不查找这些非必需字符，或者允许规则在期望字符出现但未出现的情况下正常中止并继续执行。</span><span class="sxs-lookup"><span data-stu-id="c7d36-p104">The normalization rules that were used in previous versions may not work properly without some adjustments. Because the white space and non-mandatory characters are removed prior to the normalization rules, if your regex expression is specifically looking for a dash or other character that was removed, your normalization rule might fail. You should review your normalization rules to ensure that either they are not looking for these non-mandatory characters, or that the rule can fail gracefully and continue in the event that the character is not present where the rule anticipates it will be.</span></span>

</div>

<div>

## <a name="user-replicator-and-address-book-server"></a><span data-ttu-id="c7d36-115">用户复制程序和通讯簿服务器</span><span class="sxs-lookup"><span data-stu-id="c7d36-115">User Replicator and Address Book Server</span></span>

<span data-ttu-id="c7d36-116">通讯簿服务器使用由用户复制程序提供的数据来更新最初从全局地址列表 (GAL) 中获取的信息。</span><span class="sxs-lookup"><span data-stu-id="c7d36-116">The Address Book Server uses data provided by User Replicator to update the information that it initially obtains from the global address list (GAL).</span></span> <span data-ttu-id="c7d36-117">用户复制程序将每个用户、联系人和组的 Active Directory 域服务属性写入数据库中的 AbUserEntry 表，通讯簿服务器将数据库中的用户数据同步到通讯簿服务器文件存储中的文件，并导入通讯簿数据库 RTCab。</span><span class="sxs-lookup"><span data-stu-id="c7d36-117">User Replicator writes the Active Directory Domain Services attributes for each user, contact, and group into the AbUserEntry table in the database and the Address Book Server syncs the user data from the database into files in the Address Book Server file store and into the Address Book database RTCab.</span></span> <span data-ttu-id="c7d36-118">AbUserEntry 表的架构使用两列：**UserGuid** 和 **UserData**。</span><span class="sxs-lookup"><span data-stu-id="c7d36-118">The schema for the AbUserEntry table uses two columns, **UserGuid** and **UserData**.</span></span> <span data-ttu-id="c7d36-119">**UserGuid**是索引列，其中包含 Active Directory 对象的16字节 GUID。</span><span class="sxs-lookup"><span data-stu-id="c7d36-119">**UserGuid** is the index column and contains the 16-byte GUID of the Active Directory object.</span></span> <span data-ttu-id="c7d36-120">**UserData**是一个图像列，其中包含了该联系人的所有上述 Active Directory 域服务属性。</span><span class="sxs-lookup"><span data-stu-id="c7d36-120">**UserData** is an image column which contains all of the previously mentioned Active Directory Domain Services attributes for that contact.</span></span>

<span data-ttu-id="c7d36-121">用户复制程序通过读取位于基于 SQL Server 的实例中的配置表来确定要写入的 Active Directory 属性，AbUserEntry 表。</span><span class="sxs-lookup"><span data-stu-id="c7d36-121">User Replicator determines which Active Directory attributes to write by reading a configuration table located in the same SQL Server-based instance as the AbUserEntry table.</span></span> <span data-ttu-id="c7d36-122">AbAttribute 表包含四列：**ID**、**Name**、**Flags** 和 **Enable**。</span><span class="sxs-lookup"><span data-stu-id="c7d36-122">The AbAttribute table contains three columns, **ID**, **Name**, **Flags**, and **Enable**.</span></span> <span data-ttu-id="c7d36-123">该表在数据库安装期间创建。</span><span class="sxs-lookup"><span data-stu-id="c7d36-123">The table is created during database setup.</span></span> <span data-ttu-id="c7d36-124">如果 AbAttribute 表为空，用户复制程序将跳过其 AbUserEntry 表处理逻辑。</span><span class="sxs-lookup"><span data-stu-id="c7d36-124">If the AbAttribute table is empty, User Replicator skips its AbUserEntry table processing logic.</span></span> <span data-ttu-id="c7d36-125">通讯簿服务器属性是动态的，可以从 AbAttribute 表中检索，该表最初在通讯簿服务器激活时由通讯簿服务器写入。</span><span class="sxs-lookup"><span data-stu-id="c7d36-125">Address Book Server attributes are dynamic and are retrieved from the AbAttribute table, which is initially written by the Address Book Server when the Address Book Server is activated.</span></span>

<span data-ttu-id="c7d36-126">通讯簿服务器激活将使用下表中显示的值填充 AbAttribute 表。</span><span class="sxs-lookup"><span data-stu-id="c7d36-126">Address Book Server activation populates the AbAttribute table with the values shown in the following table.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c7d36-127">ID</span><span class="sxs-lookup"><span data-stu-id="c7d36-127">ID</span></span></th>
<th><span data-ttu-id="c7d36-128">名称</span><span class="sxs-lookup"><span data-stu-id="c7d36-128">Name</span></span></th>
<th><span data-ttu-id="c7d36-129">Flags</span><span class="sxs-lookup"><span data-stu-id="c7d36-129">Flags</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c7d36-130">1</span><span class="sxs-lookup"><span data-stu-id="c7d36-130">1</span></span></p></td>
<td><p><span data-ttu-id="c7d36-131">givenName</span><span class="sxs-lookup"><span data-stu-id="c7d36-131">givenName</span></span></p></td>
<td><p><span data-ttu-id="c7d36-132">0x01400000</span><span class="sxs-lookup"><span data-stu-id="c7d36-132">0x01400000</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c7d36-133">双面</span><span class="sxs-lookup"><span data-stu-id="c7d36-133">2</span></span></p></td>
<td><p><span data-ttu-id="c7d36-134">Sn</span><span class="sxs-lookup"><span data-stu-id="c7d36-134">Sn</span></span></p></td>
<td><p><span data-ttu-id="c7d36-135">0x02400000</span><span class="sxs-lookup"><span data-stu-id="c7d36-135">0x02400000</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c7d36-136">第三章</span><span class="sxs-lookup"><span data-stu-id="c7d36-136">3</span></span></p></td>
<td><p><span data-ttu-id="c7d36-137">displayName</span><span class="sxs-lookup"><span data-stu-id="c7d36-137">displayName</span></span></p></td>
<td><p><span data-ttu-id="c7d36-138">0x03420000</span><span class="sxs-lookup"><span data-stu-id="c7d36-138">0x03420000</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c7d36-139">4</span><span class="sxs-lookup"><span data-stu-id="c7d36-139">4</span></span></p></td>
<td><p><span data-ttu-id="c7d36-140">标题</span><span class="sxs-lookup"><span data-stu-id="c7d36-140">Title</span></span></p></td>
<td><p><span data-ttu-id="c7d36-141">0x04000000</span><span class="sxs-lookup"><span data-stu-id="c7d36-141">0x04000000</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c7d36-142">5</span><span class="sxs-lookup"><span data-stu-id="c7d36-142">5</span></span></p></td>
<td><p><span data-ttu-id="c7d36-143">mailNickname</span><span class="sxs-lookup"><span data-stu-id="c7d36-143">mailNickname</span></span></p></td>
<td><p><span data-ttu-id="c7d36-144">0x05400000</span><span class="sxs-lookup"><span data-stu-id="c7d36-144">0x05400000</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c7d36-145">6 </span><span class="sxs-lookup"><span data-stu-id="c7d36-145">6</span></span></p></td>
<td><p><span data-ttu-id="c7d36-146">Company</span><span class="sxs-lookup"><span data-stu-id="c7d36-146">Company</span></span></p></td>
<td><p><span data-ttu-id="c7d36-147">0x06000000</span><span class="sxs-lookup"><span data-stu-id="c7d36-147">0x06000000</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c7d36-148">7 </span><span class="sxs-lookup"><span data-stu-id="c7d36-148">7</span></span></p></td>
<td><p><span data-ttu-id="c7d36-149">physicalDeliveryOfficeName</span><span class="sxs-lookup"><span data-stu-id="c7d36-149">physicalDeliveryOfficeName</span></span></p></td>
<td><p><span data-ttu-id="c7d36-150">0x07000000</span><span class="sxs-lookup"><span data-stu-id="c7d36-150">0x07000000</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c7d36-151">8 </span><span class="sxs-lookup"><span data-stu-id="c7d36-151">8</span></span></p></td>
<td><p><span data-ttu-id="c7d36-152">msRTCSIP-PrimaryUserAddress</span><span class="sxs-lookup"><span data-stu-id="c7d36-152">msRTCSIP-PrimaryUserAddress</span></span></p></td>
<td><p><span data-ttu-id="c7d36-153">0x08520C00</span><span class="sxs-lookup"><span data-stu-id="c7d36-153">0x08520C00</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c7d36-154">9 </span><span class="sxs-lookup"><span data-stu-id="c7d36-154">9</span></span></p></td>
<td><p><span data-ttu-id="c7d36-155">telephoneNumber</span><span class="sxs-lookup"><span data-stu-id="c7d36-155">telephoneNumber</span></span></p></td>
<td><p><span data-ttu-id="c7d36-156">0x09022800</span><span class="sxs-lookup"><span data-stu-id="c7d36-156">0x09022800</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c7d36-157">10 </span><span class="sxs-lookup"><span data-stu-id="c7d36-157">10</span></span></p></td>
<td><p><span data-ttu-id="c7d36-158">homePhone</span><span class="sxs-lookup"><span data-stu-id="c7d36-158">homePhone</span></span></p></td>
<td><p><span data-ttu-id="c7d36-159">0x0A302800</span><span class="sxs-lookup"><span data-stu-id="c7d36-159">0x0A302800</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c7d36-160">11 </span><span class="sxs-lookup"><span data-stu-id="c7d36-160">11</span></span></p></td>
<td><p><span data-ttu-id="c7d36-161">移动设备</span><span class="sxs-lookup"><span data-stu-id="c7d36-161">Mobile</span></span></p></td>
<td><p><span data-ttu-id="c7d36-162">0x0B622800</span><span class="sxs-lookup"><span data-stu-id="c7d36-162">0x0B622800</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c7d36-163">12</span><span class="sxs-lookup"><span data-stu-id="c7d36-163">12</span></span></p></td>
<td><p><span data-ttu-id="c7d36-164">otherTelephone</span><span class="sxs-lookup"><span data-stu-id="c7d36-164">otherTelephone</span></span></p></td>
<td><p><span data-ttu-id="c7d36-165">0x0C302000</span><span class="sxs-lookup"><span data-stu-id="c7d36-165">0x0C302000</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c7d36-166">13 </span><span class="sxs-lookup"><span data-stu-id="c7d36-166">13</span></span></p></td>
<td><p><span data-ttu-id="c7d36-167">ipPhone</span><span class="sxs-lookup"><span data-stu-id="c7d36-167">ipPhone</span></span></p></td>
<td><p><span data-ttu-id="c7d36-168">0x0D302000</span><span class="sxs-lookup"><span data-stu-id="c7d36-168">0x0D302000</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c7d36-169">14 </span><span class="sxs-lookup"><span data-stu-id="c7d36-169">14</span></span></p></td>
<td><p><span data-ttu-id="c7d36-170">邮件</span><span class="sxs-lookup"><span data-stu-id="c7d36-170">Mail</span></span></p></td>
<td><p><span data-ttu-id="c7d36-171">0x0E500000</span><span class="sxs-lookup"><span data-stu-id="c7d36-171">0x0E500000</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c7d36-172">15 </span><span class="sxs-lookup"><span data-stu-id="c7d36-172">15</span></span></p></td>
<td><p><span data-ttu-id="c7d36-173">groupType</span><span class="sxs-lookup"><span data-stu-id="c7d36-173">groupType</span></span></p></td>
<td><p><span data-ttu-id="c7d36-174">0x0F010800</span><span class="sxs-lookup"><span data-stu-id="c7d36-174">0x0F010800</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c7d36-175">16 </span><span class="sxs-lookup"><span data-stu-id="c7d36-175">16</span></span></p></td>
<td><p><span data-ttu-id="c7d36-176">部门</span><span class="sxs-lookup"><span data-stu-id="c7d36-176">Department</span></span></p></td>
<td><p><span data-ttu-id="c7d36-177">0x10000000</span><span class="sxs-lookup"><span data-stu-id="c7d36-177">0x10000000</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c7d36-178">17 </span><span class="sxs-lookup"><span data-stu-id="c7d36-178">17</span></span></p></td>
<td><p><span data-ttu-id="c7d36-179">Description</span><span class="sxs-lookup"><span data-stu-id="c7d36-179">Description</span></span></p></td>
<td><p><span data-ttu-id="c7d36-180">0x11000100</span><span class="sxs-lookup"><span data-stu-id="c7d36-180">0x11000100</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c7d36-181">18 </span><span class="sxs-lookup"><span data-stu-id="c7d36-181">18</span></span></p></td>
<td><p><span data-ttu-id="c7d36-182">Manager</span><span class="sxs-lookup"><span data-stu-id="c7d36-182">Manager</span></span></p></td>
<td><p><span data-ttu-id="c7d36-183">0x12040001</span><span class="sxs-lookup"><span data-stu-id="c7d36-183">0x12040001</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c7d36-184">合</span><span class="sxs-lookup"><span data-stu-id="c7d36-184">19</span></span></p></td>
<td><p><span data-ttu-id="c7d36-185">proxyAddress</span><span class="sxs-lookup"><span data-stu-id="c7d36-185">proxyAddress</span></span></p></td>
<td><p><span data-ttu-id="c7d36-186">0x00500105</span><span class="sxs-lookup"><span data-stu-id="c7d36-186">0x00500105</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c7d36-187">20</span><span class="sxs-lookup"><span data-stu-id="c7d36-187">20</span></span></p></td>
<td><p><span data-ttu-id="c7d36-188">msExchHideFromAddressLists</span><span class="sxs-lookup"><span data-stu-id="c7d36-188">msExchHideFromAddressLists</span></span></p></td>
<td><p><span data-ttu-id="c7d36-189">0xFF000003</span><span class="sxs-lookup"><span data-stu-id="c7d36-189">0xFF000003</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c7d36-190">99</span><span class="sxs-lookup"><span data-stu-id="c7d36-190">99</span></span></p></td>
<td><p><span data-ttu-id="c7d36-191">entryID</span><span class="sxs-lookup"><span data-stu-id="c7d36-191">entryID</span></span></p></td>
<td><p><span data-ttu-id="c7d36-192">0x99000000</span><span class="sxs-lookup"><span data-stu-id="c7d36-192">0x99000000</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="c7d36-193">**ID** 列中的数字必须唯一，并且绝对不能重复使用。</span><span class="sxs-lookup"><span data-stu-id="c7d36-193">The numbers in the **ID** column must be unique and should never be reused.</span></span> <span data-ttu-id="c7d36-194">另外，使 ID 值低于 256 可以节省通讯簿服务器写入的输出文件的空间。</span><span class="sxs-lookup"><span data-stu-id="c7d36-194">Also, keeping the ID values under 256 saves space in the output files written by the Address Book Server.</span></span> <span data-ttu-id="c7d36-195">然而，最大 ID 值是 65535。</span><span class="sxs-lookup"><span data-stu-id="c7d36-195">However, the maximum ID value is 65535.</span></span> <span data-ttu-id="c7d36-196">"**名称**" 列对应于用户复制程序应在每个联系人的 "AbUserEntry" 表中放置的 Active Directory 属性名称。</span><span class="sxs-lookup"><span data-stu-id="c7d36-196">The **Name** column corresponds to the Active Directory attribute name that User Replicator should put in the AbUserEntry table for each contact.</span></span> <span data-ttu-id="c7d36-197">**Flags** 列中的值用于定义属性类型。</span><span class="sxs-lookup"><span data-stu-id="c7d36-197">The value in the **Flags** column is used to define the type of attribute.</span></span> <span data-ttu-id="c7d36-198">以下类型的通讯簿服务器属性由用户复制程序标识，并由 **Flags** 列中的值的低位字节指示。</span><span class="sxs-lookup"><span data-stu-id="c7d36-198">The following types of Address Book Server attributes are recognized by User Replicator, indicated by the low byte of the value in the **Flags** column.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c7d36-199">属性</span><span class="sxs-lookup"><span data-stu-id="c7d36-199">Attribute</span></span></th>
<th><span data-ttu-id="c7d36-200">说明</span><span class="sxs-lookup"><span data-stu-id="c7d36-200">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c7d36-201">0x0</span><span class="sxs-lookup"><span data-stu-id="c7d36-201">0x0</span></span></p></td>
<td><p><span data-ttu-id="c7d36-p108">字符串属性。用户复制程序在将此类型存储在 AbUserEntry 表中之前，先将其转换成 UTF-8。</span><span class="sxs-lookup"><span data-stu-id="c7d36-p108">A string attribute. User Replicator converts this type to UTF-8 before storing it in the AbUserEntry table.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c7d36-204">0x1</span><span class="sxs-lookup"><span data-stu-id="c7d36-204">0x1</span></span></p></td>
<td><p><span data-ttu-id="c7d36-p109">二进制属性。用户复制程序不进行任何转换即将此类型存储在 blob 中。</span><span class="sxs-lookup"><span data-stu-id="c7d36-p109">A binary attribute. User Replicator stores this in the blob without any conversion.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c7d36-207">0x2</span><span class="sxs-lookup"><span data-stu-id="c7d36-207">0x2</span></span></p></td>
<td><p><span data-ttu-id="c7d36-208">一个字符串属性，但仅当属性值以&quot;电话：&quot;时才包含该属性。</span><span class="sxs-lookup"><span data-stu-id="c7d36-208">A string attribute, but is included only if the attribute value begins with &quot;tel:&quot;.</span></span> <span data-ttu-id="c7d36-209">此类型主要用于多值字符串属性，特别是 <strong>proxyAddresses</strong>。</span><span class="sxs-lookup"><span data-stu-id="c7d36-209">This is primarily for multi-valued string attributes, specifically <strong>proxyAddresses</strong>.</span></span> <span data-ttu-id="c7d36-210">在这种情况下，通讯簿服务器只对<strong></strong>以&quot;电话开始的 proxyAddresses 条目感&quot;兴趣：。</span><span class="sxs-lookup"><span data-stu-id="c7d36-210">In this case, Address Book Server is interested only in <strong>proxyAddresses</strong> entries that begin with &quot;tel:&quot;.</span></span> <span data-ttu-id="c7d36-211">因此，在节省空间的情况下，用户复制程序仅存储以&quot;电话开头的条目：&quot;。</span><span class="sxs-lookup"><span data-stu-id="c7d36-211">Therefore, in the interest of saving space, User Replicator stores only the entries that begin with &quot;tel:&quot;.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c7d36-212">0x3</span><span class="sxs-lookup"><span data-stu-id="c7d36-212">0x3</span></span></p></td>
<td><p><span data-ttu-id="c7d36-p111">布尔字符串属性，如果为 TRUE，用户复制程序不会将此联系人包含在 AbUserEntry 表中。如果为 FALSE，用户复制程序会将此联系人的属性包含在 AbUserEntry 表中，但不包含具有此标志的特定属性。这是另一种特殊类型，主要用于 <strong>msExchHideFromAddressLists</strong> 属性。</span><span class="sxs-lookup"><span data-stu-id="c7d36-p111">A Boolean string attribute, which if TRUE causes User Replicator to not include this contact in the AbUserEntry table. If FALSE, it causes User Replicator to include the attributes for this contact in the AbUserEntry table, but not the particular attribute with this flag. This is another special case type that is primarily for the <strong>msExchHideFromAddressLists</strong> attribute.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c7d36-216">0x4</span><span class="sxs-lookup"><span data-stu-id="c7d36-216">0x4</span></span></p></td>
<td><p><span data-ttu-id="c7d36-217">一个字符串属性，但仅当属性&quot;值以 smtp：&quot;开头并包含符号时才包含&quot; @ &quot;该属性。</span><span class="sxs-lookup"><span data-stu-id="c7d36-217">A string attribute, but is included only if the attribute value begins with &quot;smtp:&quot; and includes the &quot;@&quot; symbol.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c7d36-218">0x5</span><span class="sxs-lookup"><span data-stu-id="c7d36-218">0x5</span></span></p></td>
<td><p><span data-ttu-id="c7d36-219">String 属性，但仅&quot;当属性值以电话：&quot;或&quot;smtp：&quot;开头并包含&quot; @ &quot;符号时才包含该属性。</span><span class="sxs-lookup"><span data-stu-id="c7d36-219">A string attribute, but is included only if the attribute value begins with either &quot;tel:&quot; or &quot;smtp:&quot; and includes the &quot;@&quot; symbol.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c7d36-220">0x100</span><span class="sxs-lookup"><span data-stu-id="c7d36-220">0x100</span></span></p></td>
<td><p><span data-ttu-id="c7d36-221">如果设置，则是可针对每个联系人出现多次的多值属性。</span><span class="sxs-lookup"><span data-stu-id="c7d36-221">If set, this is a multi-valued attribute that can appear more than once for each contact.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c7d36-222">0x400</span><span class="sxs-lookup"><span data-stu-id="c7d36-222">0x400</span></span></p></td>
<td><p><span data-ttu-id="c7d36-p112">如果设置，将标识联系人的电子邮件用户帐户名属性。通讯簿服务器使用此标志来标识在电话规范化事件日志条目中显示的属性值。</span><span class="sxs-lookup"><span data-stu-id="c7d36-p112">If set, this identifies the email user account name attribute for a contact. Address Book Server uses this flag to identify which attribute value to show in the phone normalization event log entry.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c7d36-225">0x800</span><span class="sxs-lookup"><span data-stu-id="c7d36-225">0x800</span></span></p></td>
<td><p><span data-ttu-id="c7d36-p113">如果设置，将标识联系人的必需属性。仅当在 Active Directory 中存在此属性的值时，通讯簿服务器才会在 AbUserEntry 表中包含用户。如果存在多个必需属性，只需其中一个属性具有值即会在 AbUserEntry 表中包含用户。</span><span class="sxs-lookup"><span data-stu-id="c7d36-p113">If set, this identifies a required attribute for a contact. Address Book Server includes a user in the AbUserEntry table only if there is a value for this attribute in Active Directory. If there is more than one required attribute, only one of them is required to have a value to include the user in the AbUserEntry table.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c7d36-229">0x1000</span><span class="sxs-lookup"><span data-stu-id="c7d36-229">0x1000</span></span></p></td>
<td><p><span data-ttu-id="c7d36-230">如果设置，通讯簿服务器将始终规范化此属性的值。</span><span class="sxs-lookup"><span data-stu-id="c7d36-230">If set, Address Book Server always normalizes the value of this attribute.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c7d36-231">0x2000</span><span class="sxs-lookup"><span data-stu-id="c7d36-231">0x2000</span></span></p></td>
<td><p><span data-ttu-id="c7d36-232">如果设置并且 <strong>UseNormalizationRules</strong> CMS 设置为 FALSE，通讯簿服务器将使用 <strong>proxyAddresses</strong> 中的规范化号码；否则通讯簿服务器的行为将与标志位是 0x1000 时相同。</span><span class="sxs-lookup"><span data-stu-id="c7d36-232">If set, Address Book Server uses the normalized number from <strong>proxyAddresses</strong>, if the <strong>UseNormalizationRules</strong> CMS setting is FALSE; otherwise it behaves the same as when the flag bit is 0x1000.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c7d36-233">0x4000</span><span class="sxs-lookup"><span data-stu-id="c7d36-233">0x4000</span></span></p></td>
<td><p><span data-ttu-id="c7d36-p114">如果设置，通讯簿服务器不会在 AbUserEntry 表中包含为指定属性设置了此值的对象。例如，如果 <strong>msRTCSIP-PrimaryUserAddress</strong> 属性设置了此标志位，则不会将具有此属性的联系人写入数据库。</span><span class="sxs-lookup"><span data-stu-id="c7d36-p114">If set, Address Book Server does not include objects in the AbUserEntry table that have this value for the specified attribute. For example, if the <strong>msRTCSIP-PrimaryUserAddress</strong> attribute has this flag bit set, then contacts that have this attribute are not written to the database.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c7d36-236">0x8000</span><span class="sxs-lookup"><span data-stu-id="c7d36-236">0x8000</span></span></p></td>
<td><p><span data-ttu-id="c7d36-p115">如果设置，通讯簿服务器不会在 AbUserEntry 表中包含没有为指定属性设置此值的对象。如果在一个对象上设置了 0x4000 和 0x8000 标志位，则标志位值设置为 0x4000 的属性优先，并且会在 AbUserEntry 表中排除该对象。</span><span class="sxs-lookup"><span data-stu-id="c7d36-p115">If set, Address Book Server does not include objects in the AbUserEntry table that do not have this value for the specified attribute. If both the 0x4000 and 0x8000 flag bits are set on an object, the attribute with the flag bit value set to 0x4000 takes precedence, and the object is excluded from the AbUserEntry table.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c7d36-239">0x10000</span><span class="sxs-lookup"><span data-stu-id="c7d36-239">0x10000</span></span></p></td>
<td><p><span data-ttu-id="c7d36-p116">如果设置，则代表组对象。用户复制程序使用此标志位包含具有 <strong>groupType</strong> 属性且状态指示组（例如，通讯组列表或安全组）的联系人。</span><span class="sxs-lookup"><span data-stu-id="c7d36-p116">If set, this represents a group object. User Replicator uses this flag bit to include contacts with the <strong>groupType</strong> attribute whose presence indicates a group (for example, a distribution list or security group).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c7d36-242">0x20000</span><span class="sxs-lookup"><span data-stu-id="c7d36-242">0x20000</span></span></p></td>
<td><p><span data-ttu-id="c7d36-243">如果设置，用户复制程序将使用此标志位在特定于设备的通讯簿服务器文件（即扩展名为 .dabs 的文件）中包含此属性。</span><span class="sxs-lookup"><span data-stu-id="c7d36-243">If set, User Replicator uses this flag bit to include this attribute in device-specific Address Book Server files (that is, files with a .dabs extension).</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="c7d36-244">在 Lync Server 的早期版本中，将更改应用于 Active Directory 时，管理员需要运行**CSUserDatabase**和**update – CSAddressBook** Windows PowerShell cmdlet，以立即将更改保存到 Lync Server 用户数据库和 RTCab 数据库中。</span><span class="sxs-lookup"><span data-stu-id="c7d36-244">In previous versions of Lync Server, when applying a change to Active Directory, the administrator would be required to run **Update -CSUserDatabase** and **Update –CSAddressBook** Windows PowerShell cmdlets to persist the change to the Lync Server user database and RTCab database immediately.</span></span> <span data-ttu-id="c7d36-245">在 Lync Server 2013 中，Lync Server 用户复制器将从 Active Directory 中获取更改，并根据配置的间隔更新 Lync Server 用户数据库。</span><span class="sxs-lookup"><span data-stu-id="c7d36-245">In Lync Server 2013, Lync Server User Replicator will pick up the changes from Active Directory and update the Lync Server user database based on a configured interval.</span></span> <span data-ttu-id="c7d36-246">Lync Server 用户复制程序还会快速将更改传播到 RTCab 数据库，而管理员必须运行更新-CSAddressBook。</span><span class="sxs-lookup"><span data-stu-id="c7d36-246">Lync Server User Replicator will also propagate the changes to the RTCab database quickly without the administrator having to run Update-CSAddressBook.</span></span> <span data-ttu-id="c7d36-247">如果启用了通讯簿 Web 查询，则更改将在 Lync 客户端的搜索结果中反映出来。</span><span class="sxs-lookup"><span data-stu-id="c7d36-247">If Address Book Web query is enabled, then the changes will be reflected in search results by Lync clients.</span></span> <span data-ttu-id="c7d36-248">只有在启用了通讯簿文件下载时，管理员才需要运行 CSAddressBook 更新。</span><span class="sxs-lookup"><span data-stu-id="c7d36-248">Administrators will only need to run Update -CSAddressBook if the Address Book file download is enabled.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="c7d36-249">默认情况下，Lync Server 用户复制程序每5分钟自动运行一次。</span><span class="sxs-lookup"><span data-stu-id="c7d36-249">By default Lync Server User Replicator runs automatically every 5 minutes.</span></span> <span data-ttu-id="c7d36-250">您可以使用 CSUserReplicatorConfiguration-ReplicationCycleInterval &lt; &gt;配置此间隔。</span><span class="sxs-lookup"><span data-stu-id="c7d36-250">You can configure this interval by using Set -CSUserReplicatorConfiguration -ReplicationCycleInterval &lt;&gt;.</span></span>



</div>

</div>

<div>

## <a name="filtering-the-address-book"></a><span data-ttu-id="c7d36-251">筛选通讯簿</span><span class="sxs-lookup"><span data-stu-id="c7d36-251">Filtering the Address Book</span></span>

<span data-ttu-id="c7d36-252">可以基于 AbAttribute 表中列出的某些 Active Directory 域服务属性来控制在通讯簿服务器文件中填充的用户。</span><span class="sxs-lookup"><span data-stu-id="c7d36-252">The users populated in the Address Book Server files can be controlled based on certain Active Directory Domain Services attributes listed in the AbAttribute table.</span></span> <span data-ttu-id="c7d36-253">**msExchangeHideFromAddressBook** 属性是一个用于筛选的此类属性。</span><span class="sxs-lookup"><span data-stu-id="c7d36-253">One such attribute used for filtering is the **msExchangeHideFromAddressBook** attribute.</span></span> <span data-ttu-id="c7d36-254">这是由 Exchange 架构添加的用户属性。</span><span class="sxs-lookup"><span data-stu-id="c7d36-254">This is a user attribute added by the Exchange schema.</span></span> <span data-ttu-id="c7d36-255">如果将此属性的值为 TRUE，Exchange Server 将使用此属性隐藏 Outlook 全局地址列表 (GAL) 中的联系人。</span><span class="sxs-lookup"><span data-stu-id="c7d36-255">If the value of this attribute is TRUE, Exchange Server uses this attribute to hide the contact from the Outlook Global Address List (GAL).</span></span> <span data-ttu-id="c7d36-256">同样，如果此属性的值为 TRUE，用户复制程序不会在 AbUserEntry 表中包含该用户，并且该用户不会包含在通讯簿服务器文件中。</span><span class="sxs-lookup"><span data-stu-id="c7d36-256">Similarly, if the value of this attribute is TRUE, User Replicator does not include that user in the AbUserEntry table and this user will not be in the Address Book Server files.</span></span>

<span data-ttu-id="c7d36-p120">可以使用某些标志位定义用于通讯簿服务器属性的筛选器。例如，某些标志位的状态可以将属性标识为包含属性或排除属性。用户复制程序筛选出包含排除属性的联系人，并筛选出不包含包含属性的联系人。</span><span class="sxs-lookup"><span data-stu-id="c7d36-p120">You can use some flag bits to define a filter to use on Address Book Server attributes. For example, the presence of certain flag bits can identify an attribute as an include attribute or an exclude attribute. User Replicator filters out contacts that contain an exclude attribute and filters out contains that do not contain an include attribute.</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="c7d36-260">有关筛选通讯簿的详细信息，请参阅<A href="https://technet.microsoft.com/library/gg415643(v=ocs.15)">Lync server 2013 中的通讯簿服务器 cmdlet</A>和<A href="https://go.microsoft.com/fwlink/?linkid=330430">筛选器 lync 2013 通讯簿</A></span><span class="sxs-lookup"><span data-stu-id="c7d36-260">For more information about filtering the Address Book, see <A href="https://technet.microsoft.com/library/gg415643(v=ocs.15)">Address Book Server cmdlets in Lync Server 2013</A>, and <A href="https://go.microsoft.com/fwlink/?linkid=330430">Filter Lync 2013 address book</A></span></span>



</div>

<span data-ttu-id="c7d36-p121">目前，存在三种不同的筛选器。下表列出了这些筛选器。</span><span class="sxs-lookup"><span data-stu-id="c7d36-p121">Currently, there are three different filters. The following table lists these filters.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c7d36-263">属性</span><span class="sxs-lookup"><span data-stu-id="c7d36-263">Attribute</span></span></th>
<th><span data-ttu-id="c7d36-264">说明</span><span class="sxs-lookup"><span data-stu-id="c7d36-264">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c7d36-265">0x800</span><span class="sxs-lookup"><span data-stu-id="c7d36-265">0x800</span></span></p></td>
<td><p><span data-ttu-id="c7d36-p122">如果设置，将标识联系人的必需属性。用户复制程序使用此标志位筛选出未包含至少一个必需属性的联系人。OuPathId 是必需属性，始终会设置。因此，应至少设置一个其他必需属性。否则，仍无法将联系人（即具有必需属性 OuPathId 的值）写入数据库。例如，如果将 <strong>telephoneNumber</strong> 和 <strong>homePhone</strong> 定义为必需属性，则只有至少具有其中一个属性的联系人才会写入数据库。</span><span class="sxs-lookup"><span data-stu-id="c7d36-p122">If set, this identifies a required attribute for a contact. User Replicator uses this flag bit to filter out contacts that do not contain at least one required attribute. The OuPathId is a required attribute, which is always set. So at least one of other required attributes should be set. Otherwise, contact (that is, with value of required attribute OuPathId) will still not be written to database. For example, if <strong>telephoneNumber</strong> and <strong>homePhone</strong> are defined as required attributes, only the contacts that have at least one of these attributes are written to the database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c7d36-272">0x4000</span><span class="sxs-lookup"><span data-stu-id="c7d36-272">0x4000</span></span></p></td>
<td><p><span data-ttu-id="c7d36-p123">如果设置，将标识排除属性。用户复制程序使用此标志位筛选出包含此属性的联系人。例如，如果将 <strong>msRTCSIP-PrimaryUserAddress</strong> 定义为排除属性，则不会将具有此属性的联系人写入数据库。</span><span class="sxs-lookup"><span data-stu-id="c7d36-p123">If set, this identifies an exclude attribute. User Replicator uses this flag bit to filter out contacts that contain this attribute. For example, if <strong>msRTCSIP-PrimaryUserAddress</strong> is defined as an exclude attribute, contacts that have this attribute are not written to the database.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c7d36-276">0x8000</span><span class="sxs-lookup"><span data-stu-id="c7d36-276">0x8000</span></span></p></td>
<td><p><span data-ttu-id="c7d36-p124">如果设置，将标识包含属性。用户复制程序使用此标志位筛选出不包含此属性的联系人。例如，如果将 <strong>msRTCSIP-PrimaryUserAddress</strong> 定义为包含属性，则仅将具有此属性的联系人写入数据库。</span><span class="sxs-lookup"><span data-stu-id="c7d36-p124">If set, this identifies an include attribute. User Replicator uses this flag bit to filter out contacts that do not contain this attribute. For example, if <strong>msRTCSIP-PrimaryUserAddress</strong> is defined as an include attribute, only the contacts that have this attribute are written to the database.</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="c7d36-280">如果同时设置了 0x4000（排除属性）和 0x8000（包含属性）标志位，0x4000 位将覆盖 0x8000 位，并且将排除联系人。</span><span class="sxs-lookup"><span data-stu-id="c7d36-280">If both the 0x4000 (exclude attribute) and 0x8000 (include attribute) flag bits are set, the 0x4000 bit overrides the 0x8000 bit and the contact is excluded.</span></span>



</div>

<span data-ttu-id="c7d36-p125">尽管可以筛选通讯簿以仅包含特定用户，但是限制条目不会限制其他用户联系筛选出的用户或查看其状态的能力。通过输入用户的完整登录名，用户始终可以查找通讯簿中不存在的用户，手动向这些用户发送即时消息或者手动发起呼叫。此外，还可以在 Outlook 中找到用户的联系人信息。</span><span class="sxs-lookup"><span data-stu-id="c7d36-p125">Although you can filter the Address Book to include only certain users, limiting entries does not limit other users' ability to contact the filtered users or to see their presence status. Users can always find, manually send instant messages, or manually initiate calls to users not in the Address Book by entering a user's complete sign-in name. Also, contact information for a user could also be found in Outlook.</span></span>

<span data-ttu-id="c7d36-284">通过通讯簿文件中的完整联系人记录，您可以使用 Lync Server 启动电子邮件、电话或企业语音呼叫（即，如果在服务器上启用企业语音）和未配置为进行会话初始化的用户协议（SIP），某些组织更喜欢在其通讯簿服务器条目中包含启用了 SIP 的用户。</span><span class="sxs-lookup"><span data-stu-id="c7d36-284">While having full contact records in the Address Book files enables you to use Lync Server to initiate email, telephone, or Enterprise Voice calls (that is, if Enterprise Voice is enabled on the server) with users that are not configured for Session Initiation Protocol (SIP), some organizations prefer to include only SIP-enabled users in their Address Book Server entries.</span></span> <span data-ttu-id="c7d36-285">您可以通过清除以下必需属性的**Flags**列中的0x800 位来筛选通讯簿，使其仅包含启用了 SIP 的用户： **mailNickname**、 **telephoneNumber**、 **homePhone**和**mobile**。</span><span class="sxs-lookup"><span data-stu-id="c7d36-285">You can filter the Address Book to include only SIP-enabled users by clearing the 0x800 bit in the **Flags** column of the following required attributes: **mailNickname**, **telephoneNumber**, **homePhone**, and **mobile**.</span></span> <span data-ttu-id="c7d36-286">您还可以将通讯簿筛选为仅包含启用了 SIP 的用户，方法是在**msRTCSIP-PrimaryUserAddress**属性的**Flags**列中设置0x8000 （include 属性）。</span><span class="sxs-lookup"><span data-stu-id="c7d36-286">You can also filter the Address Book to include only SIP-enabled users by setting the 0x8000 (include attribute) in the **Flags** column of the **msRTCSIP-PrimaryUserAddress** attribute.</span></span> <span data-ttu-id="c7d36-287">这还有助于从通讯簿文件中排除服务帐户。</span><span class="sxs-lookup"><span data-stu-id="c7d36-287">This also helps to exclude service accounts from the Address Book files.</span></span>

<span data-ttu-id="c7d36-288">修改 AbAttribute 表后，可以通过运行 cmdlet **Update-CsUserDatabase** 命令刷新 AbUserEntry 表中的数据。</span><span class="sxs-lookup"><span data-stu-id="c7d36-288">After you modify the AbAttribute table, you can refresh the data in the AbUserEntry table by running the cmdlet **Update-CsUserDatabase** command.</span></span> <span data-ttu-id="c7d36-289">UR 复制完成后，可以通过手动运行 cmdlet **UpdateCsAddressBook** 命令更新通讯簿服务器文件存储中的文件。</span><span class="sxs-lookup"><span data-stu-id="c7d36-289">After UR replication completes, you can update the file in the Address Book Server file store by manually running the cmdlet **UpdateCsAddressBook** command.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="c7d36-290">不能以管理方式配置通讯簿服务器所在的前端服务器。</span><span class="sxs-lookup"><span data-stu-id="c7d36-290">The Front End Server that the Address Book Server is placed is not administratively configurable.</span></span> <span data-ttu-id="c7d36-291">在部署过程中选择一个（通常是部署第一台前端服务器）。</span><span class="sxs-lookup"><span data-stu-id="c7d36-291">One is chosen during deployment—typically, the first Front End Server deployed.</span></span> <span data-ttu-id="c7d36-292">如果出现故障，通讯簿服务将移至另一台前端服务器，并且不需要管理方面的注意力。</span><span class="sxs-lookup"><span data-stu-id="c7d36-292">In the event of failure, the Address Book Service will move to another Front End Server, and requires no administrative attention.</span></span>



</div>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="c7d36-293">如果已从多林部署或父/子部署（例如，在移动到 Lync Server 之前合并基础结构）对基础结构进行了合并或其他修改，则可能会发现某些用户的通讯簿服务下载和通讯簿 Web 查询失败。</span><span class="sxs-lookup"><span data-stu-id="c7d36-293">If you have consolidated or otherwise modified your infrastructure from a multi-forest deployment or a parent/child deployment (such as consolidating your infrastructure before moving to Lync Server), you may find that the Address Book service download and the Address Book Web Query fails for some users.</span></span> <span data-ttu-id="c7d36-294">在包含多个域或林的部署中时，将在出现此问题的用户对象上填充 <STRONG>MsRTCSIP-OriginatorSid</STRONG> 属性。</span><span class="sxs-lookup"><span data-stu-id="c7d36-294">When in a deployment that had multiple domains or forests, the attribute <STRONG>MsRTCSIP-OriginatorSid</STRONG> is populated on the user objects that are exhibiting the issue.</span></span> <span data-ttu-id="c7d36-295">为了解决此问题，必须在这些对象上将 <STRONG>MsRTCSIP-OriginatorSid</STRONG> 属性设置为 NULL。</span><span class="sxs-lookup"><span data-stu-id="c7d36-295">The <STRONG>MsRTCSIP-OriginatorSid</STRONG> attribute must be set to NULL on these objects to resolve the issue.</span></span>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

