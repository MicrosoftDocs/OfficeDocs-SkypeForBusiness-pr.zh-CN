---
title: '在通话质量仪表板中上载租户和构建数据 (CQD) '
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.reviewer: mikedav, siunies, gageames
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection:
- M365-voice
search.appverid: MET150
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Reporting
- seo-marvel-apr2020
description: 了解如何在通话质量仪表板中上载租户和构建数据 (CQD) 。
ms.openlocfilehash: 1ee722e63a8699e1447ffc0c2bc859a6a080d220
ms.sourcegitcommit: bac9aa29074ef32387dc05b3918e87d4c38d195d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2020
ms.locfileid: "49385629"
---
# <a name="upload-tenant-and-building-data-in-call-quality-dashboard-cqd"></a><span data-ttu-id="b9ffe-103">在通话质量仪表板中上载租户和构建数据 (CQD) </span><span class="sxs-lookup"><span data-stu-id="b9ffe-103">Upload tenant and building data in Call Quality Dashboard (CQD)</span></span>


<span data-ttu-id="b9ffe-104">若要充分利用通话质量仪表板 (CQD) ，建议你上载租户并生成数据。</span><span class="sxs-lookup"><span data-stu-id="b9ffe-104">To get the most out of Call Quality Dashboard (CQD), we recommend that you upload your tenant and building data.</span></span> <span data-ttu-id="b9ffe-105">有2种类型的租户数据文件， [生成](#upload-building-data-file) 和 [终结点](#endpoint-data-file)。</span><span class="sxs-lookup"><span data-stu-id="b9ffe-105">There are 2 types of tenant data files, [Building](#upload-building-data-file) and [Endpoint](#endpoint-data-file).</span></span>

<span data-ttu-id="b9ffe-106">你可以 [在此处](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/locations-template.zip?raw=true)下载示例租户数据模板。</span><span class="sxs-lookup"><span data-stu-id="b9ffe-106">You can download a sample tenant data template [here](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/locations-template.zip?raw=true).</span></span> <span data-ttu-id="b9ffe-107">有关生成映射的帮助，请参阅为 [CQD 创建构建地图](CQD-building-mapping.md)。</span><span class="sxs-lookup"><span data-stu-id="b9ffe-107">For help with building mapping, read [Create a building map for CQD](CQD-building-mapping.md).</span></span>

<span data-ttu-id="b9ffe-108">在 "CQD 摘要报告" 仪表板中，从 "CQD **设置**" 菜单中选择 "**租户数据上传**"， (位于 CQD ") 顶部的齿轮图标。</span><span class="sxs-lookup"><span data-stu-id="b9ffe-108">From the CQD Summary Reports dashboard, select **Tenant Data Upload** from the CQD **Settings** menu (a gear icon at the top of CQD).</span></span> <span data-ttu-id="b9ffe-109">在此，管理员可以上载其组织的建筑物和终结点信息，例如 IP 地址和地理信息的映射、映射每个无线访问点及其 MAC 地址等。</span><span class="sxs-lookup"><span data-stu-id="b9ffe-109">From here, admins can upload their organization's building and endpoint information, such as mapping of IP addresses and geographical information, mapping each wireless access point and its MAC address, etc.</span></span>

1. <span data-ttu-id="b9ffe-110">从团队管理中心打开 CQD (，或在) 中 [https://cqd.teams.microsoft.com](https://cqd.teams.microsoft.com) ，选择右上角的齿轮图标，然后从 "**摘要报告**" 页面中选择 "**租户数据上传**"。</span><span class="sxs-lookup"><span data-stu-id="b9ffe-110">Open CQD (from the Teams admin center, or at [https://cqd.teams.microsoft.com](https://cqd.teams.microsoft.com)), then select the gear icon in the upper-right corner and choose **Tenant Data Upload** from the **Summary Reports** page.</span></span>

   ![在上载数据时出现的对话框的屏幕截图](media/qerguide-image-tenantdataupload.png)
    
2. <span data-ttu-id="b9ffe-112">或者，如果你首次访问 CQD，系统将要求你上载数据。</span><span class="sxs-lookup"><span data-stu-id="b9ffe-112">Alternatively, if this is your first time visiting CQD, you'll be asked to upload building data.</span></span> <span data-ttu-id="b9ffe-113">你可以选择 " **立即上载** " 以快速导航到 **租户数据上载** 页面。</span><span class="sxs-lookup"><span data-stu-id="b9ffe-113">You can select **Upload Now** to quickly navigate to the **Tenant Data Upload** page.</span></span>

   ![通知用户上载生成数据的横幅的屏幕截图](media/qerguide-image-buildingdatauploadbanner.png)

3. <span data-ttu-id="b9ffe-115">在 " **租户数据上载** " 页面上，选择 " **浏览** " 以选择数据文件。</span><span class="sxs-lookup"><span data-stu-id="b9ffe-115">On the **Tenant Data Upload** page, select **Browse** to choose a data file.</span></span>

4. <span data-ttu-id="b9ffe-116">选择数据文件后，指定 " **开始日期** "，（可选）指定结束日期。</span><span class="sxs-lookup"><span data-stu-id="b9ffe-116">After selecting a data file, specify **Start date** and, optionally, specify an end date.</span></span>

5. <span data-ttu-id="b9ffe-117">选择 " **开始日期**" 后，选择 " **上传** " 将文件上传到 CQD。</span><span class="sxs-lookup"><span data-stu-id="b9ffe-117">After selecting **Start date**, select **Upload** to upload the file to CQD.</span></span> <br><br><span data-ttu-id="b9ffe-118">在上载文件之前，它将经过验证。</span><span class="sxs-lookup"><span data-stu-id="b9ffe-118">Before the file is uploaded, it's validated.</span></span> <span data-ttu-id="b9ffe-119">如果验证失败，则会显示一条错误消息，要求你更正该文件。</span><span class="sxs-lookup"><span data-stu-id="b9ffe-119">If validation fails, an error message is displayed requesting that you correct the file.</span></span> <span data-ttu-id="b9ffe-120">下图显示了当数据文件中的列数不正确时出现的错误。</span><span class="sxs-lookup"><span data-stu-id="b9ffe-120">The following figure shows an error occurring when the number of columns in the data file is incorrect.</span></span>

   ![显示生成数据上载错误的对话框示例](media/qerguide-image-buildingdatauploaderror.png)
 
6. <span data-ttu-id="b9ffe-122">如果验证期间没有出现错误，文件上载将成功。</span><span class="sxs-lookup"><span data-stu-id="b9ffe-122">If no errors occur during validation, the file upload will succeed.</span></span> <span data-ttu-id="b9ffe-123">然后，你可以在 "我的上 **传** " 表中看到上载的数据文件，其中显示了当前租户在该页面底部的所有上载文件的完整列表。</span><span class="sxs-lookup"><span data-stu-id="b9ffe-123">You can then see the uploaded data file in the **My uploads** table, which shows the full list of all uploaded files for the current tenant at the bottom of that page.</span></span>

> [!NOTE]
> <span data-ttu-id="b9ffe-124">最多可能需要四个小时才能完成处理生成文件。</span><span class="sxs-lookup"><span data-stu-id="b9ffe-124">It can take up to four hours to finish processing the building file.</span></span> <br><br> <span data-ttu-id="b9ffe-125">如果你已经上载了一个生成文件，但需要添加可能已错过或排除的子网，请通过添加新的子网、删除当前文件并重新上载新编辑的文件来修改原始文件。</span><span class="sxs-lookup"><span data-stu-id="b9ffe-125">If you've already uploaded a building file and need to add subnets that might have been missed or excluded, modify the original file by adding the new subnets, remove the current file, and re-upload the newly edited file.</span></span> <span data-ttu-id="b9ffe-126">CQD 中只能有一个活动的构建数据文件。</span><span class="sxs-lookup"><span data-stu-id="b9ffe-126">There can be only one active building data file in CQD.</span></span> 


## <a name="upload-building-data-file"></a><span data-ttu-id="b9ffe-127">上载构建数据文件</span><span class="sxs-lookup"><span data-stu-id="b9ffe-127">Upload building data file</span></span>

<span data-ttu-id="b9ffe-128">CQD 中的第一种类型的租户数据文件是 **生成** 数据文件。</span><span class="sxs-lookup"><span data-stu-id="b9ffe-128">The first type of tenant data file in CQD is the **Building** data file.</span></span> <span data-ttu-id="b9ffe-129">通过展开 "网络 + NetworkRange" 列，然后将 "子网" 列联接到呼叫记录的第一个子网或 "第二个子网" 列中，显示建筑物、城市、国家或地区信息，从而派生出子网列。</span><span class="sxs-lookup"><span data-stu-id="b9ffe-129">The Subnet column is derived by expanding the Network+NetworkRange column, then joining the Subnet column to the call record’s First Subnet or Second Subnet column to show Building, City, Country, or Region information.</span></span> <span data-ttu-id="b9ffe-130">你上载的数据文件的格式必须满足以下条件才能在上载之前通过验证检查：</span><span class="sxs-lookup"><span data-stu-id="b9ffe-130">The format of the data file you upload must meet the following criteria to pass the validation check before upload:</span></span>
  
- <span data-ttu-id="b9ffe-131">文件必须是 tsv 文件 (列由选项卡) 或 .csv 文件分隔， (列之间用) 逗号分隔。</span><span class="sxs-lookup"><span data-stu-id="b9ffe-131">The file must be either a .tsv file (columns are separated by a TAB) or a .csv file (columns are separated by a comma).</span></span>

- <span data-ttu-id="b9ffe-132">数据文件不包含表格标题行。</span><span class="sxs-lookup"><span data-stu-id="b9ffe-132">The data file doesn't include a table header row.</span></span> <span data-ttu-id="b9ffe-133">数据文件的第一行应为真实数据，而不是标题标签（如 "Network"）。</span><span class="sxs-lookup"><span data-stu-id="b9ffe-133">The first line of the data file is expected to be real data, not header labels like "Network".</span></span>

- <span data-ttu-id="b9ffe-134">文件中的数据类型只能是 String、Integer 或 Boolean。</span><span class="sxs-lookup"><span data-stu-id="b9ffe-134">Data types in the file can only be String, Integer, or Boolean.</span></span> <span data-ttu-id="b9ffe-135">对于整数数据类型，值必须是一个数值。</span><span class="sxs-lookup"><span data-stu-id="b9ffe-135">For the  Integer data type, the value must be a numeric value.</span></span> <span data-ttu-id="b9ffe-136">布尔值必须是0或1。</span><span class="sxs-lookup"><span data-stu-id="b9ffe-136">Boolean values must be either 0 or 1.</span></span>

- <span data-ttu-id="b9ffe-137">如果列使用字符串数据类型，则数据字段可以为空，但仍须由制表符或逗号分隔。</span><span class="sxs-lookup"><span data-stu-id="b9ffe-137">If a column uses the String data type, a data field can be empty but must still be separated by a tab or comma.</span></span> <span data-ttu-id="b9ffe-138">空数据字段只是分配一个空字符串值。</span><span class="sxs-lookup"><span data-stu-id="b9ffe-138">An empty data field just assigns an empty String value.</span></span>

- <span data-ttu-id="b9ffe-139">每一行必须有15列，每一列必须具有相应的数据类型，并且列必须按照下表中列出的顺序 (逗号或制表符分隔) ：</span><span class="sxs-lookup"><span data-stu-id="b9ffe-139">There must be 15 columns for each row, each column must have the appropriate data type, and the columns must be in the order listed in the following table (comma or tab delimited):</span></span>

  <span data-ttu-id="b9ffe-140">**构建数据文件格式**</span><span class="sxs-lookup"><span data-stu-id="b9ffe-140">**Building data file format**</span></span>
  
  | <span data-ttu-id="b9ffe-141">列名称</span><span class="sxs-lookup"><span data-stu-id="b9ffe-141">Column name</span></span>        | <span data-ttu-id="b9ffe-142">数据类型</span><span class="sxs-lookup"><span data-stu-id="b9ffe-142">Data type</span></span> | <span data-ttu-id="b9ffe-143">示例</span><span class="sxs-lookup"><span data-stu-id="b9ffe-143">Example</span></span>                   | <span data-ttu-id="b9ffe-144">指引</span><span class="sxs-lookup"><span data-stu-id="b9ffe-144">Guidance</span></span>              |
  |--------------------|-----------|---------------------------|-----------------------|
  | <span data-ttu-id="b9ffe-145">NetworkIP</span><span class="sxs-lookup"><span data-stu-id="b9ffe-145">NetworkIP</span></span>          | <span data-ttu-id="b9ffe-146">String</span><span class="sxs-lookup"><span data-stu-id="b9ffe-146">String</span></span>    | <span data-ttu-id="b9ffe-147">192.168.1.0</span><span class="sxs-lookup"><span data-stu-id="b9ffe-147">192.168.1.0</span></span>               | <span data-ttu-id="b9ffe-148">必需</span><span class="sxs-lookup"><span data-stu-id="b9ffe-148">Required</span></span>              |
  | <span data-ttu-id="b9ffe-149">NetworkName</span><span class="sxs-lookup"><span data-stu-id="b9ffe-149">NetworkName</span></span>        | <span data-ttu-id="b9ffe-150">String</span><span class="sxs-lookup"><span data-stu-id="b9ffe-150">String</span></span>    | <span data-ttu-id="b9ffe-151">美国/西雅图/西雅图-海-1</span><span class="sxs-lookup"><span data-stu-id="b9ffe-151">USA/Seattle/SEATTLE-SEA-1</span></span> | <span data-ttu-id="b9ffe-152">必需<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="b9ffe-152">Required<sup>1</sup></span></span>  |
  | <span data-ttu-id="b9ffe-153">NetworkRange</span><span class="sxs-lookup"><span data-stu-id="b9ffe-153">NetworkRange</span></span>       | <span data-ttu-id="b9ffe-154">数字</span><span class="sxs-lookup"><span data-stu-id="b9ffe-154">Number</span></span>    | <span data-ttu-id="b9ffe-155">个</span><span class="sxs-lookup"><span data-stu-id="b9ffe-155">26</span></span>                        | <span data-ttu-id="b9ffe-156">必需</span><span class="sxs-lookup"><span data-stu-id="b9ffe-156">Required</span></span>              |
  | <span data-ttu-id="b9ffe-157">BuildingName</span><span class="sxs-lookup"><span data-stu-id="b9ffe-157">BuildingName</span></span>       | <span data-ttu-id="b9ffe-158">String</span><span class="sxs-lookup"><span data-stu-id="b9ffe-158">String</span></span>    | <span data-ttu-id="b9ffe-159">西雅图-海-1</span><span class="sxs-lookup"><span data-stu-id="b9ffe-159">SEATTLE-SEA-1</span></span>             | <span data-ttu-id="b9ffe-160">必需<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="b9ffe-160">Required<sup>1</sup></span></span>  |
  | <span data-ttu-id="b9ffe-161">OwnershipType</span><span class="sxs-lookup"><span data-stu-id="b9ffe-161">OwnershipType</span></span>      | <span data-ttu-id="b9ffe-162">String</span><span class="sxs-lookup"><span data-stu-id="b9ffe-162">String</span></span>    | <span data-ttu-id="b9ffe-163">制定</span><span class="sxs-lookup"><span data-stu-id="b9ffe-163">Contoso</span></span>                   | <span data-ttu-id="b9ffe-164">可选</span><span class="sxs-lookup"><span data-stu-id="b9ffe-164">Optional</span></span>              |
  | <span data-ttu-id="b9ffe-165">BuildingType</span><span class="sxs-lookup"><span data-stu-id="b9ffe-165">BuildingType</span></span>       | <span data-ttu-id="b9ffe-166">String</span><span class="sxs-lookup"><span data-stu-id="b9ffe-166">String</span></span>    | <span data-ttu-id="b9ffe-167">终止</span><span class="sxs-lookup"><span data-stu-id="b9ffe-167">IT Termination</span></span>            | <span data-ttu-id="b9ffe-168">可选</span><span class="sxs-lookup"><span data-stu-id="b9ffe-168">Optional</span></span>              |
  | <span data-ttu-id="b9ffe-169">BuildingOfficeType</span><span class="sxs-lookup"><span data-stu-id="b9ffe-169">BuildingOfficeType</span></span> | <span data-ttu-id="b9ffe-170">String</span><span class="sxs-lookup"><span data-stu-id="b9ffe-170">String</span></span>    | <span data-ttu-id="b9ffe-171">技术</span><span class="sxs-lookup"><span data-stu-id="b9ffe-171">Engineering</span></span>               | <span data-ttu-id="b9ffe-172">可选</span><span class="sxs-lookup"><span data-stu-id="b9ffe-172">Optional</span></span>              |
  | <span data-ttu-id="b9ffe-173">城市</span><span class="sxs-lookup"><span data-stu-id="b9ffe-173">City</span></span>               | <span data-ttu-id="b9ffe-174">String</span><span class="sxs-lookup"><span data-stu-id="b9ffe-174">String</span></span>    | <span data-ttu-id="b9ffe-175">西雅图</span><span class="sxs-lookup"><span data-stu-id="b9ffe-175">Seattle</span></span>                   | <span data-ttu-id="b9ffe-176">推荐</span><span class="sxs-lookup"><span data-stu-id="b9ffe-176">Recommended</span></span>           |
  | <span data-ttu-id="b9ffe-177">ZipCode</span><span class="sxs-lookup"><span data-stu-id="b9ffe-177">ZipCode</span></span>            | <span data-ttu-id="b9ffe-178">String</span><span class="sxs-lookup"><span data-stu-id="b9ffe-178">String</span></span>    | <span data-ttu-id="b9ffe-179">98001</span><span class="sxs-lookup"><span data-stu-id="b9ffe-179">98001</span></span>                     | <span data-ttu-id="b9ffe-180">推荐</span><span class="sxs-lookup"><span data-stu-id="b9ffe-180">Recommended</span></span>           |
  | <span data-ttu-id="b9ffe-181">该国</span><span class="sxs-lookup"><span data-stu-id="b9ffe-181">Country</span></span>            | <span data-ttu-id="b9ffe-182">String</span><span class="sxs-lookup"><span data-stu-id="b9ffe-182">String</span></span>    | <span data-ttu-id="b9ffe-183">我们</span><span class="sxs-lookup"><span data-stu-id="b9ffe-183">US</span></span>                        | <span data-ttu-id="b9ffe-184">推荐</span><span class="sxs-lookup"><span data-stu-id="b9ffe-184">Recommended</span></span>           |
  | <span data-ttu-id="b9ffe-185">省/市/自治区</span><span class="sxs-lookup"><span data-stu-id="b9ffe-185">State</span></span>              | <span data-ttu-id="b9ffe-186">String</span><span class="sxs-lookup"><span data-stu-id="b9ffe-186">String</span></span>    | <span data-ttu-id="b9ffe-187">WA</span><span class="sxs-lookup"><span data-stu-id="b9ffe-187">WA</span></span>                        | <span data-ttu-id="b9ffe-188">推荐</span><span class="sxs-lookup"><span data-stu-id="b9ffe-188">Recommended</span></span>           |
  | <span data-ttu-id="b9ffe-189">区域</span><span class="sxs-lookup"><span data-stu-id="b9ffe-189">Region</span></span>             | <span data-ttu-id="b9ffe-190">String</span><span class="sxs-lookup"><span data-stu-id="b9ffe-190">String</span></span>    | <span data-ttu-id="b9ffe-191">MSUS</span><span class="sxs-lookup"><span data-stu-id="b9ffe-191">MSUS</span></span>                      | <span data-ttu-id="b9ffe-192">推荐</span><span class="sxs-lookup"><span data-stu-id="b9ffe-192">Recommended</span></span>           |
  | <span data-ttu-id="b9ffe-193">InsideCorp<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="b9ffe-193">InsideCorp<sup>2</sup></span></span>         | <span data-ttu-id="b9ffe-194">Bool</span><span class="sxs-lookup"><span data-stu-id="b9ffe-194">Bool</span></span>      | <span data-ttu-id="b9ffe-195">1</span><span class="sxs-lookup"><span data-stu-id="b9ffe-195">1</span></span>             | <span data-ttu-id="b9ffe-196">必需</span><span class="sxs-lookup"><span data-stu-id="b9ffe-196">Required</span></span>              |
  | <span data-ttu-id="b9ffe-197">ExpressRoute<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="b9ffe-197">ExpressRoute<sup>3</sup></span></span>       | <span data-ttu-id="b9ffe-198">Bool</span><span class="sxs-lookup"><span data-stu-id="b9ffe-198">Bool</span></span>      | <span data-ttu-id="b9ffe-199">0</span><span class="sxs-lookup"><span data-stu-id="b9ffe-199">0</span></span>             | <span data-ttu-id="b9ffe-200">必需</span><span class="sxs-lookup"><span data-stu-id="b9ffe-200">Required</span></span>              |
  | <span data-ttu-id="b9ffe-201">VPN</span><span class="sxs-lookup"><span data-stu-id="b9ffe-201">VPN</span></span>                | <span data-ttu-id="b9ffe-202">Bool</span><span class="sxs-lookup"><span data-stu-id="b9ffe-202">Bool</span></span>      | <span data-ttu-id="b9ffe-203">0</span><span class="sxs-lookup"><span data-stu-id="b9ffe-203">0</span></span>                         | <span data-ttu-id="b9ffe-204">可选</span><span class="sxs-lookup"><span data-stu-id="b9ffe-204">Optional</span></span>              |

  <span data-ttu-id="b9ffe-205"><sup>1</sup> 虽然 CQD 不是必需的，但模板配置为显示建筑物和网络名称。</span><span class="sxs-lookup"><span data-stu-id="b9ffe-205"><sup>1</sup> While not required by CQD, the templates are configured to display Building and Network name.</span></span>

  <span data-ttu-id="b9ffe-206"><sup>2</sup> 此设置可用于反映子网是否位于企业网络内。</span><span class="sxs-lookup"><span data-stu-id="b9ffe-206"><sup>2</sup> This setting can be used to reflect whether or not the subnet is inside the corporate network.</span></span> <span data-ttu-id="b9ffe-207">你可以自定义其他用途的用法。</span><span class="sxs-lookup"><span data-stu-id="b9ffe-207">You can customize usage for other purposes.</span></span>

  <span data-ttu-id="b9ffe-208"><sup>3</sup> 此设置可用于反映网络是否使用 Azure ExpressRoute。</span><span class="sxs-lookup"><span data-stu-id="b9ffe-208"><sup>3</sup> This setting can be used to reflect whether or not the network uses Azure ExpressRoute.</span></span> <span data-ttu-id="b9ffe-209">你可以自定义其他用途的用法。</span><span class="sxs-lookup"><span data-stu-id="b9ffe-209">You can customize usage for other purposes.</span></span>  

  <span data-ttu-id="b9ffe-210">**示例行：**</span><span class="sxs-lookup"><span data-stu-id="b9ffe-210">**Sample row:**</span></span>

  `192.168.1.0,USA/Seattle/SEATTLE-SEA-1,26,SEATTLE-SEA-1,Contoso,IT Termination,Engineering,Seattle,98001,US,WA,MSUS,1,0,0`

> [!IMPORTANT]
> <span data-ttu-id="b9ffe-211">网络范围可用于表示具有单个路由前缀) 的多个子网的 supernet (组合。</span><span class="sxs-lookup"><span data-stu-id="b9ffe-211">The network range can be used to represent a supernet (combination of several subnets with a single routing prefix).</span></span> <span data-ttu-id="b9ffe-212">将检查所有新的生成上载，查找任何重叠区域。</span><span class="sxs-lookup"><span data-stu-id="b9ffe-212">All new building uploads will be checked for any overlapping ranges.</span></span> <span data-ttu-id="b9ffe-213">如果你以前上载了一个生成文件，则应下载当前文件，然后重新上载它以标识任何重叠，并在再次上载之前修复该问题。</span><span class="sxs-lookup"><span data-stu-id="b9ffe-213">If you have previously uploaded a building file, you should download the current file and re-upload it to identify any overlaps and fix the issue before uploading again.</span></span> <span data-ttu-id="b9ffe-214">以前上载的文件中的任何重叠都可能会导致向报表中的建筑物进行错误的子网映射。</span><span class="sxs-lookup"><span data-stu-id="b9ffe-214">Any overlap in previously uploaded files may result in the wrong mappings of subnets to buildings in the reports.</span></span> <span data-ttu-id="b9ffe-215">某些 VPN 实现不能准确报告子网信息。</span><span class="sxs-lookup"><span data-stu-id="b9ffe-215">Certain VPN implementations do not accurately report the subnet information.</span></span> 
>
> <span data-ttu-id="b9ffe-216">"VPN" 列是可选的，默认值为0。</span><span class="sxs-lookup"><span data-stu-id="b9ffe-216">The VPN column is optional and will default to 0.</span></span> <span data-ttu-id="b9ffe-217">如果 VPN 列的值设置为1，则该行表示的子网将完全展开，以匹配子网内的所有 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="b9ffe-217">If the VPN column’s value is set to 1, the subnet represented by that row will be fully expanded to match all IP addresses within the subnet.</span></span>  <span data-ttu-id="b9ffe-218">请谨慎使用，并且仅针对 VPN 子网，因为完全展开这些子网将对涉及生成数据的查询的查询时间产生负面影响。</span><span class="sxs-lookup"><span data-stu-id="b9ffe-218">Please use this sparingly and only for VPN subnets since fully expanding these subnets will have a negative impact on query times for queries involving building data.</span></span>


### <a name="supernetting"></a><span data-ttu-id="b9ffe-219">Supernetting</span><span class="sxs-lookup"><span data-stu-id="b9ffe-219">Supernetting</span></span>

<span data-ttu-id="b9ffe-220">你可以使用 supernetting （通常称为无类别 Inter-Domain 路由 (CIDR），) 代替定义每个子网。</span><span class="sxs-lookup"><span data-stu-id="b9ffe-220">You can use supernetting, commonly called Classless Inter-Domain Routing (CIDR,) in place of defining each subnet.</span></span> <span data-ttu-id="b9ffe-221">*Supernet* 是共享单个路由前缀的若干子网的组合。</span><span class="sxs-lookup"><span data-stu-id="b9ffe-221">A *supernet* is a combination of several subnets that share a single routing prefix.</span></span> <span data-ttu-id="b9ffe-222">你可以使用 supernetted 地址，而不是为每个子网添加条目。</span><span class="sxs-lookup"><span data-stu-id="b9ffe-222">Instead of adding an entry for each subnet, you can use the supernetted address.</span></span> <span data-ttu-id="b9ffe-223">支持 Supernetting，但我们不建议使用它。</span><span class="sxs-lookup"><span data-stu-id="b9ffe-223">Supernetting is supported, but we don't recommend using it.</span></span>

<span data-ttu-id="b9ffe-224">例如，Contoso 的市场营销大楼由以下子网组成：</span><span class="sxs-lookup"><span data-stu-id="b9ffe-224">For example, Contoso's marketing building is made up of the subnets below:</span></span>

-   <span data-ttu-id="b9ffe-225">10.1.0.0/24-第一层</span><span class="sxs-lookup"><span data-stu-id="b9ffe-225">10.1.0.0/24—first floor</span></span>
-   <span data-ttu-id="b9ffe-226">10.1.1.0/24-第二层</span><span class="sxs-lookup"><span data-stu-id="b9ffe-226">10.1.1.0/24—second floor</span></span>
-   <span data-ttu-id="b9ffe-227">10.1.2.0/24-第三个楼层</span><span class="sxs-lookup"><span data-stu-id="b9ffe-227">10.1.2.0/24—third floor</span></span>
-   <span data-ttu-id="b9ffe-228">10.1.3.0/24-第四个楼层</span><span class="sxs-lookup"><span data-stu-id="b9ffe-228">10.1.3.0/24—fourth floor</span></span>

<span data-ttu-id="b9ffe-229">你可以使用 supernetted 地址（在本例中为 10.1.0.0/22），而不是为每个子网添加条目。</span><span class="sxs-lookup"><span data-stu-id="b9ffe-229">Instead of adding an entry for each subnet, you can use the supernetted address—in this example, 10.1.0.0/22.</span></span>

-   <span data-ttu-id="b9ffe-230">Network = 10.1.0。0</span><span class="sxs-lookup"><span data-stu-id="b9ffe-230">Network = 10.1.0.0</span></span>
-   <span data-ttu-id="b9ffe-231">网络范围 = 22</span><span class="sxs-lookup"><span data-stu-id="b9ffe-231">Network Range = 22</span></span>

<span data-ttu-id="b9ffe-232">在实现 supernetting 之前，需要考虑以下几点：</span><span class="sxs-lookup"><span data-stu-id="b9ffe-232">Here are a few things to consider before you implement supernetting:</span></span>

-   <span data-ttu-id="b9ffe-233">Supernetting 只能在具有8位到28位掩码的子网映射中使用。</span><span class="sxs-lookup"><span data-stu-id="b9ffe-233">Supernetting can only be used in a subnet mapping with 8-bit to 28-bit mask.</span></span>

-   <span data-ttu-id="b9ffe-234">Supernetting 花费的时间更少，但它以减少数据丰富的成本为代价。</span><span class="sxs-lookup"><span data-stu-id="b9ffe-234">Supernetting takes less time up front, but it comes at the cost of reducing the richness of your data.</span></span> <span data-ttu-id="b9ffe-235">假设存在涉及子网10.1.2.0 的质量问题。</span><span class="sxs-lookup"><span data-stu-id="b9ffe-235">Let's say there's a quality problem involving subnet 10.1.2.0.</span></span> <span data-ttu-id="b9ffe-236">如果你已实现 supernetting，则不会知道子网所在位置或 (的网络类型（例如，实验室) ）。</span><span class="sxs-lookup"><span data-stu-id="b9ffe-236">If you implemented supernetting, you won't know where in the building the subnet is located or what type of network it is (for example, a lab).</span></span> <span data-ttu-id="b9ffe-237">如果您已为建筑物和上传的地板位置信息定义了所有子网，您将能够看到这种区别。</span><span class="sxs-lookup"><span data-stu-id="b9ffe-237">If you'd defined all the subnets for a building and uploaded floor location information, you'd be able to see that distinction.</span></span>

-   <span data-ttu-id="b9ffe-238">请务必确保 supernetted 地址正确，并且不会捕获不需要的子网。</span><span class="sxs-lookup"><span data-stu-id="b9ffe-238">It's important to ensure that the supernetted address is correct and isn't catching unwanted subnets.</span></span>

-   <span data-ttu-id="b9ffe-239">在数据中查找192.168.0.0 非常常见。</span><span class="sxs-lookup"><span data-stu-id="b9ffe-239">It's quite common to find 192.168.0.0 in data.</span></span> <span data-ttu-id="b9ffe-240">对于许多组织，这表示用户在家中。</span><span class="sxs-lookup"><span data-stu-id="b9ffe-240">For many organizations, this indicates that the user is at home.</span></span> <span data-ttu-id="b9ffe-241">对于其他人，这是卫星办公室的 IP 地址方案。</span><span class="sxs-lookup"><span data-stu-id="b9ffe-241">For others, this is the IP address scheme for a satellite office.</span></span> <span data-ttu-id="b9ffe-242">如果你的组织具有使用此配置的办事处，则不要将其包含在你的构建文件中，因为很难通过使用 [公共子网](quality-of-experience-review-guide.md#common-subnets)来区分家庭网络和内部网络。</span><span class="sxs-lookup"><span data-stu-id="b9ffe-242">If your organization does have offices that use this configuration, don't include it in your building file because it's difficult to distinguish between home and internal networks by using [common subnets](quality-of-experience-review-guide.md#common-subnets).</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="b9ffe-243">网络范围可用于表示 supernet。</span><span class="sxs-lookup"><span data-stu-id="b9ffe-243">The network range can be used to represent a supernet.</span></span> <span data-ttu-id="b9ffe-244">将检查所有新生成数据文件上是否有任何重叠区域。</span><span class="sxs-lookup"><span data-stu-id="b9ffe-244">All new building data file uploads will be checked for any overlapping ranges.</span></span> <span data-ttu-id="b9ffe-245">如果你以前上载了一个生成文件，你应该下载当前文件并再次上载它以识别任何重叠并解决问题。</span><span class="sxs-lookup"><span data-stu-id="b9ffe-245">If you've previously uploaded a building file, you should download the current file and upload it again to identify any overlaps and fix the issue.</span></span> <span data-ttu-id="b9ffe-246">以前上载的文件中的任何重叠都可能会导致向报表中的建筑物进行错误的子网映射。</span><span class="sxs-lookup"><span data-stu-id="b9ffe-246">Any overlap in previously uploaded files might result in the wrong mappings of subnets to buildings in the reports.</span></span>

### <a name="vpn"></a><span data-ttu-id="b9ffe-247">VPN</span><span class="sxs-lookup"><span data-stu-id="b9ffe-247">VPN</span></span>

<span data-ttu-id="b9ffe-248"> (QoE) 客户端发送到 Microsoft 365 或 Office 365 （CQD 数据来源）的体验的质量，包括 VPN 标志。</span><span class="sxs-lookup"><span data-stu-id="b9ffe-248">The quality of experience (QoE) data that clients send to Microsoft 365 or Office 365—which is where CQD data is sourced from—includes a VPN flag.</span></span> <span data-ttu-id="b9ffe-249">CQD 将看到这是第一个 VPN 和第二个 VPN 维度。</span><span class="sxs-lookup"><span data-stu-id="b9ffe-249">CQD will see this as the First VPN and Second VPN dimensions.</span></span> <span data-ttu-id="b9ffe-250">但是，此标志依赖于 VPN 供应商向 Windows 报告，VPN 网络适配器已注册为远程访问适配器。</span><span class="sxs-lookup"><span data-stu-id="b9ffe-250">However, this flag relies on VPN vendors' reporting to Windows that the VPN network adapter registered is a Remote Access adapter.</span></span> <span data-ttu-id="b9ffe-251">并非所有 VPN 供应商都正确注册远程访问适配器。</span><span class="sxs-lookup"><span data-stu-id="b9ffe-251">Not all VPN vendors properly register Remote Access adapters.</span></span> <span data-ttu-id="b9ffe-252">因此，你可能无法使用内置的 VPN 查询筛选器。</span><span class="sxs-lookup"><span data-stu-id="b9ffe-252">Because of this, you might not be able to use the built-in VPN query filters.</span></span> <span data-ttu-id="b9ffe-253">使用上面所述的 VPN 列准确标记和标识 VPN 子网。</span><span class="sxs-lookup"><span data-stu-id="b9ffe-253">Use the VPN column discussed above to accurately mark and identify VPN subnets.</span></span> <span data-ttu-id="b9ffe-254">将 VPN 网络标记为易于在报表中进行标识也是一种好做法。</span><span class="sxs-lookup"><span data-stu-id="b9ffe-254">It is also good practice to label your VPN networks for easy identification in your reports.</span></span> <span data-ttu-id="b9ffe-255">下面是两个有关如何标记 VPN 子网的示例：</span><span class="sxs-lookup"><span data-stu-id="b9ffe-255">Below are two examples of how to label your VPN subnets:</span></span>

- <span data-ttu-id="b9ffe-256">通过在此字段中输入 VPN 子网的 "VPN" 来定义 **网络名称** 。</span><span class="sxs-lookup"><span data-stu-id="b9ffe-256">Define a **Network Name** by entering "VPN" in this field for VPN subnets.</span></span>

  ![使用网络名称显示 VPN 的 QCD 报告屏幕截图](media/qerguide-image-vpnnetworkname.png)

- <span data-ttu-id="b9ffe-258">通过在此字段中输入 VPN 子网的 "VPN" 来定义 **建筑物名称** 。</span><span class="sxs-lookup"><span data-stu-id="b9ffe-258">Define a **Building Name** by entering "VPN" in this field for VPN subnets.</span></span>

  ![显示使用建筑物名称的 VPN 的 QCD 报告屏幕截图](media/qerguide-image-vpnbuildingname.png)

> [!NOTE]
> <span data-ttu-id="b9ffe-260">在基础连接为无线连接时，misidentify 的 VPN 连接将网络连接类型作为有线。</span><span class="sxs-lookup"><span data-stu-id="b9ffe-260">VPN connections have been known to misidentify the network connection type as wired when the underlying connection is wireless.</span></span> <span data-ttu-id="b9ffe-261">在通过 VPN 连接查看高质量时，无法假定已准确识别连接类型。</span><span class="sxs-lookup"><span data-stu-id="b9ffe-261">When looking at quality over VPN connections, you can't assume that the connection type has been accurately identified.</span></span>

## <a name="endpoint-data-file"></a><span data-ttu-id="b9ffe-262">终结点数据文件</span><span class="sxs-lookup"><span data-stu-id="b9ffe-262">Endpoint data file</span></span>

<span data-ttu-id="b9ffe-263">另一种类型的 CQD 租户数据文件是 **终结点** 数据文件。</span><span class="sxs-lookup"><span data-stu-id="b9ffe-263">The other type of CQD tenant data file is the **Endpoint** data file.</span></span> <span data-ttu-id="b9ffe-264">在调用记录的第一个客户端终结点名称列或第二个客户端终结点名称列中使用列值来显示终结点的 "创建"、"模型" 或 "类型" 信息。</span><span class="sxs-lookup"><span data-stu-id="b9ffe-264">The column values are used in the call record’s First Client Endpoint Name or Second Client Endpoint Name column to show Endpoint Make, Model, or Type information.</span></span> <span data-ttu-id="b9ffe-265">你上载的数据文件的格式必须满足以下条件才能在上载之前通过验证检查：</span><span class="sxs-lookup"><span data-stu-id="b9ffe-265">The format of the data file you upload must meet the following criteria to pass the validation check before upload:</span></span>

- <span data-ttu-id="b9ffe-266">文件必须是 tsv 文件 (列由选项卡) 或 .csv 文件分隔， (列之间用) 逗号分隔。</span><span class="sxs-lookup"><span data-stu-id="b9ffe-266">The file must be either a .tsv file (columns are separated by a TAB) or a .csv file (columns are separated by a comma).</span></span>

- <span data-ttu-id="b9ffe-267">数据文件的内容不包含表格标题。</span><span class="sxs-lookup"><span data-stu-id="b9ffe-267">The content of the data file doesn't include table headers.</span></span> <span data-ttu-id="b9ffe-268">数据文件的第一行应为真实数据，而不是标题标签（如 "终结点"）。</span><span class="sxs-lookup"><span data-stu-id="b9ffe-268">The first line of the data file is expected to be real data, not a header label like "EndpointName".</span></span>

- <span data-ttu-id="b9ffe-269">所有七列仅使用字符串数据类型。</span><span class="sxs-lookup"><span data-stu-id="b9ffe-269">All seven columns use the String data type only.</span></span> <span data-ttu-id="b9ffe-270">允许的最大长度为64个字符。</span><span class="sxs-lookup"><span data-stu-id="b9ffe-270">The maximum allowed length is 64 characters.</span></span>

- <span data-ttu-id="b9ffe-271">数据字段可以为空，但仍须由制表符或逗号分隔。</span><span class="sxs-lookup"><span data-stu-id="b9ffe-271">A data field can be empty but must still be separated by a tab or comma.</span></span> <span data-ttu-id="b9ffe-272">空数据字段只是分配一个空字符串值。</span><span class="sxs-lookup"><span data-stu-id="b9ffe-272">An empty data field just assigns an empty String value.</span></span>

- <span data-ttu-id="b9ffe-273">终结点必须是唯一的，否则上传将失败。</span><span class="sxs-lookup"><span data-stu-id="b9ffe-273">EndpointName must be unique, otherwise the upload fails.</span></span> <span data-ttu-id="b9ffe-274">如果存在重复的行或两行使用同一终结点，则冲突将导致不正确的联接。</span><span class="sxs-lookup"><span data-stu-id="b9ffe-274">If there is a duplicate row or two rows that use the same EndpointName the conflict will  cause incorrect joining.</span></span>

- <span data-ttu-id="b9ffe-275">EndpointLabel1、EndpointLabel2 和 EndpointLabel3 是可自定义的标签。</span><span class="sxs-lookup"><span data-stu-id="b9ffe-275">EndpointLabel1, EndpointLabel2, and EndpointLabel3 are customizable labels.</span></span> <span data-ttu-id="b9ffe-276">它们可以是空字符串或值，如 "IT 部门指定的2018膝上型计算机" 或 "资产标签 5678"。</span><span class="sxs-lookup"><span data-stu-id="b9ffe-276">They can be empty Strings or values such as “IT Department designated 2018 Laptop” or “Asset Tag 5678”.</span></span>

- <span data-ttu-id="b9ffe-277">每行必须有七列，并且列必须按以下顺序排列：</span><span class="sxs-lookup"><span data-stu-id="b9ffe-277">There must be seven columns for each row and the columns must be in the following order:</span></span>

  <span data-ttu-id="b9ffe-278">**字段顺序：**</span><span class="sxs-lookup"><span data-stu-id="b9ffe-278">**Field order:**</span></span>

  <span data-ttu-id="b9ffe-279">终结点、EndpointMake、EndpointModel、EndpointType、EndpointLabel1、EndpointLabel2、EndpointLabel3</span><span class="sxs-lookup"><span data-stu-id="b9ffe-279">EndpointName, EndpointMake, EndpointModel, EndpointType, EndpointLabel1, EndpointLabel2,  EndpointLabel3</span></span>

  <span data-ttu-id="b9ffe-280">**示例行：**</span><span class="sxs-lookup"><span data-stu-id="b9ffe-280">**Sample row:**</span></span>

  `1409W3534, Fabrikam, Model 123, Laptop, IT designated 2018 Laptop, Asset Tag 5678, Purchase 2018`


## <a name="update-a-building-file"></a><span data-ttu-id="b9ffe-281">更新生成文件</span><span class="sxs-lookup"><span data-stu-id="b9ffe-281">Update a building file</span></span>

<span data-ttu-id="b9ffe-282">在收集生成和子网信息时，管理员通常会在一段时间内将生成文件上载到多个迭代中，并在新子网可用时添加新的子网和生成信息。</span><span class="sxs-lookup"><span data-stu-id="b9ffe-282">While gathering building and subnet information, administrators will often upload the building file in multiple iterations over time, adding new subnets and their building information as it becomes available.</span></span> <span data-ttu-id="b9ffe-283">出现这种情况时，你需要重新上载你的构建文件。</span><span class="sxs-lookup"><span data-stu-id="b9ffe-283">When this occurs, you'll need to re-upload your building file.</span></span> <span data-ttu-id="b9ffe-284">此过程类似于上一节中所述的初始上载，还有一些例外，如下部分所述。</span><span class="sxs-lookup"><span data-stu-id="b9ffe-284">This process is like the initial upload as described in the previous section, with a few exceptions as noted in the following section.</span></span>

> [!Important]
> <span data-ttu-id="b9ffe-285">一次只能有一个生成文件处于活动状态。</span><span class="sxs-lookup"><span data-stu-id="b9ffe-285">Only one building file can be active at a time.</span></span> <span data-ttu-id="b9ffe-286">多个生成文件不具有累积性。</span><span class="sxs-lookup"><span data-stu-id="b9ffe-286">Multiple building files aren't cumulative.</span></span>

## <a name="add-net-new-subnets"></a><span data-ttu-id="b9ffe-287">添加全新的子网</span><span class="sxs-lookup"><span data-stu-id="b9ffe-287">Add net new subnets</span></span>

<span data-ttu-id="b9ffe-288">有时，你需要将新的子网添加到 CQD 中的子网，而不是你的网络拓扑的一部分。</span><span class="sxs-lookup"><span data-stu-id="b9ffe-288">There are times when you'll need to add net new subnets to CQD that weren't originally part of your network topology.</span></span> <span data-ttu-id="b9ffe-289">若要添加全新的子网，请在 CQD 中的 **租户数据上传** 页面执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="b9ffe-289">To add net new subnets, do the following from the **Tenant Data Upload** page in CQD:</span></span>

1.  <span data-ttu-id="b9ffe-290">如果尚未有最新的副本，请下载原始文件。</span><span class="sxs-lookup"><span data-stu-id="b9ffe-290">Download the original file, if you don't already have an up-to-date copy.</span></span>

1.  <span data-ttu-id="b9ffe-291">删除 CQD 中的当前文件。</span><span class="sxs-lookup"><span data-stu-id="b9ffe-291">Remove the current file in CQD.</span></span>

1.  <span data-ttu-id="b9ffe-292">编辑原始构建文件，并提供在获取网络新子网之前至少一天出现的结束日期。</span><span class="sxs-lookup"><span data-stu-id="b9ffe-292">Edit the original building file and provide an end date that occurs at least one day before the net new subnets were acquired.</span></span>

1.  <span data-ttu-id="b9ffe-293">将新的全新子网附加到原始生成文件。</span><span class="sxs-lookup"><span data-stu-id="b9ffe-293">Append the net new subnets to the original building file.</span></span>

1.  <span data-ttu-id="b9ffe-294">上载新修改的生成文件，并将开始日期设置为上一个生成文件结束后的一天。</span><span class="sxs-lookup"><span data-stu-id="b9ffe-294">Upload the newly modified building file, and set the start date for one day after the previous building file ends.</span></span>

## <a name="add-missing-subnets"></a><span data-ttu-id="b9ffe-295">添加缺少的子网</span><span class="sxs-lookup"><span data-stu-id="b9ffe-295">Add missing subnets</span></span>

<span data-ttu-id="b9ffe-296">在上载托管网络的生成信息后，每个托管网络都应具有一个建筑物关联。</span><span class="sxs-lookup"><span data-stu-id="b9ffe-296">After you upload building information for managed networks, every managed network should have a building association.</span></span> <span data-ttu-id="b9ffe-297">但是，这并不总是这样。通常，缺少几个子网。</span><span class="sxs-lookup"><span data-stu-id="b9ffe-297">However, this won't always be the case; typically, a few subnets are missed.</span></span> <span data-ttu-id="b9ffe-298">若要查找这些缺少的网络，请查看 CQD 中的 "**体验质量报告**" 页面上 **缺少的子网报告**。</span><span class="sxs-lookup"><span data-stu-id="b9ffe-298">To find these missing networks, review the **Missing Subnet Report** on the **Quality of Experience Reports** page in CQD.</span></span> <span data-ttu-id="b9ffe-299">这将显示包含10个或更多音频流的所有子网，这些流在建筑物数据文件中未定义且标记为外部。</span><span class="sxs-lookup"><span data-stu-id="b9ffe-299">This presents all the subnets with 10 or more audio streams that aren't defined in the building data file and are being marked as outside.</span></span> <span data-ttu-id="b9ffe-300">确保此列表中没有托管网络。</span><span class="sxs-lookup"><span data-stu-id="b9ffe-300">Ensure that there are no managed networks in this list.</span></span> <span data-ttu-id="b9ffe-301">如果缺少子网，请使用以下过程更新原始生成数据文件，并将其重新上载到 CQD。</span><span class="sxs-lookup"><span data-stu-id="b9ffe-301">If subnets are missing, use the following procedure to update the original building data file and re-upload it to CQD.</span></span>

1. <span data-ttu-id="b9ffe-302">转到 CQD 中的 **租户数据上传** 页面。</span><span class="sxs-lookup"><span data-stu-id="b9ffe-302">Go to the **Tenant Data Upload** page in CQD.</span></span>

1. <span data-ttu-id="b9ffe-303">如果尚未有最新的副本，请下载原始文件。</span><span class="sxs-lookup"><span data-stu-id="b9ffe-303">Download the original file, if you don't already have an up-to-date copy.</span></span>

1. <span data-ttu-id="b9ffe-304">删除 CQD 中的当前文件。</span><span class="sxs-lookup"><span data-stu-id="b9ffe-304">Remove the current file in CQD.</span></span>

1. <span data-ttu-id="b9ffe-305">将新子网追加到原始文件。</span><span class="sxs-lookup"><span data-stu-id="b9ffe-305">Append the new subnets to the original file.</span></span>

1. <span data-ttu-id="b9ffe-306">上载构建文件。</span><span class="sxs-lookup"><span data-stu-id="b9ffe-306">Upload the building file.</span></span> <span data-ttu-id="b9ffe-307">请务必先将开始日期设置为至少八个月，这样 CQD 将处理历史记录数据。</span><span class="sxs-lookup"><span data-stu-id="b9ffe-307">Be sure to set the start date to at least eight months prior so that CQD will process historical data.</span></span>


> [!IMPORTANT]
> <span data-ttu-id="b9ffe-308">你需要将租户 ID 作为 **第二租户 id** 的查询筛选器添加到此报表，以筛选报表以仅查看你的组织的租户数据。</span><span class="sxs-lookup"><span data-stu-id="b9ffe-308">You'll need to add your tenant ID as a query filter for **Second Tenant ID** to this report to filter the report to view only your organization's tenant data.</span></span> <span data-ttu-id="b9ffe-309">否则，报表将显示联合子网。</span><span class="sxs-lookup"><span data-stu-id="b9ffe-309">Otherwise, the report will show federated subnets.</span></span>

> [!NOTE] 
> <span data-ttu-id="b9ffe-310">请确保将 "月" 报表筛选器调整为当前月份。</span><span class="sxs-lookup"><span data-stu-id="b9ffe-310">Be sure to adjust the Month Year report filter to the current month.</span></span> <span data-ttu-id="b9ffe-311">选择 " **编辑**"，然后调整 " **月** " 报表筛选器以保存新的默认月份。</span><span class="sxs-lookup"><span data-stu-id="b9ffe-311">Select **Edit**, and adjust the **Month Year** report filter to save the new default month.</span></span>


## <a name="related-topics"></a><span data-ttu-id="b9ffe-312">相关主题</span><span class="sxs-lookup"><span data-stu-id="b9ffe-312">Related topics</span></span>

[<span data-ttu-id="b9ffe-313">为 CQD 创建建筑地图</span><span class="sxs-lookup"><span data-stu-id="b9ffe-313">Create a building map for CQD</span></span>](CQD-building-mapping.md)

[<span data-ttu-id="b9ffe-314">改善和监控团队的通话质量</span><span class="sxs-lookup"><span data-stu-id="b9ffe-314">Improve and monitor call quality for Teams</span></span>](monitor-call-quality-qos.md)

[<span data-ttu-id="b9ffe-315">什么是 CQD？</span><span class="sxs-lookup"><span data-stu-id="b9ffe-315">What is CQD?</span></span>](CQD-what-is-call-quality-dashboard.md)

[<span data-ttu-id="b9ffe-316">设置通话质量仪表板 (CQD) </span><span class="sxs-lookup"><span data-stu-id="b9ffe-316">Set up Call Quality Dashboard (CQD)</span></span>](turning-on-and-using-call-quality-dashboard.md)

[<span data-ttu-id="b9ffe-317">CQD 数据和报告</span><span class="sxs-lookup"><span data-stu-id="b9ffe-317">CQD data and reports</span></span>](CQD-data-and-reports.md)

[<span data-ttu-id="b9ffe-318">使用 CQD 管理通话和会议质量</span><span class="sxs-lookup"><span data-stu-id="b9ffe-318">Use CQD to manage call and meeting quality</span></span>](quality-of-experience-review-guide.md)

[<span data-ttu-id="b9ffe-319">CQD 中可用的维度和度量值</span><span class="sxs-lookup"><span data-stu-id="b9ffe-319">Dimensions and measures available in CQD</span></span>](dimensions-and-measures-available-in-call-quality-dashboard.md)

[<span data-ttu-id="b9ffe-320">CQD 中的流分类</span><span class="sxs-lookup"><span data-stu-id="b9ffe-320">Stream Classification in CQD</span></span>](stream-classification-in-call-quality-dashboard.md)

[<span data-ttu-id="b9ffe-321">使用 Power BI 分析 CQD 数据</span><span class="sxs-lookup"><span data-stu-id="b9ffe-321">Use Power BI to analyze CQD data</span></span>](CQD-Power-BI-query-templates.md)
