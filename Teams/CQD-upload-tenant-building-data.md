---
title: 'Upload CQD 服务中的呼叫质量仪表板 (租户和) '
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
description: 了解如何在 CQD 仪表板的呼叫质量仪表板 (租户和) 。
ms.openlocfilehash: 7a1f6de78e01a8988317aa99aae917aa0018e19a
ms.sourcegitcommit: 7e673b88346e07f7c777710437b19d257ccecb1b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/01/2021
ms.locfileid: "50067137"
---
# <a name="upload-tenant-and-building-data-in-call-quality-dashboard-cqd"></a><span data-ttu-id="a6e70-103">Upload CQD 服务中的呼叫质量仪表板 (租户和) </span><span class="sxs-lookup"><span data-stu-id="a6e70-103">Upload tenant and building data in Call Quality Dashboard (CQD)</span></span>


<span data-ttu-id="a6e70-104">若要在 CQD 仪表板中 (呼叫质量) ，建议上传租户和建筑物数据。</span><span class="sxs-lookup"><span data-stu-id="a6e70-104">To get the most out of Call Quality Dashboard (CQD), we recommend that you upload your tenant and building data.</span></span> <span data-ttu-id="a6e70-105">有 2 种类型的租户数据文件，[即"生成"和"](#upload-building-data-file)[终结点"。](#endpoint-data-file)</span><span class="sxs-lookup"><span data-stu-id="a6e70-105">There are 2 types of tenant data files, [Building](#upload-building-data-file) and [Endpoint](#endpoint-data-file).</span></span>

<span data-ttu-id="a6e70-106">可以在此处下载示例租户数据 [模板](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/locations-template.zip?raw=true)。</span><span class="sxs-lookup"><span data-stu-id="a6e70-106">You can download a sample tenant data template [here](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/locations-template.zip?raw=true).</span></span> <span data-ttu-id="a6e70-107">有关建筑物映射的帮助，请阅读 [为 CQD 创建建筑地图](CQD-building-mapping.md)。</span><span class="sxs-lookup"><span data-stu-id="a6e70-107">For help with building mapping, read [Create a building map for CQD](CQD-building-mapping.md).</span></span>

<span data-ttu-id="a6e70-108">在"CQD 摘要报表"仪表板中，从 CQD 设置 菜单中选择"租户数据Upload"， (CQD 报表顶部的齿轮图标) 。</span><span class="sxs-lookup"><span data-stu-id="a6e70-108">From the CQD Summary Reports dashboard, select **Tenant Data Upload** from the CQD **Settings** menu (a gear icon at the top of CQD).</span></span> <span data-ttu-id="a6e70-109">在这里，管理员可以上传其组织的建筑物和终结点信息，例如 IP 地址和地理信息映射、映射每个无线接入点及其 MAC 地址，等等。</span><span class="sxs-lookup"><span data-stu-id="a6e70-109">From here, admins can upload their organization's building and endpoint information, such as mapping of IP addresses and geographical information, mapping each wireless access point and its MAC address, etc.</span></span>

1. <span data-ttu-id="a6e70-110">从 Teams 管理中心或) 打开 CQD (，然后选择右上角的齿轮图标，然后从"摘要报表"页中选择"租户数据 Upload"。 [https://cqd.teams.microsoft.com](https://cqd.teams.microsoft.com)  </span><span class="sxs-lookup"><span data-stu-id="a6e70-110">Open CQD (from the Teams admin center, or at [https://cqd.teams.microsoft.com](https://cqd.teams.microsoft.com)), then select the gear icon in the upper-right corner and choose **Tenant Data Upload** from the **Summary Reports** page.</span></span>

   ![上传数据时出现的对话框的屏幕截图](media/qerguide-image-tenantdataupload.png)
    
2. <span data-ttu-id="a6e70-112">或者，如果这是您第一次访问 CQD，将要求您上传建筑物数据。</span><span class="sxs-lookup"><span data-stu-id="a6e70-112">Alternatively, if this is your first time visiting CQD, you'll be asked to upload building data.</span></span> <span data-ttu-id="a6e70-113">可以选择 **"Upload"** 以快速导航到"租户数据 **Upload页。**</span><span class="sxs-lookup"><span data-stu-id="a6e70-113">You can select **Upload Now** to quickly navigate to the **Tenant Data Upload** page.</span></span>

   ![通知用户上传建筑物数据的横幅屏幕截图](media/qerguide-image-buildingdatauploadbanner.png)

3. <span data-ttu-id="a6e70-115">在"**租户数据Upload** 页上，选择 **"浏览**"以选择数据文件。</span><span class="sxs-lookup"><span data-stu-id="a6e70-115">On the **Tenant Data Upload** page, select **Browse** to choose a data file.</span></span>

4. <span data-ttu-id="a6e70-116">选择数据文件后 **，指定开始日期** ，并选择性地指定结束日期。</span><span class="sxs-lookup"><span data-stu-id="a6e70-116">After selecting a data file, specify **Start date** and, optionally, specify an end date.</span></span>

5. <span data-ttu-id="a6e70-117">选择"**开始日期"** 后 **，Upload** 文件上传到 CQD。</span><span class="sxs-lookup"><span data-stu-id="a6e70-117">After selecting **Start date**, select **Upload** to upload the file to CQD.</span></span> <br><br><span data-ttu-id="a6e70-118">在上传文件之前，会验证该文件。</span><span class="sxs-lookup"><span data-stu-id="a6e70-118">Before the file is uploaded, it's validated.</span></span> <span data-ttu-id="a6e70-119">如果验证失败，则会显示一条错误消息，要求更正文件。</span><span class="sxs-lookup"><span data-stu-id="a6e70-119">If validation fails, an error message is displayed requesting that you correct the file.</span></span> <span data-ttu-id="a6e70-120">下图显示了当数据文件中的列数不正确时发生的错误。</span><span class="sxs-lookup"><span data-stu-id="a6e70-120">The following figure shows an error occurring when the number of columns in the data file is incorrect.</span></span>

   ![显示建筑物数据上传错误的对话框示例](media/qerguide-image-buildingdatauploaderror.png)
 
6. <span data-ttu-id="a6e70-122">如果在验证期间未发生错误，文件上传会成功。</span><span class="sxs-lookup"><span data-stu-id="a6e70-122">If no errors occur during validation, the file upload will succeed.</span></span> <span data-ttu-id="a6e70-123">然后，可以在"我的上传"表中查看上传的数据文件，其中显示页面底部的当前租户的所有已上传文件的完整列表。</span><span class="sxs-lookup"><span data-stu-id="a6e70-123">You can then see the uploaded data file in the **My uploads** table, which shows the full list of all uploaded files for the current tenant at the bottom of that page.</span></span>

> [!NOTE]
> <span data-ttu-id="a6e70-124">可能需要 4 小时才能完成建筑物文件的处理。</span><span class="sxs-lookup"><span data-stu-id="a6e70-124">It can take up to four hours to finish processing the building file.</span></span> <br><br> <span data-ttu-id="a6e70-125">如果已上传建筑物文件，并且需要添加可能错过或排除的子网，请通过添加新子网来修改原始文件，删除当前文件，然后重新上传新编辑的文件。</span><span class="sxs-lookup"><span data-stu-id="a6e70-125">If you've already uploaded a building file and need to add subnets that might have been missed or excluded, modify the original file by adding the new subnets, remove the current file, and re-upload the newly edited file.</span></span> <span data-ttu-id="a6e70-126">CQD 中只能有一个活动的建筑物数据文件。</span><span class="sxs-lookup"><span data-stu-id="a6e70-126">There can be only one active building data file in CQD.</span></span> 


## <a name="upload-building-data-file"></a><span data-ttu-id="a6e70-127">Upload生成数据文件</span><span class="sxs-lookup"><span data-stu-id="a6e70-127">Upload building data file</span></span>

<span data-ttu-id="a6e70-128">CQD 中第一种类型的租户数据文件是 **建筑物** 数据文件。</span><span class="sxs-lookup"><span data-stu-id="a6e70-128">The first type of tenant data file in CQD is the **Building** data file.</span></span> <span data-ttu-id="a6e70-129">通过展开"Network+NetworkRange"列，然后将"子网"列联接到呼叫记录的"第一个子网"或"第二个子网"列以显示"建筑物、城市、国家/地区"或"区域"信息，派生子网列。</span><span class="sxs-lookup"><span data-stu-id="a6e70-129">The Subnet column is derived by expanding the Network+NetworkRange column, then joining the Subnet column to the call record’s First Subnet or Second Subnet column to show Building, City, Country, or Region information.</span></span> <span data-ttu-id="a6e70-130">上传的数据文件的格式必须满足以下条件，才能在上传前通过验证检查：</span><span class="sxs-lookup"><span data-stu-id="a6e70-130">The format of the data file you upload must meet the following criteria to pass the validation check before upload:</span></span>
  
- <span data-ttu-id="a6e70-131">该文件必须是 .tsv 文件 (制表符分隔) 或 .csv 文件 (以逗号分隔) 。</span><span class="sxs-lookup"><span data-stu-id="a6e70-131">The file must be either a .tsv file (columns are separated by a TAB) or a .csv file (columns are separated by a comma).</span></span>

- <span data-ttu-id="a6e70-132">数据文件不包括表标题行。</span><span class="sxs-lookup"><span data-stu-id="a6e70-132">The data file doesn't include a table header row.</span></span> <span data-ttu-id="a6e70-133">数据文件的第一行应该是实际数据，而不是标头标签（如"网络"）。</span><span class="sxs-lookup"><span data-stu-id="a6e70-133">The first line of the data file is expected to be real data, not header labels like "Network".</span></span>

- <span data-ttu-id="a6e70-134">该文件中的数据类型只能是字符串、整数或布尔值。</span><span class="sxs-lookup"><span data-stu-id="a6e70-134">Data types in the file can only be String, Integer, or Boolean.</span></span> <span data-ttu-id="a6e70-135">对于整数数据类型，该值必须是数值。</span><span class="sxs-lookup"><span data-stu-id="a6e70-135">For the  Integer data type, the value must be a numeric value.</span></span> <span data-ttu-id="a6e70-136">布尔值必须为 0 或 1。</span><span class="sxs-lookup"><span data-stu-id="a6e70-136">Boolean values must be either 0 or 1.</span></span>

- <span data-ttu-id="a6e70-137">如果列使用字符串数据类型，则数据字段可以为空，但仍必须以制表符或逗号分隔。</span><span class="sxs-lookup"><span data-stu-id="a6e70-137">If a column uses the String data type, a data field can be empty but must still be separated by a tab or comma.</span></span> <span data-ttu-id="a6e70-138">空数据字段只分配一个空的字符串值。</span><span class="sxs-lookup"><span data-stu-id="a6e70-138">An empty data field just assigns an empty String value.</span></span>

- <span data-ttu-id="a6e70-139">每个租户数据文件有 1，000，000 个扩展行限制。</span><span class="sxs-lookup"><span data-stu-id="a6e70-139">There is a 1,000,000 expanded row limit per tenant data file.</span></span>

- <span data-ttu-id="a6e70-140">每行必须包含 15 列，每一列必须具有相应的 数据类型，列必须按照下表中列出的顺序（逗号或制表符 (分隔) ：</span><span class="sxs-lookup"><span data-stu-id="a6e70-140">There must be 15 columns for each row, each column must have the appropriate data type, and the columns must be in the order listed in the following table (comma or tab delimited):</span></span>

  <span data-ttu-id="a6e70-141">**构建数据文件格式**</span><span class="sxs-lookup"><span data-stu-id="a6e70-141">**Building data file format**</span></span>
  
  | <span data-ttu-id="a6e70-142">列名称</span><span class="sxs-lookup"><span data-stu-id="a6e70-142">Column name</span></span>        | <span data-ttu-id="a6e70-143">数据类型</span><span class="sxs-lookup"><span data-stu-id="a6e70-143">Data type</span></span> | <span data-ttu-id="a6e70-144">示例</span><span class="sxs-lookup"><span data-stu-id="a6e70-144">Example</span></span>                   | <span data-ttu-id="a6e70-145">指引</span><span class="sxs-lookup"><span data-stu-id="a6e70-145">Guidance</span></span>              |
  |--------------------|-----------|---------------------------|-----------------------|
  | <span data-ttu-id="a6e70-146">NetworkIP</span><span class="sxs-lookup"><span data-stu-id="a6e70-146">NetworkIP</span></span>          | <span data-ttu-id="a6e70-147">String</span><span class="sxs-lookup"><span data-stu-id="a6e70-147">String</span></span>    | <span data-ttu-id="a6e70-148">192.168.1.0</span><span class="sxs-lookup"><span data-stu-id="a6e70-148">192.168.1.0</span></span>               | <span data-ttu-id="a6e70-149">必需</span><span class="sxs-lookup"><span data-stu-id="a6e70-149">Required</span></span>              |
  | <span data-ttu-id="a6e70-150">NetworkName</span><span class="sxs-lookup"><span data-stu-id="a6e70-150">NetworkName</span></span>        | <span data-ttu-id="a6e70-151">String</span><span class="sxs-lookup"><span data-stu-id="a6e70-151">String</span></span>    | <span data-ttu-id="a6e70-152">USA/Seattle/SEATTLE-SEA-1</span><span class="sxs-lookup"><span data-stu-id="a6e70-152">USA/Seattle/SEATTLE-SEA-1</span></span> | <span data-ttu-id="a6e70-153">必需<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="a6e70-153">Required<sup>1</sup></span></span>  |
  | <span data-ttu-id="a6e70-154">NetworkRange</span><span class="sxs-lookup"><span data-stu-id="a6e70-154">NetworkRange</span></span>       | <span data-ttu-id="a6e70-155">数字</span><span class="sxs-lookup"><span data-stu-id="a6e70-155">Number</span></span>    | <span data-ttu-id="a6e70-156">26</span><span class="sxs-lookup"><span data-stu-id="a6e70-156">26</span></span>                        | <span data-ttu-id="a6e70-157">必需</span><span class="sxs-lookup"><span data-stu-id="a6e70-157">Required</span></span>              |
  | <span data-ttu-id="a6e70-158">BuildingName</span><span class="sxs-lookup"><span data-stu-id="a6e70-158">BuildingName</span></span>       | <span data-ttu-id="a6e70-159">String</span><span class="sxs-lookup"><span data-stu-id="a6e70-159">String</span></span>    | <span data-ttu-id="a6e70-160">SEATTLE-SEA-1</span><span class="sxs-lookup"><span data-stu-id="a6e70-160">SEATTLE-SEA-1</span></span>             | <span data-ttu-id="a6e70-161">必需<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="a6e70-161">Required<sup>1</sup></span></span>  |
  | <span data-ttu-id="a6e70-162">OwnershipType</span><span class="sxs-lookup"><span data-stu-id="a6e70-162">OwnershipType</span></span>      | <span data-ttu-id="a6e70-163">String</span><span class="sxs-lookup"><span data-stu-id="a6e70-163">String</span></span>    | <span data-ttu-id="a6e70-164">Contoso</span><span class="sxs-lookup"><span data-stu-id="a6e70-164">Contoso</span></span>                   | <span data-ttu-id="a6e70-165">可选</span><span class="sxs-lookup"><span data-stu-id="a6e70-165">Optional</span></span>              |
  | <span data-ttu-id="a6e70-166">BuildingType</span><span class="sxs-lookup"><span data-stu-id="a6e70-166">BuildingType</span></span>       | <span data-ttu-id="a6e70-167">String</span><span class="sxs-lookup"><span data-stu-id="a6e70-167">String</span></span>    | <span data-ttu-id="a6e70-168">IT 终止</span><span class="sxs-lookup"><span data-stu-id="a6e70-168">IT Termination</span></span>            | <span data-ttu-id="a6e70-169">可选</span><span class="sxs-lookup"><span data-stu-id="a6e70-169">Optional</span></span>              |
  | <span data-ttu-id="a6e70-170">BuildingOfficeType</span><span class="sxs-lookup"><span data-stu-id="a6e70-170">BuildingOfficeType</span></span> | <span data-ttu-id="a6e70-171">String</span><span class="sxs-lookup"><span data-stu-id="a6e70-171">String</span></span>    | <span data-ttu-id="a6e70-172">工程</span><span class="sxs-lookup"><span data-stu-id="a6e70-172">Engineering</span></span>               | <span data-ttu-id="a6e70-173">可选</span><span class="sxs-lookup"><span data-stu-id="a6e70-173">Optional</span></span>              |
  | <span data-ttu-id="a6e70-174">城市</span><span class="sxs-lookup"><span data-stu-id="a6e70-174">City</span></span>               | <span data-ttu-id="a6e70-175">String</span><span class="sxs-lookup"><span data-stu-id="a6e70-175">String</span></span>    | <span data-ttu-id="a6e70-176">西雅图</span><span class="sxs-lookup"><span data-stu-id="a6e70-176">Seattle</span></span>                   | <span data-ttu-id="a6e70-177">推荐</span><span class="sxs-lookup"><span data-stu-id="a6e70-177">Recommended</span></span>           |
  | <span data-ttu-id="a6e70-178">ZipCode</span><span class="sxs-lookup"><span data-stu-id="a6e70-178">ZipCode</span></span>            | <span data-ttu-id="a6e70-179">String</span><span class="sxs-lookup"><span data-stu-id="a6e70-179">String</span></span>    | <span data-ttu-id="a6e70-180">98001</span><span class="sxs-lookup"><span data-stu-id="a6e70-180">98001</span></span>                     | <span data-ttu-id="a6e70-181">推荐</span><span class="sxs-lookup"><span data-stu-id="a6e70-181">Recommended</span></span>           |
  | <span data-ttu-id="a6e70-182">国家/地区</span><span class="sxs-lookup"><span data-stu-id="a6e70-182">Country</span></span>            | <span data-ttu-id="a6e70-183">String</span><span class="sxs-lookup"><span data-stu-id="a6e70-183">String</span></span>    | <span data-ttu-id="a6e70-184">美国</span><span class="sxs-lookup"><span data-stu-id="a6e70-184">US</span></span>                        | <span data-ttu-id="a6e70-185">推荐</span><span class="sxs-lookup"><span data-stu-id="a6e70-185">Recommended</span></span>           |
  | <span data-ttu-id="a6e70-186">省/市/自治区</span><span class="sxs-lookup"><span data-stu-id="a6e70-186">State</span></span>              | <span data-ttu-id="a6e70-187">String</span><span class="sxs-lookup"><span data-stu-id="a6e70-187">String</span></span>    | <span data-ttu-id="a6e70-188">WA</span><span class="sxs-lookup"><span data-stu-id="a6e70-188">WA</span></span>                        | <span data-ttu-id="a6e70-189">推荐</span><span class="sxs-lookup"><span data-stu-id="a6e70-189">Recommended</span></span>           |
  | <span data-ttu-id="a6e70-190">区域</span><span class="sxs-lookup"><span data-stu-id="a6e70-190">Region</span></span>             | <span data-ttu-id="a6e70-191">String</span><span class="sxs-lookup"><span data-stu-id="a6e70-191">String</span></span>    | <span data-ttu-id="a6e70-192">MSUS</span><span class="sxs-lookup"><span data-stu-id="a6e70-192">MSUS</span></span>                      | <span data-ttu-id="a6e70-193">推荐</span><span class="sxs-lookup"><span data-stu-id="a6e70-193">Recommended</span></span>           |
  | <span data-ttu-id="a6e70-194">InsideCorp<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="a6e70-194">InsideCorp<sup>2</sup></span></span>         | <span data-ttu-id="a6e70-195">Bool</span><span class="sxs-lookup"><span data-stu-id="a6e70-195">Bool</span></span>      | <span data-ttu-id="a6e70-196">1</span><span class="sxs-lookup"><span data-stu-id="a6e70-196">1</span></span>             | <span data-ttu-id="a6e70-197">必需</span><span class="sxs-lookup"><span data-stu-id="a6e70-197">Required</span></span>              |
  | <span data-ttu-id="a6e70-198">ExpressRoute<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="a6e70-198">ExpressRoute<sup>3</sup></span></span>       | <span data-ttu-id="a6e70-199">Bool</span><span class="sxs-lookup"><span data-stu-id="a6e70-199">Bool</span></span>      | <span data-ttu-id="a6e70-200">0</span><span class="sxs-lookup"><span data-stu-id="a6e70-200">0</span></span>             | <span data-ttu-id="a6e70-201">必需</span><span class="sxs-lookup"><span data-stu-id="a6e70-201">Required</span></span>              |
  | <span data-ttu-id="a6e70-202">VPN</span><span class="sxs-lookup"><span data-stu-id="a6e70-202">VPN</span></span>                | <span data-ttu-id="a6e70-203">Bool</span><span class="sxs-lookup"><span data-stu-id="a6e70-203">Bool</span></span>      | <span data-ttu-id="a6e70-204">0</span><span class="sxs-lookup"><span data-stu-id="a6e70-204">0</span></span>                         | <span data-ttu-id="a6e70-205">可选</span><span class="sxs-lookup"><span data-stu-id="a6e70-205">Optional</span></span>              |

  <span data-ttu-id="a6e70-206"><sup>1</sup> CQD 不要求，但模板配置为显示"建筑物"和"网络名称"。</span><span class="sxs-lookup"><span data-stu-id="a6e70-206"><sup>1</sup> While not required by CQD, the templates are configured to display Building and Network name.</span></span>

  <span data-ttu-id="a6e70-207"><sup>2</sup> 此设置可用于反映子网是否在企业网络中。</span><span class="sxs-lookup"><span data-stu-id="a6e70-207"><sup>2</sup> This setting can be used to reflect whether or not the subnet is inside the corporate network.</span></span> <span data-ttu-id="a6e70-208">可以出于其他目的自定义使用情况。</span><span class="sxs-lookup"><span data-stu-id="a6e70-208">You can customize usage for other purposes.</span></span>

  <span data-ttu-id="a6e70-209"><sup>3</sup> 此设置可用于反映网络是否使用 Azure ExpressRoute。</span><span class="sxs-lookup"><span data-stu-id="a6e70-209"><sup>3</sup> This setting can be used to reflect whether or not the network uses Azure ExpressRoute.</span></span> <span data-ttu-id="a6e70-210">可以出于其他目的自定义使用情况。</span><span class="sxs-lookup"><span data-stu-id="a6e70-210">You can customize usage for other purposes.</span></span>  

  <span data-ttu-id="a6e70-211">**示例行：**</span><span class="sxs-lookup"><span data-stu-id="a6e70-211">**Sample row:**</span></span>

  `192.168.1.0,USA/Seattle/SEATTLE-SEA-1,26,SEATTLE-SEA-1,Contoso,IT Termination,Engineering,Seattle,98001,US,WA,MSUS,1,0,0`

> [!IMPORTANT]
> <span data-ttu-id="a6e70-212">网络范围可用于表示具有单个路由前缀的 (子网的超网络) 。</span><span class="sxs-lookup"><span data-stu-id="a6e70-212">The network range can be used to represent a supernet (combination of several subnets with a single routing prefix).</span></span> <span data-ttu-id="a6e70-213">所有新建筑物上载都将检查是否有重叠的范围。</span><span class="sxs-lookup"><span data-stu-id="a6e70-213">All new building uploads will be checked for any overlapping ranges.</span></span> <span data-ttu-id="a6e70-214">如果以前上传过一个建筑物文件，应下载当前文件，然后重新上传该文件，以确定任何重叠，并修复问题，然后再重新上传。</span><span class="sxs-lookup"><span data-stu-id="a6e70-214">If you have previously uploaded a building file, you should download the current file and re-upload it to identify any overlaps and fix the issue before uploading again.</span></span> <span data-ttu-id="a6e70-215">以前上传的文件的任何重叠都可能导致报告中子网与建筑物之间的映射错误。</span><span class="sxs-lookup"><span data-stu-id="a6e70-215">Any overlap in previously uploaded files may result in the wrong mappings of subnets to buildings in the reports.</span></span> <span data-ttu-id="a6e70-216">某些 VPN 实现无法准确报告子网信息。</span><span class="sxs-lookup"><span data-stu-id="a6e70-216">Certain VPN implementations do not accurately report the subnet information.</span></span> 
>
> <span data-ttu-id="a6e70-217">VPN 列是可选的，默认为 0。</span><span class="sxs-lookup"><span data-stu-id="a6e70-217">The VPN column is optional and will default to 0.</span></span> <span data-ttu-id="a6e70-218">如果 VPN 列的值设置为 1，则该行表示的子网将完全展开，以匹配子网内的所有 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="a6e70-218">If the VPN column’s value is set to 1, the subnet represented by that row will be fully expanded to match all IP addresses within the subnet.</span></span> <span data-ttu-id="a6e70-219">请尽量少用，仅对 VPN 子网使用，因为完全扩展这些子网会对涉及生成数据的查询的查询时间产生负面影响。</span><span class="sxs-lookup"><span data-stu-id="a6e70-219">Please use this sparingly and only for VPN subnets since fully expanding these subnets will have a negative impact on query times for queries involving building data.</span></span> <span data-ttu-id="a6e70-220">如果子网的扩展导致超出 1，000，000 的扩展行限制，则不接受生成文件。</span><span class="sxs-lookup"><span data-stu-id="a6e70-220">If the expansion of the subnet results in the expansion row limit of 1,000,000 being exceeded, the building file will not be accepted.</span></span>


### <a name="supernetting"></a><span data-ttu-id="a6e70-221">Supernetting</span><span class="sxs-lookup"><span data-stu-id="a6e70-221">Supernetting</span></span>

<span data-ttu-id="a6e70-222">可以使用超级网络（通常称为无Inter-Domain路由 (CIDR，) 定义每个子网。</span><span class="sxs-lookup"><span data-stu-id="a6e70-222">You can use supernetting, commonly called Classless Inter-Domain Routing (CIDR,) in place of defining each subnet.</span></span> <span data-ttu-id="a6e70-223">超级 *网络* 是共享单个路由前缀的几个子网的组合。</span><span class="sxs-lookup"><span data-stu-id="a6e70-223">A *supernet* is a combination of several subnets that share a single routing prefix.</span></span> <span data-ttu-id="a6e70-224">可以使用超网络地址，而不是添加每个子网的条目。</span><span class="sxs-lookup"><span data-stu-id="a6e70-224">Instead of adding an entry for each subnet, you can use the supernetted address.</span></span> <span data-ttu-id="a6e70-225">支持超网络，但我们不建议使用它。</span><span class="sxs-lookup"><span data-stu-id="a6e70-225">Supernetting is supported, but we don't recommend using it.</span></span>

<span data-ttu-id="a6e70-226">例如，Contoso 的营销大楼由以下子网决定：</span><span class="sxs-lookup"><span data-stu-id="a6e70-226">For example, Contoso's marketing building is made up of the subnets below:</span></span>

-   <span data-ttu-id="a6e70-227">10.1.0.0/24 — 一楼</span><span class="sxs-lookup"><span data-stu-id="a6e70-227">10.1.0.0/24—first floor</span></span>
-   <span data-ttu-id="a6e70-228">10.1.1.0/24 — 二楼</span><span class="sxs-lookup"><span data-stu-id="a6e70-228">10.1.1.0/24—second floor</span></span>
-   <span data-ttu-id="a6e70-229">10.1.2.0/24 — 三楼</span><span class="sxs-lookup"><span data-stu-id="a6e70-229">10.1.2.0/24—third floor</span></span>
-   <span data-ttu-id="a6e70-230">10.1.3.0/24 — 第四层</span><span class="sxs-lookup"><span data-stu-id="a6e70-230">10.1.3.0/24—fourth floor</span></span>

<span data-ttu-id="a6e70-231">可以使用超网络地址（本示例中为 10.1.0.0/22）而不是添加每个子网的条目。</span><span class="sxs-lookup"><span data-stu-id="a6e70-231">Instead of adding an entry for each subnet, you can use the supernetted address—in this example, 10.1.0.0/22.</span></span>

-   <span data-ttu-id="a6e70-232">网络 = 10.1.0.0</span><span class="sxs-lookup"><span data-stu-id="a6e70-232">Network = 10.1.0.0</span></span>
-   <span data-ttu-id="a6e70-233">网络范围 = 22</span><span class="sxs-lookup"><span data-stu-id="a6e70-233">Network Range = 22</span></span>

<span data-ttu-id="a6e70-234">实现超网之前，需要考虑以下一些操作：</span><span class="sxs-lookup"><span data-stu-id="a6e70-234">Here are a few things to consider before you implement supernetting:</span></span>

-   <span data-ttu-id="a6e70-235">超级网络只能在具有 8 位到 28 位掩码的子网映射中使用。</span><span class="sxs-lookup"><span data-stu-id="a6e70-235">Supernetting can only be used in a subnet mapping with 8-bit to 28-bit mask.</span></span>

-   <span data-ttu-id="a6e70-236">超网占用的前面时间更少，但代价是降低数据的丰富性。</span><span class="sxs-lookup"><span data-stu-id="a6e70-236">Supernetting takes less time up front, but it comes at the cost of reducing the richness of your data.</span></span> <span data-ttu-id="a6e70-237">假设存在涉及子网 10.1.2.0 的质量问题。</span><span class="sxs-lookup"><span data-stu-id="a6e70-237">Let's say there's a quality problem involving subnet 10.1.2.0.</span></span> <span data-ttu-id="a6e70-238">如果实现了超网络化，则不知道子网在建筑物中的什么位置，或者它 (类型的网络，例如实验室) 。</span><span class="sxs-lookup"><span data-stu-id="a6e70-238">If you implemented supernetting, you won't know where in the building the subnet is located or what type of network it is (for example, a lab).</span></span> <span data-ttu-id="a6e70-239">如果已定义建筑物的所有子网和上载的楼层位置信息，则能够看到这种区别。</span><span class="sxs-lookup"><span data-stu-id="a6e70-239">If you'd defined all the subnets for a building and uploaded floor location information, you'd be able to see that distinction.</span></span>

-   <span data-ttu-id="a6e70-240">确保超网络地址正确且不会捕获不需要的子网，这一点很重要。</span><span class="sxs-lookup"><span data-stu-id="a6e70-240">It's important to ensure that the supernetted address is correct and isn't catching unwanted subnets.</span></span>

-   <span data-ttu-id="a6e70-241">在数据中查找 192.168.0.0 很常见。</span><span class="sxs-lookup"><span data-stu-id="a6e70-241">It's quite common to find 192.168.0.0 in data.</span></span> <span data-ttu-id="a6e70-242">对于许多组织，这表示用户在家里。</span><span class="sxs-lookup"><span data-stu-id="a6e70-242">For many organizations, this indicates that the user is at home.</span></span> <span data-ttu-id="a6e70-243">对于其他人，这是卫星办公室的 IP 地址方案。</span><span class="sxs-lookup"><span data-stu-id="a6e70-243">For others, this is the IP address scheme for a satellite office.</span></span> <span data-ttu-id="a6e70-244">如果组织有使用此配置办公室，请不要将其包括在建筑物文件中，因为使用公共子网难以区分家庭网络和内部 [网络](quality-of-experience-review-guide.md#common-subnets)。</span><span class="sxs-lookup"><span data-stu-id="a6e70-244">If your organization does have offices that use this configuration, don't include it in your building file because it's difficult to distinguish between home and internal networks by using [common subnets](quality-of-experience-review-guide.md#common-subnets).</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="a6e70-245">网络范围可用于表示超网络。</span><span class="sxs-lookup"><span data-stu-id="a6e70-245">The network range can be used to represent a supernet.</span></span> <span data-ttu-id="a6e70-246">所有新的建筑物数据文件上传都将检查是否有重叠的范围。</span><span class="sxs-lookup"><span data-stu-id="a6e70-246">All new building data file uploads will be checked for any overlapping ranges.</span></span> <span data-ttu-id="a6e70-247">如果以前上传过一个建筑物文件，应下载当前文件并再次上传该文件，以识别任何重叠并解决问题。</span><span class="sxs-lookup"><span data-stu-id="a6e70-247">If you've previously uploaded a building file, you should download the current file and upload it again to identify any overlaps and fix the issue.</span></span> <span data-ttu-id="a6e70-248">以前上传的文件的任何重叠都可能导致报告中子网与建筑物之间的映射错误。</span><span class="sxs-lookup"><span data-stu-id="a6e70-248">Any overlap in previously uploaded files might result in the wrong mappings of subnets to buildings in the reports.</span></span>

### <a name="vpn"></a><span data-ttu-id="a6e70-249">VPN</span><span class="sxs-lookup"><span data-stu-id="a6e70-249">VPN</span></span>

<span data-ttu-id="a6e70-250">QoE (质量) 客户端发送到 Microsoft 365 或 Office 365（CQD 数据的来源）的数据包括 VPN 标志。</span><span class="sxs-lookup"><span data-stu-id="a6e70-250">The quality of experience (QoE) data that clients send to Microsoft 365 or Office 365—which is where CQD data is sourced from—includes a VPN flag.</span></span> <span data-ttu-id="a6e70-251">CQD 将看到此为第一个 VPN 维度和第二个 VPN 维度。</span><span class="sxs-lookup"><span data-stu-id="a6e70-251">CQD will see this as the First VPN and Second VPN dimensions.</span></span> <span data-ttu-id="a6e70-252">但是，此标志依赖于 VPN 供应商向Windows注册的 VPN 网络适配器是远程访问适配器的报告。</span><span class="sxs-lookup"><span data-stu-id="a6e70-252">However, this flag relies on VPN vendors' reporting to Windows that the VPN network adapter registered is a Remote Access adapter.</span></span> <span data-ttu-id="a6e70-253">并非所有 VPN 供应商都正确注册远程访问适配器。</span><span class="sxs-lookup"><span data-stu-id="a6e70-253">Not all VPN vendors properly register Remote Access adapters.</span></span> <span data-ttu-id="a6e70-254">因此，可能无法使用内置的 VPN 查询筛选器。</span><span class="sxs-lookup"><span data-stu-id="a6e70-254">Because of this, you might not be able to use the built-in VPN query filters.</span></span> <span data-ttu-id="a6e70-255">使用上面讨论的 VPN 列准确标记和标识 VPN 子网。</span><span class="sxs-lookup"><span data-stu-id="a6e70-255">Use the VPN column discussed above to accurately mark and identify VPN subnets.</span></span> <span data-ttu-id="a6e70-256">此外，为 VPN 网络添加标签也是一种很好的做法，便于在报告中识别。</span><span class="sxs-lookup"><span data-stu-id="a6e70-256">It is also good practice to label your VPN networks for easy identification in your reports.</span></span> <span data-ttu-id="a6e70-257">下面是如何标记 VPN 子网的两个示例：</span><span class="sxs-lookup"><span data-stu-id="a6e70-257">Below are two examples of how to label your VPN subnets:</span></span>

- <span data-ttu-id="a6e70-258">在 VPN **子网的** 此字段中输入"VPN"，定义网络名称。</span><span class="sxs-lookup"><span data-stu-id="a6e70-258">Define a **Network Name** by entering "VPN" in this field for VPN subnets.</span></span>

  ![显示使用网络名称的 VPN 的 QCD 报告屏幕截图](media/qerguide-image-vpnnetworkname.png)

- <span data-ttu-id="a6e70-260">在 VPN **子网的此字段** 中输入"VPN"，定义建筑物名称。</span><span class="sxs-lookup"><span data-stu-id="a6e70-260">Define a **Building Name** by entering "VPN" in this field for VPN subnets.</span></span>

  ![显示使用建筑物名称的 VPN 的 QCD 报告屏幕截图](media/qerguide-image-vpnbuildingname.png)

> [!NOTE]
> <span data-ttu-id="a6e70-262">VPN 连接已知在基础连接为无线时将网络连接类型错误识别为有线。</span><span class="sxs-lookup"><span data-stu-id="a6e70-262">VPN connections have been known to misidentify the network connection type as wired when the underlying connection is wireless.</span></span> <span data-ttu-id="a6e70-263">通过 VPN 连接查看质量时，无法假定已准确标识连接类型。</span><span class="sxs-lookup"><span data-stu-id="a6e70-263">When looking at quality over VPN connections, you can't assume that the connection type has been accurately identified.</span></span>

## <a name="endpoint-data-file"></a><span data-ttu-id="a6e70-264">终结点数据文件</span><span class="sxs-lookup"><span data-stu-id="a6e70-264">Endpoint data file</span></span>

<span data-ttu-id="a6e70-265">另一种类型的 CQD 租户数据文件是 **终结点** 数据文件。</span><span class="sxs-lookup"><span data-stu-id="a6e70-265">The other type of CQD tenant data file is the **Endpoint** data file.</span></span> <span data-ttu-id="a6e70-266">列值用于调用记录的"第一个客户端终结点名称"或"第二个客户端终结点名称"列中，以显示终结点制造、模型或类型信息。</span><span class="sxs-lookup"><span data-stu-id="a6e70-266">The column values are used in the call record’s First Client Endpoint Name or Second Client Endpoint Name column to show Endpoint Make, Model, or Type information.</span></span> <span data-ttu-id="a6e70-267">上传的数据文件的格式必须满足以下条件，才能在上传前通过验证检查：</span><span class="sxs-lookup"><span data-stu-id="a6e70-267">The format of the data file you upload must meet the following criteria to pass the validation check before upload:</span></span>

- <span data-ttu-id="a6e70-268">该文件必须是 .tsv 文件 (制表符分隔) 或 .csv 文件 (以逗号分隔) 。</span><span class="sxs-lookup"><span data-stu-id="a6e70-268">The file must be either a .tsv file (columns are separated by a TAB) or a .csv file (columns are separated by a comma).</span></span>

- <span data-ttu-id="a6e70-269">数据文件的内容不包括表标题。</span><span class="sxs-lookup"><span data-stu-id="a6e70-269">The content of the data file doesn't include table headers.</span></span> <span data-ttu-id="a6e70-270">数据文件的第一行应该是实际数据，而不是标头标签（如"EndpointName"）。</span><span class="sxs-lookup"><span data-stu-id="a6e70-270">The first line of the data file is expected to be real data, not a header label like "EndpointName".</span></span>

- <span data-ttu-id="a6e70-271">所有七列都仅使用字符串数据类型字符串。</span><span class="sxs-lookup"><span data-stu-id="a6e70-271">All seven columns use the String data type only.</span></span> <span data-ttu-id="a6e70-272">允许的最大长度为 64 个字符。</span><span class="sxs-lookup"><span data-stu-id="a6e70-272">The maximum allowed length is 64 characters.</span></span>

- <span data-ttu-id="a6e70-273">数据字段可以为空，但仍必须以制表符或逗号分隔。</span><span class="sxs-lookup"><span data-stu-id="a6e70-273">A data field can be empty but must still be separated by a tab or comma.</span></span> <span data-ttu-id="a6e70-274">空数据字段只分配一个空的字符串值。</span><span class="sxs-lookup"><span data-stu-id="a6e70-274">An empty data field just assigns an empty String value.</span></span>

- <span data-ttu-id="a6e70-275">EndpointName 必须唯一，否则上传失败。</span><span class="sxs-lookup"><span data-stu-id="a6e70-275">EndpointName must be unique, otherwise the upload fails.</span></span> <span data-ttu-id="a6e70-276">如果存在重复的一行或两行使用相同的 EndpointName，则冲突将导致联接错误。</span><span class="sxs-lookup"><span data-stu-id="a6e70-276">If there is a duplicate row or two rows that use the same EndpointName the conflict will  cause incorrect joining.</span></span>

- <span data-ttu-id="a6e70-277">EndpointLabel1、EndpointLabel2 和 EndpointLabel3 是可自定义的标签。</span><span class="sxs-lookup"><span data-stu-id="a6e70-277">EndpointLabel1, EndpointLabel2, and EndpointLabel3 are customizable labels.</span></span> <span data-ttu-id="a6e70-278">它们可以为空字符串或值，例如"IT 部门指定的 2018 笔记本电脑"或"资产标记 5678"。</span><span class="sxs-lookup"><span data-stu-id="a6e70-278">They can be empty Strings or values such as “IT Department designated 2018 Laptop” or “Asset Tag 5678”.</span></span>

- <span data-ttu-id="a6e70-279">每行必须有七列，列必须按以下顺序排列：</span><span class="sxs-lookup"><span data-stu-id="a6e70-279">There must be seven columns for each row and the columns must be in the following order:</span></span>

  <span data-ttu-id="a6e70-280">**域顺序：**</span><span class="sxs-lookup"><span data-stu-id="a6e70-280">**Field order:**</span></span>

  <span data-ttu-id="a6e70-281">EndpointName、EndpointMake、EndpointModel、EndpointType、EndpointLabel1、EndpointLabel2、EndpointLabel3</span><span class="sxs-lookup"><span data-stu-id="a6e70-281">EndpointName, EndpointMake, EndpointModel, EndpointType, EndpointLabel1, EndpointLabel2,  EndpointLabel3</span></span>

  <span data-ttu-id="a6e70-282">**示例行：**</span><span class="sxs-lookup"><span data-stu-id="a6e70-282">**Sample row:**</span></span>

  `1409W3534, Fabrikam, Model 123, Laptop, IT designated 2018 Laptop, Asset Tag 5678, Purchase 2018`

## <a name="update-a-building-file"></a><span data-ttu-id="a6e70-283">更新建筑物文件</span><span class="sxs-lookup"><span data-stu-id="a6e70-283">Update a building file</span></span>

<span data-ttu-id="a6e70-284">收集建筑物和子网信息时，管理员通常会在一段时间的多次迭代中上传该建筑物文件，添加新子网及其建筑物信息，因为它可用。</span><span class="sxs-lookup"><span data-stu-id="a6e70-284">While gathering building and subnet information, administrators will often upload the building file in multiple iterations over time, adding new subnets and their building information as it becomes available.</span></span> <span data-ttu-id="a6e70-285">发生这种情况时，需要重新上传建筑物文件。</span><span class="sxs-lookup"><span data-stu-id="a6e70-285">When this occurs, you'll need to re-upload your building file.</span></span> <span data-ttu-id="a6e70-286">此过程与上一部分中所述的初始上传类似，但以下部分介绍了一些例外。</span><span class="sxs-lookup"><span data-stu-id="a6e70-286">This process is like the initial upload as described in the previous section, with a few exceptions as noted in the following section.</span></span>

> [!Important]
> <span data-ttu-id="a6e70-287">一次只能有一个建筑物文件处于活动状态。</span><span class="sxs-lookup"><span data-stu-id="a6e70-287">Only one building file can be active at a time.</span></span> <span data-ttu-id="a6e70-288">多个建筑物文件不是累积的。</span><span class="sxs-lookup"><span data-stu-id="a6e70-288">Multiple building files aren't cumulative.</span></span>

## <a name="add-net-new-subnets"></a><span data-ttu-id="a6e70-289">添加新子网</span><span class="sxs-lookup"><span data-stu-id="a6e70-289">Add net new subnets</span></span>

<span data-ttu-id="a6e70-290">有时，需要向 CQD 添加最初不是网络拓扑一部分的新子网。</span><span class="sxs-lookup"><span data-stu-id="a6e70-290">There are times when you'll need to add net new subnets to CQD that weren't originally part of your network topology.</span></span> <span data-ttu-id="a6e70-291">若要添加新子网，请从 CQD 中的"租户数据 **"Upload** 页执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="a6e70-291">To add net new subnets, do the following from the **Tenant Data Upload** page in CQD:</span></span>

1.  <span data-ttu-id="a6e70-292">下载原始文件（如果还没有最新副本）。</span><span class="sxs-lookup"><span data-stu-id="a6e70-292">Download the original file, if you don't already have an up-to-date copy.</span></span>

1.  <span data-ttu-id="a6e70-293">删除 CQD 中的当前文件。</span><span class="sxs-lookup"><span data-stu-id="a6e70-293">Remove the current file in CQD.</span></span>

1.  <span data-ttu-id="a6e70-294">编辑原始建筑物文件，并提供在获取新子网之前至少一天的结束日期。</span><span class="sxs-lookup"><span data-stu-id="a6e70-294">Edit the original building file and provide an end date that occurs at least one day before the net new subnets were acquired.</span></span>

1.  <span data-ttu-id="a6e70-295">将网络新子网追加到原始建筑物文件。</span><span class="sxs-lookup"><span data-stu-id="a6e70-295">Append the net new subnets to the original building file.</span></span>

1.  <span data-ttu-id="a6e70-296">Upload新修改的建筑物文件，将开始日期设置为上一个建筑物文件结束后的一天。</span><span class="sxs-lookup"><span data-stu-id="a6e70-296">Upload the newly modified building file, and set the start date for one day after the previous building file ends.</span></span>

## <a name="add-missing-subnets"></a><span data-ttu-id="a6e70-297">添加缺少的子网</span><span class="sxs-lookup"><span data-stu-id="a6e70-297">Add missing subnets</span></span>

<span data-ttu-id="a6e70-298">上传托管网络的建筑物信息后，每个托管网络都应具有建筑物关联。</span><span class="sxs-lookup"><span data-stu-id="a6e70-298">After you upload building information for managed networks, every managed network should have a building association.</span></span> <span data-ttu-id="a6e70-299">但是，情况并非总是如此;通常，会遗漏几个子网。</span><span class="sxs-lookup"><span data-stu-id="a6e70-299">However, this won't always be the case; typically, a few subnets are missed.</span></span> <span data-ttu-id="a6e70-300">若要查找这些缺失的网络，请查看CQD 中"体验质量报告 **"页上的**"缺少子网报告"。</span><span class="sxs-lookup"><span data-stu-id="a6e70-300">To find these missing networks, review the **Missing Subnet Report** on the **Quality of Experience Reports** page in CQD.</span></span> <span data-ttu-id="a6e70-301">这会向所有子网显示 10 个或多个音频流，这些音频流未在建筑物数据文件中定义，并且被标记为外部。</span><span class="sxs-lookup"><span data-stu-id="a6e70-301">This presents all the subnets with 10 or more audio streams that aren't defined in the building data file and are being marked as outside.</span></span> <span data-ttu-id="a6e70-302">请确保此列表中没有托管网络。</span><span class="sxs-lookup"><span data-stu-id="a6e70-302">Ensure that there are no managed networks in this list.</span></span> <span data-ttu-id="a6e70-303">如果缺少子网，请使用以下过程更新原始建筑物数据文件，并将其重新上传到 CQD。</span><span class="sxs-lookup"><span data-stu-id="a6e70-303">If subnets are missing, use the following procedure to update the original building data file and re-upload it to CQD.</span></span>

1. <span data-ttu-id="a6e70-304">转到 CQD **Upload"** 租户数据"页。</span><span class="sxs-lookup"><span data-stu-id="a6e70-304">Go to the **Tenant Data Upload** page in CQD.</span></span>

1. <span data-ttu-id="a6e70-305">下载原始文件（如果还没有最新副本）。</span><span class="sxs-lookup"><span data-stu-id="a6e70-305">Download the original file, if you don't already have an up-to-date copy.</span></span>

1. <span data-ttu-id="a6e70-306">删除 CQD 中的当前文件。</span><span class="sxs-lookup"><span data-stu-id="a6e70-306">Remove the current file in CQD.</span></span>

1. <span data-ttu-id="a6e70-307">将新子网追加到原始文件。</span><span class="sxs-lookup"><span data-stu-id="a6e70-307">Append the new subnets to the original file.</span></span>

1. <span data-ttu-id="a6e70-308">Upload生成文件。</span><span class="sxs-lookup"><span data-stu-id="a6e70-308">Upload the building file.</span></span> <span data-ttu-id="a6e70-309">请确保将开始日期设置为至少八个月之前，以便 CQD 将处理历史数据。</span><span class="sxs-lookup"><span data-stu-id="a6e70-309">Be sure to set the start date to at least eight months prior so that CQD will process historical data.</span></span>


> [!IMPORTANT]
> <span data-ttu-id="a6e70-310">需要将租户 ID 作为第二租户 **ID** 的查询筛选器添加到此报表，以筛选报表，以便仅查看组织的租户数据。</span><span class="sxs-lookup"><span data-stu-id="a6e70-310">You'll need to add your tenant ID as a query filter for **Second Tenant ID** to this report to filter the report to view only your organization's tenant data.</span></span> <span data-ttu-id="a6e70-311">否则，报告会显示联合子网。</span><span class="sxs-lookup"><span data-stu-id="a6e70-311">Otherwise, the report will show federated subnets.</span></span>

> [!NOTE] 
> <span data-ttu-id="a6e70-312">请务必将"月年"报表筛选器调整为当前月份。</span><span class="sxs-lookup"><span data-stu-id="a6e70-312">Be sure to adjust the Month Year report filter to the current month.</span></span> <span data-ttu-id="a6e70-313">选择 **"编辑**"，然后调整 **"月份年份** "报表筛选器以保存新的默认月份。</span><span class="sxs-lookup"><span data-stu-id="a6e70-313">Select **Edit**, and adjust the **Month Year** report filter to save the new default month.</span></span>


## <a name="related-topics"></a><span data-ttu-id="a6e70-314">相关主题</span><span class="sxs-lookup"><span data-stu-id="a6e70-314">Related topics</span></span>

[<span data-ttu-id="a6e70-315">为 CQD 创建建筑地图</span><span class="sxs-lookup"><span data-stu-id="a6e70-315">Create a building map for CQD</span></span>](CQD-building-mapping.md)

[<span data-ttu-id="a6e70-316">改进和监视呼叫质量Teams</span><span class="sxs-lookup"><span data-stu-id="a6e70-316">Improve and monitor call quality for Teams</span></span>](monitor-call-quality-qos.md)

[<span data-ttu-id="a6e70-317">什么是 CQD？</span><span class="sxs-lookup"><span data-stu-id="a6e70-317">What is CQD?</span></span>](CQD-what-is-call-quality-dashboard.md)

[<span data-ttu-id="a6e70-318">使用 CQD (设置呼叫质量) </span><span class="sxs-lookup"><span data-stu-id="a6e70-318">Set up Call Quality Dashboard (CQD)</span></span>](turning-on-and-using-call-quality-dashboard.md)

[<span data-ttu-id="a6e70-319">CQD 数据和报表</span><span class="sxs-lookup"><span data-stu-id="a6e70-319">CQD data and reports</span></span>](CQD-data-and-reports.md)

[<span data-ttu-id="a6e70-320">使用 CQD 管理呼叫和会议质量</span><span class="sxs-lookup"><span data-stu-id="a6e70-320">Use CQD to manage call and meeting quality</span></span>](quality-of-experience-review-guide.md)

[<span data-ttu-id="a6e70-321">CQD 中可用的维度和度量值</span><span class="sxs-lookup"><span data-stu-id="a6e70-321">Dimensions and measures available in CQD</span></span>](dimensions-and-measures-available-in-call-quality-dashboard.md)

[<span data-ttu-id="a6e70-322">CQD 中的流分类</span><span class="sxs-lookup"><span data-stu-id="a6e70-322">Stream Classification in CQD</span></span>](stream-classification-in-call-quality-dashboard.md)

[<span data-ttu-id="a6e70-323">使用Power BI分析 CQD 数据</span><span class="sxs-lookup"><span data-stu-id="a6e70-323">Use Power BI to analyze CQD data</span></span>](CQD-Power-BI-query-templates.md)
