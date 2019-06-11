---
title: 'Lync Server 2013: 管理通讯簿服务'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Administering the Address Book Service
ms:assetid: 801e4243-9670-4477-aa2f-88b61ecf5351
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429711(v=OCS.15)
ms:contentKeyID: 48184649
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8acf59a898f8da14b9c5c4151728206cc501ceaf
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34837996"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="administering-the-address-book-service-in-lync-server-2013"></a><span data-ttu-id="6aac8-102">在 Lync Server 2013 中管理通讯簿服务</span><span class="sxs-lookup"><span data-stu-id="6aac8-102">Administering the Address Book Service in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6aac8-103">_**主题上次修改时间:** 2014-02-05_</span><span class="sxs-lookup"><span data-stu-id="6aac8-103">_**Topic Last Modified:** 2014-02-05_</span></span>

<span data-ttu-id="6aac8-104">作为 Lync Server、企业版或标准版服务器部署的一部分, 默认情况下会安装通讯簿服务。</span><span class="sxs-lookup"><span data-stu-id="6aac8-104">As a part of the deployment of Lync Server, Enterprise Edition or Standard Edition server, the Address Book Service is installed by default.</span></span> <span data-ttu-id="6aac8-105">通讯簿服务使用的数据库-RTCab-在 SQL Server 上创建 (对于企业版), 这是后端 SQL 服务器; 对于标准版服务器, collocated SQL Server。</span><span class="sxs-lookup"><span data-stu-id="6aac8-105">The database used by the Address Book Service – RTCab – is created on the SQL Server (for Enterprise Edition, this is the back-end SQL Server; for Standard Edition server, the collocated SQL Server).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="6aac8-106">有关使用 " <STRONG>Adsi 编辑</STRONG>" 编辑 Active Directory 域服务对象属性的信息, 请参阅<A href="http://go.microsoft.com/fwlink/?linkid=330427">ADSI edit</A>。</span><span class="sxs-lookup"><span data-stu-id="6aac8-106">For information about using <STRONG>ADSI Edit</STRONG> to edit Active Directory Domain Services object attributes, see <A href="http://go.microsoft.com/fwlink/?linkid=330427">ADSI Edit</A>.</span></span> <span data-ttu-id="6aac8-107">有关特定于通讯簿服务的资源工具包中的工具的信息, 请参阅<A href="http://go.microsoft.com/fwlink/?linkid=330429">Microsoft Lync Server 2013 资源工具包工具</A>。</span><span class="sxs-lookup"><span data-stu-id="6aac8-107">For information about a tool in the Resource Kit specifically for the Address Book service, see <A href="http://go.microsoft.com/fwlink/?linkid=330429">Microsoft Lync Server 2013 Resource Kit Tools</A>.</span></span>



</div>

<div>

## <a name="address-book-server-phone-number-normalization"></a><span data-ttu-id="6aac8-108">通讯簿服务器电话号码规范化</span><span class="sxs-lookup"><span data-stu-id="6aac8-108">Address Book Server Phone Number Normalization</span></span>

<span data-ttu-id="6aac8-109">Lync 服务器需要标准 RFC 3966/E: 164 个电话号码。</span><span class="sxs-lookup"><span data-stu-id="6aac8-109">Lync Server requires standardized RFC 3966/E.164 phone numbers.</span></span> <span data-ttu-id="6aac8-110">若要使用未结构化或格式不一致的电话号码, Lync Server 依赖于通讯簿服务器来预处理电话号码, 然后再将其移交给规范化规则。</span><span class="sxs-lookup"><span data-stu-id="6aac8-110">To use phone numbers that are unstructured or inconsistently formatted, Lync Server relies on the Address Book Server to preprocess phone numbers before they are handed off to the normalization rules.</span></span> <span data-ttu-id="6aac8-111">当从通讯簿使用电话号码并且应用规范化规则时, 客户 (如 Lync Phone Edition 和 Lync Mobile) 可以使用这些标准化的数字。</span><span class="sxs-lookup"><span data-stu-id="6aac8-111">When a phone number is used from the address book and the normalization rule is applied, clients, such as Lync Phone Edition and Lync Mobile, can use these normalized numbers.</span></span>

<span data-ttu-id="6aac8-112">无需进行一些调整, 以前版本中使用的规范化规则可能无法正常工作。</span><span class="sxs-lookup"><span data-stu-id="6aac8-112">The normalization rules that were used in previous versions may not work properly without some adjustments.</span></span> <span data-ttu-id="6aac8-113">由于在规范化规则之前删除空白和非强制字符, 因此如果你的正则表达式表达式专门查找短划线或被删除的其他字符, 则你的规范化规则可能会失败。</span><span class="sxs-lookup"><span data-stu-id="6aac8-113">Because the white space and non-mandatory characters are removed prior to the normalization rules, if your regex expression is specifically looking for a dash or other character that was removed, your normalization rule might fail.</span></span> <span data-ttu-id="6aac8-114">你应该检查你的规范化规则, 以确保它们不会查找这些非强制字符, 或者规则可以正常失败, 并在该规则预期的位置不显示字符的情况下继续执行。</span><span class="sxs-lookup"><span data-stu-id="6aac8-114">You should review your normalization rules to ensure that either they are not looking for these non-mandatory characters, or that the rule can fail gracefully and continue in the event that the character is not present where the rule anticipates it will be.</span></span>

</div>

<div>

## <a name="user-replicator-and-address-book-server"></a><span data-ttu-id="6aac8-115">用户复制程序和通讯簿服务器</span><span class="sxs-lookup"><span data-stu-id="6aac8-115">User Replicator and Address Book Server</span></span>

<span data-ttu-id="6aac8-116">通讯簿服务器使用用户复制程序提供的数据更新最初从全局地址列表 (GAL) 中获取的信息。</span><span class="sxs-lookup"><span data-stu-id="6aac8-116">The Address Book Server uses data provided by User Replicator to update the information that it initially obtains from the global address list (GAL).</span></span> <span data-ttu-id="6aac8-117">用户复制程序将每个用户、联系人和组的 Active Directory 域服务属性写入数据库中的 AbUserEntry 表, 通讯簿服务器将数据库中的用户数据同步到通讯簿服务器文件存储中的文件和插入通讯簿数据库 RTCab。</span><span class="sxs-lookup"><span data-stu-id="6aac8-117">User Replicator writes the Active Directory Domain Services attributes for each user, contact, and group into the AbUserEntry table in the database and the Address Book Server syncs the user data from the database into files in the Address Book Server file store and into the Address Book database RTCab.</span></span> <span data-ttu-id="6aac8-118">AbUserEntry 表的架构使用两列**UserGuid**和**UserData**。</span><span class="sxs-lookup"><span data-stu-id="6aac8-118">The schema for the AbUserEntry table uses two columns, **UserGuid** and **UserData**.</span></span> <span data-ttu-id="6aac8-119">**UserGuid**是 index 列, 其中包含 Active Directory 对象的16字节 GUID。</span><span class="sxs-lookup"><span data-stu-id="6aac8-119">**UserGuid** is the index column and contains the 16-byte GUID of the Active Directory object.</span></span> <span data-ttu-id="6aac8-120">**UserData**是一个图像列, 其中包含该联系人的所有前面提到的 Active Directory 域服务属性。</span><span class="sxs-lookup"><span data-stu-id="6aac8-120">**UserData** is an image column which contains all of the previously mentioned Active Directory Domain Services attributes for that contact.</span></span>

<span data-ttu-id="6aac8-121">用户复制器通过读取位于基于 SQL Server 的同一 SQL 实例中的配置表来确定要写入哪些 Active Directory 属性。 AbUserEntry 表。</span><span class="sxs-lookup"><span data-stu-id="6aac8-121">User Replicator determines which Active Directory attributes to write by reading a configuration table located in the same SQL Server-based instance as the AbUserEntry table.</span></span> <span data-ttu-id="6aac8-122">AbAttribute 表包含三列、 **ID**、**名称**、**标志**和**Enable**。</span><span class="sxs-lookup"><span data-stu-id="6aac8-122">The AbAttribute table contains three columns, **ID**, **Name**, **Flags**, and **Enable**.</span></span> <span data-ttu-id="6aac8-123">该表在数据库安装期间创建。</span><span class="sxs-lookup"><span data-stu-id="6aac8-123">The table is created during database setup.</span></span> <span data-ttu-id="6aac8-124">如果 AbAttribute 表为空, 则用户副本将跳过其 AbUserEntry 表处理逻辑。</span><span class="sxs-lookup"><span data-stu-id="6aac8-124">If the AbAttribute table is empty, User Replicator skips its AbUserEntry table processing logic.</span></span> <span data-ttu-id="6aac8-125">通讯簿服务器属性是动态的, 从 AbAttribute 表中检索, 它是在激活通讯簿服务器时由通讯簿服务器初始编写的。</span><span class="sxs-lookup"><span data-stu-id="6aac8-125">Address Book Server attributes are dynamic and are retrieved from the AbAttribute table, which is initially written by the Address Book Server when the Address Book Server is activated.</span></span>

<span data-ttu-id="6aac8-126">通讯簿服务器激活用下表中所示的值填充 AbAttribute 表。</span><span class="sxs-lookup"><span data-stu-id="6aac8-126">Address Book Server activation populates the AbAttribute table with the values shown in the following table.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="6aac8-127">ID</span><span class="sxs-lookup"><span data-stu-id="6aac8-127">ID</span></span></th>
<th><span data-ttu-id="6aac8-128">名称</span><span class="sxs-lookup"><span data-stu-id="6aac8-128">Name</span></span></th>
<th><span data-ttu-id="6aac8-129">标志</span><span class="sxs-lookup"><span data-stu-id="6aac8-129">Flags</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6aac8-130">1</span><span class="sxs-lookup"><span data-stu-id="6aac8-130">1</span></span></p></td>
<td><p><span data-ttu-id="6aac8-131">givenName</span><span class="sxs-lookup"><span data-stu-id="6aac8-131">givenName</span></span></p></td>
<td><p><span data-ttu-id="6aac8-132">0x01400000</span><span class="sxs-lookup"><span data-stu-id="6aac8-132">0x01400000</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6aac8-133">2</span><span class="sxs-lookup"><span data-stu-id="6aac8-133">2</span></span></p></td>
<td><p><span data-ttu-id="6aac8-134">Sn</span><span class="sxs-lookup"><span data-stu-id="6aac8-134">Sn</span></span></p></td>
<td><p><span data-ttu-id="6aac8-135">0x02400000</span><span class="sxs-lookup"><span data-stu-id="6aac8-135">0x02400000</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6aac8-136">3</span><span class="sxs-lookup"><span data-stu-id="6aac8-136">3</span></span></p></td>
<td><p><span data-ttu-id="6aac8-137">displayName</span><span class="sxs-lookup"><span data-stu-id="6aac8-137">displayName</span></span></p></td>
<td><p><span data-ttu-id="6aac8-138">0x03420000</span><span class="sxs-lookup"><span data-stu-id="6aac8-138">0x03420000</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6aac8-139">4</span><span class="sxs-lookup"><span data-stu-id="6aac8-139">4</span></span></p></td>
<td><p><span data-ttu-id="6aac8-140">标题</span><span class="sxs-lookup"><span data-stu-id="6aac8-140">Title</span></span></p></td>
<td><p><span data-ttu-id="6aac8-141">0x04000000</span><span class="sxs-lookup"><span data-stu-id="6aac8-141">0x04000000</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6aac8-142">5</span><span class="sxs-lookup"><span data-stu-id="6aac8-142">5</span></span></p></td>
<td><p><span data-ttu-id="6aac8-143">mailNickname</span><span class="sxs-lookup"><span data-stu-id="6aac8-143">mailNickname</span></span></p></td>
<td><p><span data-ttu-id="6aac8-144">0x05400000</span><span class="sxs-lookup"><span data-stu-id="6aac8-144">0x05400000</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6aac8-145">6</span><span class="sxs-lookup"><span data-stu-id="6aac8-145">6</span></span></p></td>
<td><p><span data-ttu-id="6aac8-146">子公司</span><span class="sxs-lookup"><span data-stu-id="6aac8-146">Company</span></span></p></td>
<td><p><span data-ttu-id="6aac8-147">0x06000000</span><span class="sxs-lookup"><span data-stu-id="6aac8-147">0x06000000</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6aac8-148">7</span><span class="sxs-lookup"><span data-stu-id="6aac8-148">7</span></span></p></td>
<td><p><span data-ttu-id="6aac8-149">physicalDeliveryOfficeName</span><span class="sxs-lookup"><span data-stu-id="6aac8-149">physicalDeliveryOfficeName</span></span></p></td>
<td><p><span data-ttu-id="6aac8-150">0x07000000</span><span class="sxs-lookup"><span data-stu-id="6aac8-150">0x07000000</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6aac8-151">个</span><span class="sxs-lookup"><span data-stu-id="6aac8-151">8</span></span></p></td>
<td><p><span data-ttu-id="6aac8-152">msRTCSIP-PrimaryUserAddress</span><span class="sxs-lookup"><span data-stu-id="6aac8-152">msRTCSIP-PrimaryUserAddress</span></span></p></td>
<td><p><span data-ttu-id="6aac8-153">0x08520C00</span><span class="sxs-lookup"><span data-stu-id="6aac8-153">0x08520C00</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6aac8-154">db-9</span><span class="sxs-lookup"><span data-stu-id="6aac8-154">9</span></span></p></td>
<td><p><span data-ttu-id="6aac8-155">telephoneNumber</span><span class="sxs-lookup"><span data-stu-id="6aac8-155">telephoneNumber</span></span></p></td>
<td><p><span data-ttu-id="6aac8-156">0x09022800</span><span class="sxs-lookup"><span data-stu-id="6aac8-156">0x09022800</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6aac8-157">10</span><span class="sxs-lookup"><span data-stu-id="6aac8-157">10</span></span></p></td>
<td><p><span data-ttu-id="6aac8-158">homePhone</span><span class="sxs-lookup"><span data-stu-id="6aac8-158">homePhone</span></span></p></td>
<td><p><span data-ttu-id="6aac8-159">0x0A302800</span><span class="sxs-lookup"><span data-stu-id="6aac8-159">0x0A302800</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6aac8-160">11</span><span class="sxs-lookup"><span data-stu-id="6aac8-160">11</span></span></p></td>
<td><p><span data-ttu-id="6aac8-161">移动</span><span class="sxs-lookup"><span data-stu-id="6aac8-161">Mobile</span></span></p></td>
<td><p><span data-ttu-id="6aac8-162">0x0B622800</span><span class="sxs-lookup"><span data-stu-id="6aac8-162">0x0B622800</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6aac8-163">至</span><span class="sxs-lookup"><span data-stu-id="6aac8-163">12</span></span></p></td>
<td><p><span data-ttu-id="6aac8-164">otherTelephone</span><span class="sxs-lookup"><span data-stu-id="6aac8-164">otherTelephone</span></span></p></td>
<td><p><span data-ttu-id="6aac8-165">0x0C302000</span><span class="sxs-lookup"><span data-stu-id="6aac8-165">0x0C302000</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6aac8-166">13</span><span class="sxs-lookup"><span data-stu-id="6aac8-166">13</span></span></p></td>
<td><p><span data-ttu-id="6aac8-167">ipPhone</span><span class="sxs-lookup"><span data-stu-id="6aac8-167">ipPhone</span></span></p></td>
<td><p><span data-ttu-id="6aac8-168">0x0D302000</span><span class="sxs-lookup"><span data-stu-id="6aac8-168">0x0D302000</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6aac8-169">14</span><span class="sxs-lookup"><span data-stu-id="6aac8-169">14</span></span></p></td>
<td><p><span data-ttu-id="6aac8-170">邮件</span><span class="sxs-lookup"><span data-stu-id="6aac8-170">Mail</span></span></p></td>
<td><p><span data-ttu-id="6aac8-171">0x0E500000</span><span class="sxs-lookup"><span data-stu-id="6aac8-171">0x0E500000</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6aac8-172">岁</span><span class="sxs-lookup"><span data-stu-id="6aac8-172">15</span></span></p></td>
<td><p><span data-ttu-id="6aac8-173">groupType</span><span class="sxs-lookup"><span data-stu-id="6aac8-173">groupType</span></span></p></td>
<td><p><span data-ttu-id="6aac8-174">0x0F010800</span><span class="sxs-lookup"><span data-stu-id="6aac8-174">0x0F010800</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6aac8-175">utf-16</span><span class="sxs-lookup"><span data-stu-id="6aac8-175">16</span></span></p></td>
<td><p><span data-ttu-id="6aac8-176">部门</span><span class="sxs-lookup"><span data-stu-id="6aac8-176">Department</span></span></p></td>
<td><p><span data-ttu-id="6aac8-177">0x10000000</span><span class="sxs-lookup"><span data-stu-id="6aac8-177">0x10000000</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6aac8-178">日</span><span class="sxs-lookup"><span data-stu-id="6aac8-178">17</span></span></p></td>
<td><p><span data-ttu-id="6aac8-179">说明</span><span class="sxs-lookup"><span data-stu-id="6aac8-179">Description</span></span></p></td>
<td><p><span data-ttu-id="6aac8-180">0x11000100</span><span class="sxs-lookup"><span data-stu-id="6aac8-180">0x11000100</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6aac8-181">18</span><span class="sxs-lookup"><span data-stu-id="6aac8-181">18</span></span></p></td>
<td><p><span data-ttu-id="6aac8-182">经理</span><span class="sxs-lookup"><span data-stu-id="6aac8-182">Manager</span></span></p></td>
<td><p><span data-ttu-id="6aac8-183">0x12040001</span><span class="sxs-lookup"><span data-stu-id="6aac8-183">0x12040001</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6aac8-184">19</span><span class="sxs-lookup"><span data-stu-id="6aac8-184">19</span></span></p></td>
<td><p><span data-ttu-id="6aac8-185">proxyAddress</span><span class="sxs-lookup"><span data-stu-id="6aac8-185">proxyAddress</span></span></p></td>
<td><p><span data-ttu-id="6aac8-186">0x00500105</span><span class="sxs-lookup"><span data-stu-id="6aac8-186">0x00500105</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6aac8-187">名</span><span class="sxs-lookup"><span data-stu-id="6aac8-187">20</span></span></p></td>
<td><p><span data-ttu-id="6aac8-188">msExchHideFromAddressLists</span><span class="sxs-lookup"><span data-stu-id="6aac8-188">msExchHideFromAddressLists</span></span></p></td>
<td><p><span data-ttu-id="6aac8-189">0xFF000003</span><span class="sxs-lookup"><span data-stu-id="6aac8-189">0xFF000003</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6aac8-190">99</span><span class="sxs-lookup"><span data-stu-id="6aac8-190">99</span></span></p></td>
<td><p><span data-ttu-id="6aac8-191">条目</span><span class="sxs-lookup"><span data-stu-id="6aac8-191">entryID</span></span></p></td>
<td><p><span data-ttu-id="6aac8-192">0x99000000</span><span class="sxs-lookup"><span data-stu-id="6aac8-192">0x99000000</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="6aac8-193">**ID**列中的数字必须是唯一的, 并且永远不应重复使用。</span><span class="sxs-lookup"><span data-stu-id="6aac8-193">The numbers in the **ID** column must be unique and should never be reused.</span></span> <span data-ttu-id="6aac8-194">此外, 在256下保留 ID 值可节省由通讯簿服务器写入的输出文件中的空间。</span><span class="sxs-lookup"><span data-stu-id="6aac8-194">Also, keeping the ID values under 256 saves space in the output files written by the Address Book Server.</span></span> <span data-ttu-id="6aac8-195">但是, 最大 ID 值为65535。</span><span class="sxs-lookup"><span data-stu-id="6aac8-195">However, the maximum ID value is 65535.</span></span> <span data-ttu-id="6aac8-196">"**名称**" 列对应于每个联系人的 AbUserEntry 表中用户复制器应放置的 Active Directory 属性名称。</span><span class="sxs-lookup"><span data-stu-id="6aac8-196">The **Name** column corresponds to the Active Directory attribute name that User Replicator should put in the AbUserEntry table for each contact.</span></span> <span data-ttu-id="6aac8-197">**Flags**列中的值用于定义属性的类型。</span><span class="sxs-lookup"><span data-stu-id="6aac8-197">The value in the **Flags** column is used to define the type of attribute.</span></span> <span data-ttu-id="6aac8-198">以下类型的通讯簿服务器属性可由用户复制程序识别, 由 "**标志**" 列中值的低字节表示。</span><span class="sxs-lookup"><span data-stu-id="6aac8-198">The following types of Address Book Server attributes are recognized by User Replicator, indicated by the low byte of the value in the **Flags** column.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="6aac8-199">属性</span><span class="sxs-lookup"><span data-stu-id="6aac8-199">Attribute</span></span></th>
<th><span data-ttu-id="6aac8-200">描述</span><span class="sxs-lookup"><span data-stu-id="6aac8-200">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6aac8-201">0x0</span><span class="sxs-lookup"><span data-stu-id="6aac8-201">0x0</span></span></p></td>
<td><p><span data-ttu-id="6aac8-202">字符串属性。</span><span class="sxs-lookup"><span data-stu-id="6aac8-202">A string attribute.</span></span> <span data-ttu-id="6aac8-203">在将此类型存储在 AbUserEntry 表中之前, 用户副本会将此类型转换为 UTF-8。</span><span class="sxs-lookup"><span data-stu-id="6aac8-203">User Replicator converts this type to UTF-8 before storing it in the AbUserEntry table.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6aac8-204">0x1</span><span class="sxs-lookup"><span data-stu-id="6aac8-204">0x1</span></span></p></td>
<td><p><span data-ttu-id="6aac8-205">二进制属性。</span><span class="sxs-lookup"><span data-stu-id="6aac8-205">A binary attribute.</span></span> <span data-ttu-id="6aac8-206">用户复制程序将此存储在 blob 中, 无需任何转换。</span><span class="sxs-lookup"><span data-stu-id="6aac8-206">User Replicator stores this in the blob without any conversion.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6aac8-207">反</span><span class="sxs-lookup"><span data-stu-id="6aac8-207">0x2</span></span></p></td>
<td><p><span data-ttu-id="6aac8-208">字符串属性, 但仅当属性值以&quot;电话:&quot;开始时才包括该属性。</span><span class="sxs-lookup"><span data-stu-id="6aac8-208">A string attribute, but is included only if the attribute value begins with &quot;tel:&quot;.</span></span> <span data-ttu-id="6aac8-209">这主要适用于多值字符串属性, 特别是<strong>proxyAddresses</strong>。</span><span class="sxs-lookup"><span data-stu-id="6aac8-209">This is primarily for multi-valued string attributes, specifically <strong>proxyAddresses</strong>.</span></span> <span data-ttu-id="6aac8-210">在这种情况下, 通讯簿服务器仅感兴趣的<strong>proxyAddresses</strong>条目以&quot;电话开始&quot;:。</span><span class="sxs-lookup"><span data-stu-id="6aac8-210">In this case, Address Book Server is interested only in <strong>proxyAddresses</strong> entries that begin with &quot;tel:&quot;.</span></span> <span data-ttu-id="6aac8-211">因此, 为了节省空间, 用户复制器仅存储以&quot;电话开始的条目:。&quot;</span><span class="sxs-lookup"><span data-stu-id="6aac8-211">Therefore, in the interest of saving space, User Replicator stores only the entries that begin with &quot;tel:&quot;.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6aac8-212">0x3</span><span class="sxs-lookup"><span data-stu-id="6aac8-212">0x3</span></span></p></td>
<td><p><span data-ttu-id="6aac8-213">布尔字符串属性, 如果 TRUE, 则在 AbUserEntry 表中导致用户副本不包含此联系人。</span><span class="sxs-lookup"><span data-stu-id="6aac8-213">A Boolean string attribute, which if TRUE causes User Replicator to not include this contact in the AbUserEntry table.</span></span> <span data-ttu-id="6aac8-214">如果为 FALSE, 则会导致用户复制器在 AbUserEntry 表中包含此联系人的属性, 而不是此标志的特定属性。</span><span class="sxs-lookup"><span data-stu-id="6aac8-214">If FALSE, it causes User Replicator to include the attributes for this contact in the AbUserEntry table, but not the particular attribute with this flag.</span></span> <span data-ttu-id="6aac8-215">这是一个主要用于<strong>msExchHideFromAddressLists</strong>属性的特殊情况类型。</span><span class="sxs-lookup"><span data-stu-id="6aac8-215">This is another special case type that is primarily for the <strong>msExchHideFromAddressLists</strong> attribute.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6aac8-216">0x4</span><span class="sxs-lookup"><span data-stu-id="6aac8-216">0x4</span></span></p></td>
<td><p><span data-ttu-id="6aac8-217">字符串&quot;属性, 但仅当属性值以 smtp:&quot;开头并包含符号时才包括该&quot; @ &quot;属性。</span><span class="sxs-lookup"><span data-stu-id="6aac8-217">A string attribute, but is included only if the attribute value begins with &quot;smtp:&quot; and includes the &quot;@&quot; symbol.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6aac8-218">0x5</span><span class="sxs-lookup"><span data-stu-id="6aac8-218">0x5</span></span></p></td>
<td><p><span data-ttu-id="6aac8-219">字符串属性, 但仅当属性&quot;值以电话:&quot;或&quot;smtp:&quot;开头, 并且包括&quot; @ &quot;符号时才包括该属性。</span><span class="sxs-lookup"><span data-stu-id="6aac8-219">A string attribute, but is included only if the attribute value begins with either &quot;tel:&quot; or &quot;smtp:&quot; and includes the &quot;@&quot; symbol.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6aac8-220">0x100</span><span class="sxs-lookup"><span data-stu-id="6aac8-220">0x100</span></span></p></td>
<td><p><span data-ttu-id="6aac8-221">如果设置, 这是一个多值属性, 可以为每个联系人多次显示。</span><span class="sxs-lookup"><span data-stu-id="6aac8-221">If set, this is a multi-valued attribute that can appear more than once for each contact.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6aac8-222">0x400</span><span class="sxs-lookup"><span data-stu-id="6aac8-222">0x400</span></span></p></td>
<td><p><span data-ttu-id="6aac8-223">如果设置, 这将标识联系人的电子邮件用户帐户名属性。</span><span class="sxs-lookup"><span data-stu-id="6aac8-223">If set, this identifies the email user account name attribute for a contact.</span></span> <span data-ttu-id="6aac8-224">通讯簿服务器使用此标志标识要在电话规范化事件日志条目中显示的属性值。</span><span class="sxs-lookup"><span data-stu-id="6aac8-224">Address Book Server uses this flag to identify which attribute value to show in the phone normalization event log entry.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6aac8-225">0x800</span><span class="sxs-lookup"><span data-stu-id="6aac8-225">0x800</span></span></p></td>
<td><p><span data-ttu-id="6aac8-226">如果设置, 这将标识联系人的必需属性。</span><span class="sxs-lookup"><span data-stu-id="6aac8-226">If set, this identifies a required attribute for a contact.</span></span> <span data-ttu-id="6aac8-227">只有当 Active Directory 中有此属性的值时, 通讯簿服务器才在 AbUserEntry 表中包含用户。</span><span class="sxs-lookup"><span data-stu-id="6aac8-227">Address Book Server includes a user in the AbUserEntry table only if there is a value for this attribute in Active Directory.</span></span> <span data-ttu-id="6aac8-228">如果存在多个必需的属性, 则只有其中一个值需要具有一个值才能将用户包括在 AbUserEntry 表中。</span><span class="sxs-lookup"><span data-stu-id="6aac8-228">If there is more than one required attribute, only one of them is required to have a value to include the user in the AbUserEntry table.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6aac8-229">0x1000</span><span class="sxs-lookup"><span data-stu-id="6aac8-229">0x1000</span></span></p></td>
<td><p><span data-ttu-id="6aac8-230">如果设置, 通讯簿服务器将始终对此属性的值进行标准化。</span><span class="sxs-lookup"><span data-stu-id="6aac8-230">If set, Address Book Server always normalizes the value of this attribute.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6aac8-231">0x2000</span><span class="sxs-lookup"><span data-stu-id="6aac8-231">0x2000</span></span></p></td>
<td><p><span data-ttu-id="6aac8-232">如果设置, 通讯簿服务器将使用<strong>proxyAddresses</strong>中的标准化数字 (如果<strong>UseNormalizationRules</strong> CMS 设置为 FALSE);否则, 其行为与标志位为0x1000 的情况相同。</span><span class="sxs-lookup"><span data-stu-id="6aac8-232">If set, Address Book Server uses the normalized number from <strong>proxyAddresses</strong>, if the <strong>UseNormalizationRules</strong> CMS setting is FALSE; otherwise it behaves the same as when the flag bit is 0x1000.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6aac8-233">0x4000</span><span class="sxs-lookup"><span data-stu-id="6aac8-233">0x4000</span></span></p></td>
<td><p><span data-ttu-id="6aac8-234">如果设置, 通讯簿服务器将不包括 AbUserEntry 表中具有指定属性的此值的对象。</span><span class="sxs-lookup"><span data-stu-id="6aac8-234">If set, Address Book Server does not include objects in the AbUserEntry table that have this value for the specified attribute.</span></span> <span data-ttu-id="6aac8-235">例如, 如果<strong>msRTCSIP-PrimaryUserAddress</strong>属性具有此标志位集, 则具有此属性的联系人不会写入数据库。</span><span class="sxs-lookup"><span data-stu-id="6aac8-235">For example, if the <strong>msRTCSIP-PrimaryUserAddress</strong> attribute has this flag bit set, then contacts that have this attribute are not written to the database.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6aac8-236">0x8000</span><span class="sxs-lookup"><span data-stu-id="6aac8-236">0x8000</span></span></p></td>
<td><p><span data-ttu-id="6aac8-237">如果设置, 通讯簿服务器将不包含 AbUserEntry 表中的对象, 指定的属性没有此值。</span><span class="sxs-lookup"><span data-stu-id="6aac8-237">If set, Address Book Server does not include objects in the AbUserEntry table that do not have this value for the specified attribute.</span></span> <span data-ttu-id="6aac8-238">如果在对象上设置了0x4000 和0x8000 标志位, 则将优先使用标志位值设置为0x4000 的属性, 并将该对象从 AbUserEntry 表中排除。</span><span class="sxs-lookup"><span data-stu-id="6aac8-238">If both the 0x4000 and 0x8000 flag bits are set on an object, the attribute with the flag bit value set to 0x4000 takes precedence, and the object is excluded from the AbUserEntry table.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6aac8-239">0x10000</span><span class="sxs-lookup"><span data-stu-id="6aac8-239">0x10000</span></span></p></td>
<td><p><span data-ttu-id="6aac8-240">如果设置, 则表示群组对象。</span><span class="sxs-lookup"><span data-stu-id="6aac8-240">If set, this represents a group object.</span></span> <span data-ttu-id="6aac8-241">用户复制器使用此标志位将联系人与<strong>groupType</strong>属性 (其状态表示 "通讯组列表" 或 "安全组") 一起包含。</span><span class="sxs-lookup"><span data-stu-id="6aac8-241">User Replicator uses this flag bit to include contacts with the <strong>groupType</strong> attribute whose presence indicates a group (for example, a distribution list or security group).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6aac8-242">0x20000</span><span class="sxs-lookup"><span data-stu-id="6aac8-242">0x20000</span></span></p></td>
<td><p><span data-ttu-id="6aac8-243">如果设置, 则用户复制器使用此标志 bit 将此属性包含在特定于设备的通讯簿服务器文件中 (即扩展名为 dabs 的文件)。</span><span class="sxs-lookup"><span data-stu-id="6aac8-243">If set, User Replicator uses this flag bit to include this attribute in device-specific Address Book Server files (that is, files with a .dabs extension).</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="6aac8-244">在早期版本的 Lync Server 中, 当应用对 Active Directory 的更改时, 管理员需要运行**CSUserDatabase**和**update-CSAddressBook** Windows PowerShell cmdlet 以将更改保存到 Lync 服务器用户数据库和 RTCab 数据库立即使用。</span><span class="sxs-lookup"><span data-stu-id="6aac8-244">In previous versions of Lync Server, when applying a change to Active Directory, the administrator would be required to run **Update -CSUserDatabase** and **Update –CSAddressBook** Windows PowerShell cmdlets to persist the change to the Lync Server user database and RTCab database immediately.</span></span> <span data-ttu-id="6aac8-245">在 Lync Server 2013 中, Lync Server 用户复制程序将从 Active Directory 中获取更改, 并根据配置的间隔更新 Lync Server 用户数据库。</span><span class="sxs-lookup"><span data-stu-id="6aac8-245">In Lync Server 2013, Lync Server User Replicator will pick up the changes from Active Directory and update the Lync Server user database based on a configured interval.</span></span> <span data-ttu-id="6aac8-246">Lync Server 用户复制程序还将在无需运行 CSAddressBook 的情况下快速将更改传播到 RTCab 数据库。</span><span class="sxs-lookup"><span data-stu-id="6aac8-246">Lync Server User Replicator will also propagate the changes to the RTCab database quickly without the administrator having to run Update-CSAddressBook.</span></span> <span data-ttu-id="6aac8-247">如果启用了 "通讯簿" Web 查询, 则这些更改将反映在 Lync 客户端的搜索结果中。</span><span class="sxs-lookup"><span data-stu-id="6aac8-247">If Address Book Web query is enabled, then the changes will be reflected in search results by Lync clients.</span></span> <span data-ttu-id="6aac8-248">只有当通讯簿文件下载已启用时, 管理员才需要运行 CSAddressBook 更新。</span><span class="sxs-lookup"><span data-stu-id="6aac8-248">Administrators will only need to run Update -CSAddressBook if the Address Book file download is enabled.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="6aac8-249">默认情况下, Lync Server 用户复制程序每隔5分钟自动运行一次。</span><span class="sxs-lookup"><span data-stu-id="6aac8-249">By default Lync Server User Replicator runs automatically every 5 minutes.</span></span> <span data-ttu-id="6aac8-250">你可以使用 CSUserReplicatorConfiguration-ReplicationCycleInterval &lt; &gt;配置此间隔。</span><span class="sxs-lookup"><span data-stu-id="6aac8-250">You can configure this interval by using Set -CSUserReplicatorConfiguration -ReplicationCycleInterval &lt;&gt;.</span></span>



</div>

</div>

<div>

## <a name="filtering-the-address-book"></a><span data-ttu-id="6aac8-251">筛选通讯簿</span><span class="sxs-lookup"><span data-stu-id="6aac8-251">Filtering the Address Book</span></span>

<span data-ttu-id="6aac8-252">根据 AbAttribute 表中列出的某些 Active Directory 域服务属性, 可以控制在通讯簿服务器文件中填充的用户。</span><span class="sxs-lookup"><span data-stu-id="6aac8-252">The users populated in the Address Book Server files can be controlled based on certain Active Directory Domain Services attributes listed in the AbAttribute table.</span></span> <span data-ttu-id="6aac8-253">用于筛选的一个此类属性是**msExchangeHideFromAddressBook**属性。</span><span class="sxs-lookup"><span data-stu-id="6aac8-253">One such attribute used for filtering is the **msExchangeHideFromAddressBook** attribute.</span></span> <span data-ttu-id="6aac8-254">这是 Exchange 架构添加的用户属性。</span><span class="sxs-lookup"><span data-stu-id="6aac8-254">This is a user attribute added by the Exchange schema.</span></span> <span data-ttu-id="6aac8-255">如果此属性的值为 TRUE, Exchange Server 将使用此属性从 Outlook 全球通讯簿 (GAL) 中隐藏联系人。</span><span class="sxs-lookup"><span data-stu-id="6aac8-255">If the value of this attribute is TRUE, Exchange Server uses this attribute to hide the contact from the Outlook Global Address List (GAL).</span></span> <span data-ttu-id="6aac8-256">同样, 如果此属性的值为 TRUE, 则用户复制程序不会在 AbUserEntry 表中包含该用户, 并且此用户将不会位于通讯簿服务器文件中。</span><span class="sxs-lookup"><span data-stu-id="6aac8-256">Similarly, if the value of this attribute is TRUE, User Replicator does not include that user in the AbUserEntry table and this user will not be in the Address Book Server files.</span></span>

<span data-ttu-id="6aac8-257">可以使用某些标志位来定义要在通讯簿服务器属性中使用的筛选器。</span><span class="sxs-lookup"><span data-stu-id="6aac8-257">You can use some flag bits to define a filter to use on Address Book Server attributes.</span></span> <span data-ttu-id="6aac8-258">例如, 某些标志位的存在可以将属性标识为 include 属性或 exclude 属性。</span><span class="sxs-lookup"><span data-stu-id="6aac8-258">For example, the presence of certain flag bits can identify an attribute as an include attribute or an exclude attribute.</span></span> <span data-ttu-id="6aac8-259">用户复制程序筛选出包含 "排除" 属性的联系人, 并且筛选器包含不包含 "包含" 属性的筛选器。</span><span class="sxs-lookup"><span data-stu-id="6aac8-259">User Replicator filters out contacts that contain an exclude attribute and filters out contains that do not contain an include attribute.</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="6aac8-260">有关筛选通讯簿的详细信息, 请参阅<A href="https://technet.microsoft.com/en-us/library/gg415643(v=ocs.15)">Lync server 2013 中的通讯簿服务器 cmdlet</A>和<A href="http://go.microsoft.com/fwlink/?linkid=330430">筛选 lync 2013 通讯簿</A></span><span class="sxs-lookup"><span data-stu-id="6aac8-260">For more information about filtering the Address Book, see <A href="https://technet.microsoft.com/en-us/library/gg415643(v=ocs.15)">Address Book Server cmdlets in Lync Server 2013</A>, and <A href="http://go.microsoft.com/fwlink/?linkid=330430">Filter Lync 2013 address book</A></span></span>



</div>

<span data-ttu-id="6aac8-261">目前有三种不同的筛选器。</span><span class="sxs-lookup"><span data-stu-id="6aac8-261">Currently, there are three different filters.</span></span> <span data-ttu-id="6aac8-262">下表列出了这些筛选器。</span><span class="sxs-lookup"><span data-stu-id="6aac8-262">The following table lists these filters.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="6aac8-263">属性</span><span class="sxs-lookup"><span data-stu-id="6aac8-263">Attribute</span></span></th>
<th><span data-ttu-id="6aac8-264">描述</span><span class="sxs-lookup"><span data-stu-id="6aac8-264">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6aac8-265">0x800</span><span class="sxs-lookup"><span data-stu-id="6aac8-265">0x800</span></span></p></td>
<td><p><span data-ttu-id="6aac8-266">如果设置, 这将标识联系人的必需属性。</span><span class="sxs-lookup"><span data-stu-id="6aac8-266">If set, this identifies a required attribute for a contact.</span></span> <span data-ttu-id="6aac8-267">用户复制程序使用此标志位筛选出不包含至少一个必需属性的联系人。</span><span class="sxs-lookup"><span data-stu-id="6aac8-267">User Replicator uses this flag bit to filter out contacts that do not contain at least one required attribute.</span></span> <span data-ttu-id="6aac8-268">OuPathId 是一个必需的属性, 它是始终设置的。</span><span class="sxs-lookup"><span data-stu-id="6aac8-268">The OuPathId is a required attribute, which is always set.</span></span> <span data-ttu-id="6aac8-269">因此, 至少应设置其他所需的属性之一。</span><span class="sxs-lookup"><span data-stu-id="6aac8-269">So at least one of other required attributes should be set.</span></span> <span data-ttu-id="6aac8-270">否则, 联系人 (即具有必需属性 OuPathId 的值) 仍不会写入到数据库中。</span><span class="sxs-lookup"><span data-stu-id="6aac8-270">Otherwise, contact (that is, with value of required attribute OuPathId) will still not be written to database.</span></span> <span data-ttu-id="6aac8-271">例如, 如果<strong>telephoneNumber</strong>和<strong>homePhone</strong>定义为所需的属性, 则只有至少包含这些属性之一的联系人才会写入数据库。</span><span class="sxs-lookup"><span data-stu-id="6aac8-271">For example, if <strong>telephoneNumber</strong> and <strong>homePhone</strong> are defined as required attributes, only the contacts that have at least one of these attributes are written to the database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6aac8-272">0x4000</span><span class="sxs-lookup"><span data-stu-id="6aac8-272">0x4000</span></span></p></td>
<td><p><span data-ttu-id="6aac8-273">如果设置, 这将标识 "排除" 属性。</span><span class="sxs-lookup"><span data-stu-id="6aac8-273">If set, this identifies an exclude attribute.</span></span> <span data-ttu-id="6aac8-274">用户复制程序使用此标志位筛选出包含此属性的联系人。</span><span class="sxs-lookup"><span data-stu-id="6aac8-274">User Replicator uses this flag bit to filter out contacts that contain this attribute.</span></span> <span data-ttu-id="6aac8-275">例如, 如果<strong>msRTCSIP-PrimaryUserAddress</strong>定义为 exclude 属性, 则具有此属性的联系人不会写入数据库。</span><span class="sxs-lookup"><span data-stu-id="6aac8-275">For example, if <strong>msRTCSIP-PrimaryUserAddress</strong> is defined as an exclude attribute, contacts that have this attribute are not written to the database.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6aac8-276">0x8000</span><span class="sxs-lookup"><span data-stu-id="6aac8-276">0x8000</span></span></p></td>
<td><p><span data-ttu-id="6aac8-277">如果设置, 这将标识一个 include 属性。</span><span class="sxs-lookup"><span data-stu-id="6aac8-277">If set, this identifies an include attribute.</span></span> <span data-ttu-id="6aac8-278">用户复制程序使用此标志位筛选出不包含此属性的联系人。</span><span class="sxs-lookup"><span data-stu-id="6aac8-278">User Replicator uses this flag bit to filter out contacts that do not contain this attribute.</span></span> <span data-ttu-id="6aac8-279">例如, 如果<strong>msRTCSIP-PrimaryUserAddress</strong>定义为 include 属性, 则仅将具有此属性的联系人写入数据库。</span><span class="sxs-lookup"><span data-stu-id="6aac8-279">For example, if <strong>msRTCSIP-PrimaryUserAddress</strong> is defined as an include attribute, only the contacts that have this attribute are written to the database.</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="6aac8-280">如果同时设置了 0x4000 (exclude 属性) 和 0x8000 (include 属性) 标志位, 则0x4000 位将重写0x8000 位, 并且将排除该联系人。</span><span class="sxs-lookup"><span data-stu-id="6aac8-280">If both the 0x4000 (exclude attribute) and 0x8000 (include attribute) flag bits are set, the 0x4000 bit overrides the 0x8000 bit and the contact is excluded.</span></span>



</div>

<span data-ttu-id="6aac8-281">虽然你可以筛选通讯簿以仅包含特定用户, 但限制条目不会限制其他用户联系筛选的用户或查看其状态。</span><span class="sxs-lookup"><span data-stu-id="6aac8-281">Although you can filter the Address Book to include only certain users, limiting entries does not limit other users' ability to contact the filtered users or to see their presence status.</span></span> <span data-ttu-id="6aac8-282">通过输入用户的完整登录名, 用户始终可以查找、手动发送即时消息或手动发起对不在通讯簿中的用户的呼叫。</span><span class="sxs-lookup"><span data-stu-id="6aac8-282">Users can always find, manually send instant messages, or manually initiate calls to users not in the Address Book by entering a user's complete sign-in name.</span></span> <span data-ttu-id="6aac8-283">此外, 还可以在 Outlook 中找到用户的联系人信息。</span><span class="sxs-lookup"><span data-stu-id="6aac8-283">Also, contact information for a user could also be found in Outlook.</span></span>

<span data-ttu-id="6aac8-284">在通讯簿文件中拥有完整的联系人记录后, 你就可以使用 Lync Server 启动电子邮件、电话或企业语音呼叫 (即, 如果在服务器上启用了企业语音), 并且用户没有为会话初始化配置的用户协议 (SIP), 某些组织希望在其通讯簿服务器条目中仅包含启用 SIP 的用户。</span><span class="sxs-lookup"><span data-stu-id="6aac8-284">While having full contact records in the Address Book files enables you to use Lync Server to initiate email, telephone, or Enterprise Voice calls (that is, if Enterprise Voice is enabled on the server) with users that are not configured for Session Initiation Protocol (SIP), some organizations prefer to include only SIP-enabled users in their Address Book Server entries.</span></span> <span data-ttu-id="6aac8-285">你可以通过清除以下必需属性的**Flags**列中的0x800 位来筛选通讯簿以仅包含启用了 SIP 的用户: **mailNickname**、 **telephoneNumber**、 **homePhone**和**mobile**。</span><span class="sxs-lookup"><span data-stu-id="6aac8-285">You can filter the Address Book to include only SIP-enabled users by clearing the 0x800 bit in the **Flags** column of the following required attributes: **mailNickname**, **telephoneNumber**, **homePhone**, and **mobile**.</span></span> <span data-ttu-id="6aac8-286">您还可以通过在**msRTCSIP-PrimaryUserAddress**属性的**Flags**列中设置 0x8000 (include 属性) 来筛选通讯簿以仅包含启用了 SIP 的用户。</span><span class="sxs-lookup"><span data-stu-id="6aac8-286">You can also filter the Address Book to include only SIP-enabled users by setting the 0x8000 (include attribute) in the **Flags** column of the **msRTCSIP-PrimaryUserAddress** attribute.</span></span> <span data-ttu-id="6aac8-287">这还有助于从通讯簿文件中排除服务帐户。</span><span class="sxs-lookup"><span data-stu-id="6aac8-287">This also helps to exclude service accounts from the Address Book files.</span></span>

<span data-ttu-id="6aac8-288">修改 AbAttribute 表后, 您可以通过运行 cmdlet **Update-CsUserDatabase**命令来刷新 AbUserEntry 表中的数据。</span><span class="sxs-lookup"><span data-stu-id="6aac8-288">After you modify the AbAttribute table, you can refresh the data in the AbUserEntry table by running the cmdlet **Update-CsUserDatabase** command.</span></span> <span data-ttu-id="6aac8-289">在 UR 复制完成后, 你可以通过手动运行 cmdlet **UpdateCsAddressBook**命令来更新通讯簿服务器文件存储中的文件。</span><span class="sxs-lookup"><span data-stu-id="6aac8-289">After UR replication completes, you can update the file in the Address Book Server file store by manually running the cmdlet **UpdateCsAddressBook** command.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="6aac8-290">通讯簿服务器所在的前端服务器不能以管理方式进行配置。</span><span class="sxs-lookup"><span data-stu-id="6aac8-290">The Front End Server that the Address Book Server is placed is not administratively configurable.</span></span> <span data-ttu-id="6aac8-291">在部署期间选择一个, 通常是部署的第一台前端服务器。</span><span class="sxs-lookup"><span data-stu-id="6aac8-291">One is chosen during deployment—typically, the first Front End Server deployed.</span></span> <span data-ttu-id="6aac8-292">如果出现故障, 通讯簿服务将移动到另一台前端服务器, 不需要管理员注意。</span><span class="sxs-lookup"><span data-stu-id="6aac8-292">In the event of failure, the Address Book Service will move to another Front End Server, and requires no administrative attention.</span></span>



</div>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="6aac8-293">如果你已从多林部署或父/子部署 (如在移动到 Lync Server 之前合并基础结构) 进行了合并或更改了你的基础结构, 你可能会发现通讯簿服务下载和某些用户的通讯簿 Web 查询失败。</span><span class="sxs-lookup"><span data-stu-id="6aac8-293">If you have consolidated or otherwise modified your infrastructure from a multi-forest deployment or a parent/child deployment (such as consolidating your infrastructure before moving to Lync Server), you may find that the Address Book service download and the Address Book Web Query fails for some users.</span></span> <span data-ttu-id="6aac8-294">在具有多个域或林的部署中, 将在出现问题的用户对象上填充属性<STRONG>MsRTCSIP-OriginatorSid</STRONG> 。</span><span class="sxs-lookup"><span data-stu-id="6aac8-294">When in a deployment that had multiple domains or forests, the attribute <STRONG>MsRTCSIP-OriginatorSid</STRONG> is populated on the user objects that are exhibiting the issue.</span></span> <span data-ttu-id="6aac8-295">要解决此问题, 必须在这些对象上将<STRONG>MsRTCSIP-OriginatorSid</STRONG>属性设置为 NULL。</span><span class="sxs-lookup"><span data-stu-id="6aac8-295">The <STRONG>MsRTCSIP-OriginatorSid</STRONG> attribute must be set to NULL on these objects to resolve the issue.</span></span>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

