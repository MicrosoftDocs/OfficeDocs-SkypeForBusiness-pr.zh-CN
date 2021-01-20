---
title: '在 CQD 仪表板的"呼叫质量仪表板" (租户和) '
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
description: 了解如何在 CQD 仪表板的"呼叫质量仪表板" (租户和) 。
ms.openlocfilehash: a7f8b4a8d84429b752692cf05013dfba7321fd5e
ms.sourcegitcommit: fdef9b52247097e5cae64f01b6b2b710c5b203cf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/20/2021
ms.locfileid: "49909346"
---
# <a name="upload-tenant-and-building-data-in-call-quality-dashboard-cqd"></a><span data-ttu-id="ae7f5-103">在 CQD 仪表板的"呼叫质量仪表板" (租户和) </span><span class="sxs-lookup"><span data-stu-id="ae7f5-103">Upload tenant and building data in Call Quality Dashboard (CQD)</span></span>


<span data-ttu-id="ae7f5-104">若要在 CQD (中) 通话质量仪表板，建议上传租户和建筑物数据。</span><span class="sxs-lookup"><span data-stu-id="ae7f5-104">To get the most out of Call Quality Dashboard (CQD), we recommend that you upload your tenant and building data.</span></span> <span data-ttu-id="ae7f5-105">有 2 种类型的租户数据文件，[即"建筑物"和](#upload-building-data-file)"[终结点"。](#endpoint-data-file)</span><span class="sxs-lookup"><span data-stu-id="ae7f5-105">There are 2 types of tenant data files, [Building](#upload-building-data-file) and [Endpoint](#endpoint-data-file).</span></span>

<span data-ttu-id="ae7f5-106">可以在此处下载示例租户数据 [模板](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/locations-template.zip?raw=true)。</span><span class="sxs-lookup"><span data-stu-id="ae7f5-106">You can download a sample tenant data template [here](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/locations-template.zip?raw=true).</span></span> <span data-ttu-id="ae7f5-107">有关建筑物映射的帮助，请阅读"[为 CQD 创建建筑物地图"。](CQD-building-mapping.md)</span><span class="sxs-lookup"><span data-stu-id="ae7f5-107">For help with building mapping, read [Create a building map for CQD](CQD-building-mapping.md).</span></span>

<span data-ttu-id="ae7f5-108">在 CQD 摘要报表仪表板中，从 CQD 设置菜单中选择"租户数据上传 (CQD 报表顶部的齿轮图标) 。</span><span class="sxs-lookup"><span data-stu-id="ae7f5-108">From the CQD Summary Reports dashboard, select **Tenant Data Upload** from the CQD **Settings** menu (a gear icon at the top of CQD).</span></span> <span data-ttu-id="ae7f5-109">在这里，管理员可以上传其组织的建筑物和终结点信息，例如 IP 地址和地理信息的映射、映射每个无线接入点及其 MAC 地址，等等。</span><span class="sxs-lookup"><span data-stu-id="ae7f5-109">From here, admins can upload their organization's building and endpoint information, such as mapping of IP addresses and geographical information, mapping each wireless access point and its MAC address, etc.</span></span>

1. <span data-ttu-id="ae7f5-110">从 Teams (中心或) 打开 CQD 租户，然后选择右上角的齿轮图标，然后从"摘要报表"页选择"租户数据上传 [https://cqd.teams.microsoft.com](https://cqd.teams.microsoft.com) "。  </span><span class="sxs-lookup"><span data-stu-id="ae7f5-110">Open CQD (from the Teams admin center, or at [https://cqd.teams.microsoft.com](https://cqd.teams.microsoft.com)), then select the gear icon in the upper-right corner and choose **Tenant Data Upload** from the **Summary Reports** page.</span></span>

   ![上传数据时出现的对话框的屏幕截图](media/qerguide-image-tenantdataupload.png)
    
2. <span data-ttu-id="ae7f5-112">或者，如果这是您第一次访问 CQD，系统将会要求您上传建筑物数据。</span><span class="sxs-lookup"><span data-stu-id="ae7f5-112">Alternatively, if this is your first time visiting CQD, you'll be asked to upload building data.</span></span> <span data-ttu-id="ae7f5-113">可以选择" **立即上传** "以快速导航到 **"租户数据上传"** 页。</span><span class="sxs-lookup"><span data-stu-id="ae7f5-113">You can select **Upload Now** to quickly navigate to the **Tenant Data Upload** page.</span></span>

   ![横幅的屏幕截图，通知用户上传建筑物数据](media/qerguide-image-buildingdatauploadbanner.png)

3. <span data-ttu-id="ae7f5-115">在" **租户数据上传"** 页上，选择 **"浏览** "以选择数据文件。</span><span class="sxs-lookup"><span data-stu-id="ae7f5-115">On the **Tenant Data Upload** page, select **Browse** to choose a data file.</span></span>

4. <span data-ttu-id="ae7f5-116">选择数据文件后，指定 **开始日期** ，并选择性地指定结束日期。</span><span class="sxs-lookup"><span data-stu-id="ae7f5-116">After selecting a data file, specify **Start date** and, optionally, specify an end date.</span></span>

5. <span data-ttu-id="ae7f5-117">选择开始日期 **后，** 选择 **"上传** "以将文件上传到 CQD。</span><span class="sxs-lookup"><span data-stu-id="ae7f5-117">After selecting **Start date**, select **Upload** to upload the file to CQD.</span></span> <br><br><span data-ttu-id="ae7f5-118">上传文件之前，会验证该文件。</span><span class="sxs-lookup"><span data-stu-id="ae7f5-118">Before the file is uploaded, it's validated.</span></span> <span data-ttu-id="ae7f5-119">如果验证失败，将显示一条错误消息，请求更正文件。</span><span class="sxs-lookup"><span data-stu-id="ae7f5-119">If validation fails, an error message is displayed requesting that you correct the file.</span></span> <span data-ttu-id="ae7f5-120">下图显示了当数据文件中的列数不正确时发生的错误。</span><span class="sxs-lookup"><span data-stu-id="ae7f5-120">The following figure shows an error occurring when the number of columns in the data file is incorrect.</span></span>

   ![显示建筑物数据上传错误的对话框示例](media/qerguide-image-buildingdatauploaderror.png)
 
6. <span data-ttu-id="ae7f5-122">如果在验证期间未发生错误，文件上传会成功。</span><span class="sxs-lookup"><span data-stu-id="ae7f5-122">If no errors occur during validation, the file upload will succeed.</span></span> <span data-ttu-id="ae7f5-123">然后，可以在"我的上传"表中看到上传的数据文件，其中显示页面底部当前租户的所有已上传文件的完整列表。</span><span class="sxs-lookup"><span data-stu-id="ae7f5-123">You can then see the uploaded data file in the **My uploads** table, which shows the full list of all uploaded files for the current tenant at the bottom of that page.</span></span>

> [!NOTE]
> <span data-ttu-id="ae7f5-124">可能需要 4 小时才能完成生成文件的处理。</span><span class="sxs-lookup"><span data-stu-id="ae7f5-124">It can take up to four hours to finish processing the building file.</span></span> <br><br> <span data-ttu-id="ae7f5-125">如果已上传建筑物文件，并且需要添加可能错过或排除的子网，请通过添加新子网来修改原始文件，删除当前文件，然后重新上传新编辑的文件。</span><span class="sxs-lookup"><span data-stu-id="ae7f5-125">If you've already uploaded a building file and need to add subnets that might have been missed or excluded, modify the original file by adding the new subnets, remove the current file, and re-upload the newly edited file.</span></span> <span data-ttu-id="ae7f5-126">CQD 中只能有一个活动的建筑物数据文件。</span><span class="sxs-lookup"><span data-stu-id="ae7f5-126">There can be only one active building data file in CQD.</span></span> 


## <a name="upload-building-data-file"></a><span data-ttu-id="ae7f5-127">上传建筑物数据文件</span><span class="sxs-lookup"><span data-stu-id="ae7f5-127">Upload building data file</span></span>

<span data-ttu-id="ae7f5-128">CQD 中第一种类型的租户数据文件是 **建筑物** 数据文件。</span><span class="sxs-lookup"><span data-stu-id="ae7f5-128">The first type of tenant data file in CQD is the **Building** data file.</span></span> <span data-ttu-id="ae7f5-129">通过展开 Network+NetworkRange 列，然后将子网列联接到呼叫记录的第一个子网或第二个子网列以显示建筑物、城市、国家/地区或区域信息，派生子网列。</span><span class="sxs-lookup"><span data-stu-id="ae7f5-129">The Subnet column is derived by expanding the Network+NetworkRange column, then joining the Subnet column to the call record’s First Subnet or Second Subnet column to show Building, City, Country, or Region information.</span></span> <span data-ttu-id="ae7f5-130">上传的数据文件的格式必须满足以下条件，才能在上传前通过验证检查：</span><span class="sxs-lookup"><span data-stu-id="ae7f5-130">The format of the data file you upload must meet the following criteria to pass the validation check before upload:</span></span>
  
- <span data-ttu-id="ae7f5-131">该文件必须是 .tsv 文件， (制表符分隔列) 或 .csv 文件 (以逗号分隔) 。</span><span class="sxs-lookup"><span data-stu-id="ae7f5-131">The file must be either a .tsv file (columns are separated by a TAB) or a .csv file (columns are separated by a comma).</span></span>

- <span data-ttu-id="ae7f5-132">数据文件不包括表标题行。</span><span class="sxs-lookup"><span data-stu-id="ae7f5-132">The data file doesn't include a table header row.</span></span> <span data-ttu-id="ae7f5-133">数据文件的第一行应该是实际数据，而不是标头标签（如"网络"）。</span><span class="sxs-lookup"><span data-stu-id="ae7f5-133">The first line of the data file is expected to be real data, not header labels like "Network".</span></span>

- <span data-ttu-id="ae7f5-134">该文件中的数据类型只能是字符串、整数或布尔值。</span><span class="sxs-lookup"><span data-stu-id="ae7f5-134">Data types in the file can only be String, Integer, or Boolean.</span></span> <span data-ttu-id="ae7f5-135">对于整数数据类型，该值必须是数值。</span><span class="sxs-lookup"><span data-stu-id="ae7f5-135">For the  Integer data type, the value must be a numeric value.</span></span> <span data-ttu-id="ae7f5-136">布尔值必须是 0 或 1。</span><span class="sxs-lookup"><span data-stu-id="ae7f5-136">Boolean values must be either 0 or 1.</span></span>

- <span data-ttu-id="ae7f5-137">如果列使用字符串数据类型，则数据字段可以为空，但仍必须以制表符或逗号分隔。</span><span class="sxs-lookup"><span data-stu-id="ae7f5-137">If a column uses the String data type, a data field can be empty but must still be separated by a tab or comma.</span></span> <span data-ttu-id="ae7f5-138">空数据字段只分配空字符串值。</span><span class="sxs-lookup"><span data-stu-id="ae7f5-138">An empty data field just assigns an empty String value.</span></span>

- <span data-ttu-id="ae7f5-139">每行必须包含 15 列，每列必须具有相应的 数据类型，列必须按照下表中列出的顺序（以逗号或制表符分隔 (分隔) ：</span><span class="sxs-lookup"><span data-stu-id="ae7f5-139">There must be 15 columns for each row, each column must have the appropriate data type, and the columns must be in the order listed in the following table (comma or tab delimited):</span></span>

  <span data-ttu-id="ae7f5-140">**构建数据文件格式**</span><span class="sxs-lookup"><span data-stu-id="ae7f5-140">**Building data file format**</span></span>
  
  | <span data-ttu-id="ae7f5-141">列名称</span><span class="sxs-lookup"><span data-stu-id="ae7f5-141">Column name</span></span>        | <span data-ttu-id="ae7f5-142">数据类型</span><span class="sxs-lookup"><span data-stu-id="ae7f5-142">Data type</span></span> | <span data-ttu-id="ae7f5-143">示例</span><span class="sxs-lookup"><span data-stu-id="ae7f5-143">Example</span></span>                   | <span data-ttu-id="ae7f5-144">指引</span><span class="sxs-lookup"><span data-stu-id="ae7f5-144">Guidance</span></span>              |
  |--------------------|-----------|---------------------------|-----------------------|
  | <span data-ttu-id="ae7f5-145">NetworkIP</span><span class="sxs-lookup"><span data-stu-id="ae7f5-145">NetworkIP</span></span>          | <span data-ttu-id="ae7f5-146">String</span><span class="sxs-lookup"><span data-stu-id="ae7f5-146">String</span></span>    | <span data-ttu-id="ae7f5-147">192.168.1.0</span><span class="sxs-lookup"><span data-stu-id="ae7f5-147">192.168.1.0</span></span>               | <span data-ttu-id="ae7f5-148">必需</span><span class="sxs-lookup"><span data-stu-id="ae7f5-148">Required</span></span>              |
  | <span data-ttu-id="ae7f5-149">NetworkName</span><span class="sxs-lookup"><span data-stu-id="ae7f5-149">NetworkName</span></span>        | <span data-ttu-id="ae7f5-150">String</span><span class="sxs-lookup"><span data-stu-id="ae7f5-150">String</span></span>    | <span data-ttu-id="ae7f5-151">USA/Seattle/SEATTLE-SEA-1</span><span class="sxs-lookup"><span data-stu-id="ae7f5-151">USA/Seattle/SEATTLE-SEA-1</span></span> | <span data-ttu-id="ae7f5-152">必需<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="ae7f5-152">Required<sup>1</sup></span></span>  |
  | <span data-ttu-id="ae7f5-153">NetworkRange</span><span class="sxs-lookup"><span data-stu-id="ae7f5-153">NetworkRange</span></span>       | <span data-ttu-id="ae7f5-154">数字</span><span class="sxs-lookup"><span data-stu-id="ae7f5-154">Number</span></span>    | <span data-ttu-id="ae7f5-155">26</span><span class="sxs-lookup"><span data-stu-id="ae7f5-155">26</span></span>                        | <span data-ttu-id="ae7f5-156">必需</span><span class="sxs-lookup"><span data-stu-id="ae7f5-156">Required</span></span>              |
  | <span data-ttu-id="ae7f5-157">BuildingName</span><span class="sxs-lookup"><span data-stu-id="ae7f5-157">BuildingName</span></span>       | <span data-ttu-id="ae7f5-158">String</span><span class="sxs-lookup"><span data-stu-id="ae7f5-158">String</span></span>    | <span data-ttu-id="ae7f5-159">SEATTLE-SEA-1</span><span class="sxs-lookup"><span data-stu-id="ae7f5-159">SEATTLE-SEA-1</span></span>             | <span data-ttu-id="ae7f5-160">必需<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="ae7f5-160">Required<sup>1</sup></span></span>  |
  | <span data-ttu-id="ae7f5-161">OwnershipType</span><span class="sxs-lookup"><span data-stu-id="ae7f5-161">OwnershipType</span></span>      | <span data-ttu-id="ae7f5-162">String</span><span class="sxs-lookup"><span data-stu-id="ae7f5-162">String</span></span>    | <span data-ttu-id="ae7f5-163">Contoso</span><span class="sxs-lookup"><span data-stu-id="ae7f5-163">Contoso</span></span>                   | <span data-ttu-id="ae7f5-164">可选</span><span class="sxs-lookup"><span data-stu-id="ae7f5-164">Optional</span></span>              |
  | <span data-ttu-id="ae7f5-165">BuildingType</span><span class="sxs-lookup"><span data-stu-id="ae7f5-165">BuildingType</span></span>       | <span data-ttu-id="ae7f5-166">String</span><span class="sxs-lookup"><span data-stu-id="ae7f5-166">String</span></span>    | <span data-ttu-id="ae7f5-167">IT 终止</span><span class="sxs-lookup"><span data-stu-id="ae7f5-167">IT Termination</span></span>            | <span data-ttu-id="ae7f5-168">可选</span><span class="sxs-lookup"><span data-stu-id="ae7f5-168">Optional</span></span>              |
  | <span data-ttu-id="ae7f5-169">BuildingOfficeType</span><span class="sxs-lookup"><span data-stu-id="ae7f5-169">BuildingOfficeType</span></span> | <span data-ttu-id="ae7f5-170">String</span><span class="sxs-lookup"><span data-stu-id="ae7f5-170">String</span></span>    | <span data-ttu-id="ae7f5-171">工程</span><span class="sxs-lookup"><span data-stu-id="ae7f5-171">Engineering</span></span>               | <span data-ttu-id="ae7f5-172">可选</span><span class="sxs-lookup"><span data-stu-id="ae7f5-172">Optional</span></span>              |
  | <span data-ttu-id="ae7f5-173">城市</span><span class="sxs-lookup"><span data-stu-id="ae7f5-173">City</span></span>               | <span data-ttu-id="ae7f5-174">String</span><span class="sxs-lookup"><span data-stu-id="ae7f5-174">String</span></span>    | <span data-ttu-id="ae7f5-175">西雅图</span><span class="sxs-lookup"><span data-stu-id="ae7f5-175">Seattle</span></span>                   | <span data-ttu-id="ae7f5-176">推荐</span><span class="sxs-lookup"><span data-stu-id="ae7f5-176">Recommended</span></span>           |
  | <span data-ttu-id="ae7f5-177">ZipCode</span><span class="sxs-lookup"><span data-stu-id="ae7f5-177">ZipCode</span></span>            | <span data-ttu-id="ae7f5-178">String</span><span class="sxs-lookup"><span data-stu-id="ae7f5-178">String</span></span>    | <span data-ttu-id="ae7f5-179">98001</span><span class="sxs-lookup"><span data-stu-id="ae7f5-179">98001</span></span>                     | <span data-ttu-id="ae7f5-180">推荐</span><span class="sxs-lookup"><span data-stu-id="ae7f5-180">Recommended</span></span>           |
  | <span data-ttu-id="ae7f5-181">国家/地区</span><span class="sxs-lookup"><span data-stu-id="ae7f5-181">Country</span></span>            | <span data-ttu-id="ae7f5-182">String</span><span class="sxs-lookup"><span data-stu-id="ae7f5-182">String</span></span>    | <span data-ttu-id="ae7f5-183">美国</span><span class="sxs-lookup"><span data-stu-id="ae7f5-183">US</span></span>                        | <span data-ttu-id="ae7f5-184">推荐</span><span class="sxs-lookup"><span data-stu-id="ae7f5-184">Recommended</span></span>           |
  | <span data-ttu-id="ae7f5-185">省/市/自治区</span><span class="sxs-lookup"><span data-stu-id="ae7f5-185">State</span></span>              | <span data-ttu-id="ae7f5-186">String</span><span class="sxs-lookup"><span data-stu-id="ae7f5-186">String</span></span>    | <span data-ttu-id="ae7f5-187">WA</span><span class="sxs-lookup"><span data-stu-id="ae7f5-187">WA</span></span>                        | <span data-ttu-id="ae7f5-188">推荐</span><span class="sxs-lookup"><span data-stu-id="ae7f5-188">Recommended</span></span>           |
  | <span data-ttu-id="ae7f5-189">区域</span><span class="sxs-lookup"><span data-stu-id="ae7f5-189">Region</span></span>             | <span data-ttu-id="ae7f5-190">String</span><span class="sxs-lookup"><span data-stu-id="ae7f5-190">String</span></span>    | <span data-ttu-id="ae7f5-191">MSUS</span><span class="sxs-lookup"><span data-stu-id="ae7f5-191">MSUS</span></span>                      | <span data-ttu-id="ae7f5-192">推荐</span><span class="sxs-lookup"><span data-stu-id="ae7f5-192">Recommended</span></span>           |
  | <span data-ttu-id="ae7f5-193">InsideCorp<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="ae7f5-193">InsideCorp<sup>2</sup></span></span>         | <span data-ttu-id="ae7f5-194">Bool</span><span class="sxs-lookup"><span data-stu-id="ae7f5-194">Bool</span></span>      | <span data-ttu-id="ae7f5-195">1</span><span class="sxs-lookup"><span data-stu-id="ae7f5-195">1</span></span>             | <span data-ttu-id="ae7f5-196">必需</span><span class="sxs-lookup"><span data-stu-id="ae7f5-196">Required</span></span>              |
  | <span data-ttu-id="ae7f5-197">ExpressRoute<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="ae7f5-197">ExpressRoute<sup>3</sup></span></span>       | <span data-ttu-id="ae7f5-198">Bool</span><span class="sxs-lookup"><span data-stu-id="ae7f5-198">Bool</span></span>      | <span data-ttu-id="ae7f5-199">0</span><span class="sxs-lookup"><span data-stu-id="ae7f5-199">0</span></span>             | <span data-ttu-id="ae7f5-200">必需</span><span class="sxs-lookup"><span data-stu-id="ae7f5-200">Required</span></span>              |
  | <span data-ttu-id="ae7f5-201">VPN</span><span class="sxs-lookup"><span data-stu-id="ae7f5-201">VPN</span></span>                | <span data-ttu-id="ae7f5-202">Bool</span><span class="sxs-lookup"><span data-stu-id="ae7f5-202">Bool</span></span>      | <span data-ttu-id="ae7f5-203">0</span><span class="sxs-lookup"><span data-stu-id="ae7f5-203">0</span></span>                         | <span data-ttu-id="ae7f5-204">可选</span><span class="sxs-lookup"><span data-stu-id="ae7f5-204">Optional</span></span>              |

  <span data-ttu-id="ae7f5-205"><sup>1</sup> CQD 不需要，但模板配置为显示建筑物和网络名称。</span><span class="sxs-lookup"><span data-stu-id="ae7f5-205"><sup>1</sup> While not required by CQD, the templates are configured to display Building and Network name.</span></span>

  <span data-ttu-id="ae7f5-206"><sup>2</sup> 此设置可用于反映子网是否在企业网络中。</span><span class="sxs-lookup"><span data-stu-id="ae7f5-206"><sup>2</sup> This setting can be used to reflect whether or not the subnet is inside the corporate network.</span></span> <span data-ttu-id="ae7f5-207">可以自定义其他用途。</span><span class="sxs-lookup"><span data-stu-id="ae7f5-207">You can customize usage for other purposes.</span></span>

  <span data-ttu-id="ae7f5-208"><sup>3</sup> 此设置可用于反映网络是否使用 Azure ExpressRoute。</span><span class="sxs-lookup"><span data-stu-id="ae7f5-208"><sup>3</sup> This setting can be used to reflect whether or not the network uses Azure ExpressRoute.</span></span> <span data-ttu-id="ae7f5-209">可以自定义其他用途。</span><span class="sxs-lookup"><span data-stu-id="ae7f5-209">You can customize usage for other purposes.</span></span>  

  <span data-ttu-id="ae7f5-210">**示例行：**</span><span class="sxs-lookup"><span data-stu-id="ae7f5-210">**Sample row:**</span></span>

  `192.168.1.0,USA/Seattle/SEATTLE-SEA-1,26,SEATTLE-SEA-1,Contoso,IT Termination,Engineering,Seattle,98001,US,WA,MSUS,1,0,0`

> [!IMPORTANT]
> <span data-ttu-id="ae7f5-211">网络范围可用于表示具有单个路由前缀 (多个子网的超网络) 。</span><span class="sxs-lookup"><span data-stu-id="ae7f5-211">The network range can be used to represent a supernet (combination of several subnets with a single routing prefix).</span></span> <span data-ttu-id="ae7f5-212">所有新建筑物上载都将检查是否有重叠范围。</span><span class="sxs-lookup"><span data-stu-id="ae7f5-212">All new building uploads will be checked for any overlapping ranges.</span></span> <span data-ttu-id="ae7f5-213">如果以前上传过一个建筑物文件，应下载当前文件，然后重新上传该文件，以识别任何重叠，并修复问题，然后再再次上载。</span><span class="sxs-lookup"><span data-stu-id="ae7f5-213">If you have previously uploaded a building file, you should download the current file and re-upload it to identify any overlaps and fix the issue before uploading again.</span></span> <span data-ttu-id="ae7f5-214">以前上传的文件的任何重叠都可能导致错误地将子网映射到报告中的建筑物。</span><span class="sxs-lookup"><span data-stu-id="ae7f5-214">Any overlap in previously uploaded files may result in the wrong mappings of subnets to buildings in the reports.</span></span> <span data-ttu-id="ae7f5-215">某些 VPN 实现无法准确报告子网信息。</span><span class="sxs-lookup"><span data-stu-id="ae7f5-215">Certain VPN implementations do not accurately report the subnet information.</span></span> 
>
> <span data-ttu-id="ae7f5-216">VPN 列是可选的，默认为 0。</span><span class="sxs-lookup"><span data-stu-id="ae7f5-216">The VPN column is optional and will default to 0.</span></span> <span data-ttu-id="ae7f5-217">如果 VPN 列的值设置为 1，则该行表示的子网将完全展开，以匹配子网内的所有 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="ae7f5-217">If the VPN column’s value is set to 1, the subnet represented by that row will be fully expanded to match all IP addresses within the subnet.</span></span>  <span data-ttu-id="ae7f5-218">请尽量少用，并且只能用于 VPN 子网，因为完全扩展这些子网会对涉及生成数据的查询的查询时间产生负面影响。</span><span class="sxs-lookup"><span data-stu-id="ae7f5-218">Please use this sparingly and only for VPN subnets since fully expanding these subnets will have a negative impact on query times for queries involving building data.</span></span>


### <a name="supernetting"></a><span data-ttu-id="ae7f5-219">超网</span><span class="sxs-lookup"><span data-stu-id="ae7f5-219">Supernetting</span></span>

<span data-ttu-id="ae7f5-220">可以使用超级网络（通常称为无Inter-Domain路由 (CIDR) 来取代定义每个子网。</span><span class="sxs-lookup"><span data-stu-id="ae7f5-220">You can use supernetting, commonly called Classless Inter-Domain Routing (CIDR,) in place of defining each subnet.</span></span> <span data-ttu-id="ae7f5-221">超 *网络* 是共享单个路由前缀的几个子网的组合。</span><span class="sxs-lookup"><span data-stu-id="ae7f5-221">A *supernet* is a combination of several subnets that share a single routing prefix.</span></span> <span data-ttu-id="ae7f5-222">可以使用超网地址，而不是添加每个子网的条目。</span><span class="sxs-lookup"><span data-stu-id="ae7f5-222">Instead of adding an entry for each subnet, you can use the supernetted address.</span></span> <span data-ttu-id="ae7f5-223">支持超网，但我们不建议使用它。</span><span class="sxs-lookup"><span data-stu-id="ae7f5-223">Supernetting is supported, but we don't recommend using it.</span></span>

<span data-ttu-id="ae7f5-224">例如，Contoso 的营销大楼由以下子网决定：</span><span class="sxs-lookup"><span data-stu-id="ae7f5-224">For example, Contoso's marketing building is made up of the subnets below:</span></span>

-   <span data-ttu-id="ae7f5-225">10.1.0.0/24 — 一楼</span><span class="sxs-lookup"><span data-stu-id="ae7f5-225">10.1.0.0/24—first floor</span></span>
-   <span data-ttu-id="ae7f5-226">10.1.1.0/24 — 二楼</span><span class="sxs-lookup"><span data-stu-id="ae7f5-226">10.1.1.0/24—second floor</span></span>
-   <span data-ttu-id="ae7f5-227">10.1.2.0/24 — 三楼</span><span class="sxs-lookup"><span data-stu-id="ae7f5-227">10.1.2.0/24—third floor</span></span>
-   <span data-ttu-id="ae7f5-228">10.1.3.0/24 — 第四层</span><span class="sxs-lookup"><span data-stu-id="ae7f5-228">10.1.3.0/24—fourth floor</span></span>

<span data-ttu-id="ae7f5-229">可以使用上网地址（本示例中为 10.1.0.0/22）而不是添加每个子网的条目。</span><span class="sxs-lookup"><span data-stu-id="ae7f5-229">Instead of adding an entry for each subnet, you can use the supernetted address—in this example, 10.1.0.0/22.</span></span>

-   <span data-ttu-id="ae7f5-230">网络 = 10.1.0.0</span><span class="sxs-lookup"><span data-stu-id="ae7f5-230">Network = 10.1.0.0</span></span>
-   <span data-ttu-id="ae7f5-231">网络范围 = 22</span><span class="sxs-lookup"><span data-stu-id="ae7f5-231">Network Range = 22</span></span>

<span data-ttu-id="ae7f5-232">实现超网之前，需要考虑以下一些操作：</span><span class="sxs-lookup"><span data-stu-id="ae7f5-232">Here are a few things to consider before you implement supernetting:</span></span>

-   <span data-ttu-id="ae7f5-233">超网只能在具有 8 位到 28 位掩码的子网映射中使用。</span><span class="sxs-lookup"><span data-stu-id="ae7f5-233">Supernetting can only be used in a subnet mapping with 8-bit to 28-bit mask.</span></span>

-   <span data-ttu-id="ae7f5-234">超网需要更少的前置时间，但代价是降低数据的丰富性。</span><span class="sxs-lookup"><span data-stu-id="ae7f5-234">Supernetting takes less time up front, but it comes at the cost of reducing the richness of your data.</span></span> <span data-ttu-id="ae7f5-235">假设存在涉及子网 10.1.2.0 的质量问题。</span><span class="sxs-lookup"><span data-stu-id="ae7f5-235">Let's say there's a quality problem involving subnet 10.1.2.0.</span></span> <span data-ttu-id="ae7f5-236">如果实现了超网，则不知道子网在建筑物中的什么位置，或者它 (类型的网络，例如实验室) 。</span><span class="sxs-lookup"><span data-stu-id="ae7f5-236">If you implemented supernetting, you won't know where in the building the subnet is located or what type of network it is (for example, a lab).</span></span> <span data-ttu-id="ae7f5-237">如果已定义建筑物的所有子网和上载的楼层位置信息，则可以看到这种区别。</span><span class="sxs-lookup"><span data-stu-id="ae7f5-237">If you'd defined all the subnets for a building and uploaded floor location information, you'd be able to see that distinction.</span></span>

-   <span data-ttu-id="ae7f5-238">确保超网地址正确且不会捕获不需要的子网，这一点很重要。</span><span class="sxs-lookup"><span data-stu-id="ae7f5-238">It's important to ensure that the supernetted address is correct and isn't catching unwanted subnets.</span></span>

-   <span data-ttu-id="ae7f5-239">在数据中查找 192.168.0.0 很常见。</span><span class="sxs-lookup"><span data-stu-id="ae7f5-239">It's quite common to find 192.168.0.0 in data.</span></span> <span data-ttu-id="ae7f5-240">对于许多组织，这表示用户在家中。</span><span class="sxs-lookup"><span data-stu-id="ae7f5-240">For many organizations, this indicates that the user is at home.</span></span> <span data-ttu-id="ae7f5-241">对于其他人，这是卫星办公室的 IP 地址方案。</span><span class="sxs-lookup"><span data-stu-id="ae7f5-241">For others, this is the IP address scheme for a satellite office.</span></span> <span data-ttu-id="ae7f5-242">如果组织有使用此配置办公室，请不要将其包括在建筑物文件中，因为使用公共子网很难区分家庭网络和内部 [网络](quality-of-experience-review-guide.md#common-subnets)。</span><span class="sxs-lookup"><span data-stu-id="ae7f5-242">If your organization does have offices that use this configuration, don't include it in your building file because it's difficult to distinguish between home and internal networks by using [common subnets](quality-of-experience-review-guide.md#common-subnets).</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="ae7f5-243">网络范围可用于表示超网络。</span><span class="sxs-lookup"><span data-stu-id="ae7f5-243">The network range can be used to represent a supernet.</span></span> <span data-ttu-id="ae7f5-244">所有新的建筑物数据文件上传都会检查是否有重叠的范围。</span><span class="sxs-lookup"><span data-stu-id="ae7f5-244">All new building data file uploads will be checked for any overlapping ranges.</span></span> <span data-ttu-id="ae7f5-245">如果以前上传过一个建筑物文件，应下载当前文件并再次上传该文件，以识别任何重叠并修复问题。</span><span class="sxs-lookup"><span data-stu-id="ae7f5-245">If you've previously uploaded a building file, you should download the current file and upload it again to identify any overlaps and fix the issue.</span></span> <span data-ttu-id="ae7f5-246">以前上传的文件的任何重叠都可能导致错误地将子网映射到报告中的建筑物。</span><span class="sxs-lookup"><span data-stu-id="ae7f5-246">Any overlap in previously uploaded files might result in the wrong mappings of subnets to buildings in the reports.</span></span>

### <a name="vpn"></a><span data-ttu-id="ae7f5-247">VPN</span><span class="sxs-lookup"><span data-stu-id="ae7f5-247">VPN</span></span>

<span data-ttu-id="ae7f5-248">客户端发送到 Microsoft 365 (Office 365（CQD 数据的来源）的 QoE) 用户体验质量包括 VPN 标志。</span><span class="sxs-lookup"><span data-stu-id="ae7f5-248">The quality of experience (QoE) data that clients send to Microsoft 365 or Office 365—which is where CQD data is sourced from—includes a VPN flag.</span></span> <span data-ttu-id="ae7f5-249">CQD 将看到此为第一个 VPN 维度和第二个 VPN 维度。</span><span class="sxs-lookup"><span data-stu-id="ae7f5-249">CQD will see this as the First VPN and Second VPN dimensions.</span></span> <span data-ttu-id="ae7f5-250">但是，此标志依赖于 VPN 供应商向 Windows 报告已注册的 VPN 网络适配器是远程访问适配器。</span><span class="sxs-lookup"><span data-stu-id="ae7f5-250">However, this flag relies on VPN vendors' reporting to Windows that the VPN network adapter registered is a Remote Access adapter.</span></span> <span data-ttu-id="ae7f5-251">并非所有 VPN 供应商都正确注册远程访问适配器。</span><span class="sxs-lookup"><span data-stu-id="ae7f5-251">Not all VPN vendors properly register Remote Access adapters.</span></span> <span data-ttu-id="ae7f5-252">因此，可能无法使用内置的 VPN 查询筛选器。</span><span class="sxs-lookup"><span data-stu-id="ae7f5-252">Because of this, you might not be able to use the built-in VPN query filters.</span></span> <span data-ttu-id="ae7f5-253">使用上面讨论的 VPN 列准确标记和标识 VPN 子网。</span><span class="sxs-lookup"><span data-stu-id="ae7f5-253">Use the VPN column discussed above to accurately mark and identify VPN subnets.</span></span> <span data-ttu-id="ae7f5-254">另外，为 VPN 网络添加标签也是一种很好的做法，便于在报告中识别。</span><span class="sxs-lookup"><span data-stu-id="ae7f5-254">It is also good practice to label your VPN networks for easy identification in your reports.</span></span> <span data-ttu-id="ae7f5-255">下面是两个如何标记 VPN 子网的示例：</span><span class="sxs-lookup"><span data-stu-id="ae7f5-255">Below are two examples of how to label your VPN subnets:</span></span>

- <span data-ttu-id="ae7f5-256">通过在此 **字段中为** VPN 子网输入"VPN"来定义网络名称。</span><span class="sxs-lookup"><span data-stu-id="ae7f5-256">Define a **Network Name** by entering "VPN" in this field for VPN subnets.</span></span>

  ![显示使用网络名称的 VPN 的 QCD 报告屏幕截图](media/qerguide-image-vpnnetworkname.png)

- <span data-ttu-id="ae7f5-258">通过在此 **字段中为** VPN 子网输入"VPN"来定义建筑物名称。</span><span class="sxs-lookup"><span data-stu-id="ae7f5-258">Define a **Building Name** by entering "VPN" in this field for VPN subnets.</span></span>

  ![显示使用建筑物名称的 VPN 的 QCD 报告屏幕截图](media/qerguide-image-vpnbuildingname.png)

> [!NOTE]
> <span data-ttu-id="ae7f5-260">已知 VPN 连接在基础连接为无线时将网络连接类型错误识别为有线。</span><span class="sxs-lookup"><span data-stu-id="ae7f5-260">VPN connections have been known to misidentify the network connection type as wired when the underlying connection is wireless.</span></span> <span data-ttu-id="ae7f5-261">通过 VPN 连接查看质量时，无法假定连接类型已准确识别。</span><span class="sxs-lookup"><span data-stu-id="ae7f5-261">When looking at quality over VPN connections, you can't assume that the connection type has been accurately identified.</span></span>

## <a name="endpoint-data-file"></a><span data-ttu-id="ae7f5-262">终结点数据文件</span><span class="sxs-lookup"><span data-stu-id="ae7f5-262">Endpoint data file</span></span>

<span data-ttu-id="ae7f5-263">另一种类型的 CQD 租户数据文件是 **终结点** 数据文件。</span><span class="sxs-lookup"><span data-stu-id="ae7f5-263">The other type of CQD tenant data file is the **Endpoint** data file.</span></span> <span data-ttu-id="ae7f5-264">列值用于调用记录的"第一个客户端终结点名称"或"第二个客户端终结点名称"列，以显示终结点制造、模型或类型信息。</span><span class="sxs-lookup"><span data-stu-id="ae7f5-264">The column values are used in the call record’s First Client Endpoint Name or Second Client Endpoint Name column to show Endpoint Make, Model, or Type information.</span></span> <span data-ttu-id="ae7f5-265">上传的数据文件的格式必须满足以下条件，才能在上传前通过验证检查：</span><span class="sxs-lookup"><span data-stu-id="ae7f5-265">The format of the data file you upload must meet the following criteria to pass the validation check before upload:</span></span>

- <span data-ttu-id="ae7f5-266">该文件必须是 .tsv 文件， (制表符分隔列) 或 .csv 文件 (以逗号分隔) 。</span><span class="sxs-lookup"><span data-stu-id="ae7f5-266">The file must be either a .tsv file (columns are separated by a TAB) or a .csv file (columns are separated by a comma).</span></span>

- <span data-ttu-id="ae7f5-267">数据文件的内容不包括表标题。</span><span class="sxs-lookup"><span data-stu-id="ae7f5-267">The content of the data file doesn't include table headers.</span></span> <span data-ttu-id="ae7f5-268">数据文件的第一行应该是实际数据，而不是"EndpointName"等标头标签。</span><span class="sxs-lookup"><span data-stu-id="ae7f5-268">The first line of the data file is expected to be real data, not a header label like "EndpointName".</span></span>

- <span data-ttu-id="ae7f5-269">所有七列都使用字符串数据类型字符串。</span><span class="sxs-lookup"><span data-stu-id="ae7f5-269">All seven columns use the String data type only.</span></span> <span data-ttu-id="ae7f5-270">允许的最大长度为 64 个字符。</span><span class="sxs-lookup"><span data-stu-id="ae7f5-270">The maximum allowed length is 64 characters.</span></span>

- <span data-ttu-id="ae7f5-271">数据字段可以为空，但仍必须以制表符或逗号分隔。</span><span class="sxs-lookup"><span data-stu-id="ae7f5-271">A data field can be empty but must still be separated by a tab or comma.</span></span> <span data-ttu-id="ae7f5-272">空数据字段只分配空字符串值。</span><span class="sxs-lookup"><span data-stu-id="ae7f5-272">An empty data field just assigns an empty String value.</span></span>

- <span data-ttu-id="ae7f5-273">EndpointName 必须唯一，否则上传失败。</span><span class="sxs-lookup"><span data-stu-id="ae7f5-273">EndpointName must be unique, otherwise the upload fails.</span></span> <span data-ttu-id="ae7f5-274">如果有重复的一行或两行使用同一 EndpointName，则冲突将导致联接错误。</span><span class="sxs-lookup"><span data-stu-id="ae7f5-274">If there is a duplicate row or two rows that use the same EndpointName the conflict will  cause incorrect joining.</span></span>

- <span data-ttu-id="ae7f5-275">EndpointLabel1、EndpointLabel2 和 EndpointLabel3 是可自定义的标签。</span><span class="sxs-lookup"><span data-stu-id="ae7f5-275">EndpointLabel1, EndpointLabel2, and EndpointLabel3 are customizable labels.</span></span> <span data-ttu-id="ae7f5-276">它们可以是空字符串或值，例如"IT 部门指定的 2018 笔记本电脑"或"资产标记 5678"。</span><span class="sxs-lookup"><span data-stu-id="ae7f5-276">They can be empty Strings or values such as “IT Department designated 2018 Laptop” or “Asset Tag 5678”.</span></span>

- <span data-ttu-id="ae7f5-277">每行必须包含七列，列必须按以下顺序排列：</span><span class="sxs-lookup"><span data-stu-id="ae7f5-277">There must be seven columns for each row and the columns must be in the following order:</span></span>

  <span data-ttu-id="ae7f5-278">**域顺序：**</span><span class="sxs-lookup"><span data-stu-id="ae7f5-278">**Field order:**</span></span>

  <span data-ttu-id="ae7f5-279">EndpointName、EndpointMake、EndpointModel、EndpointType、EndpointLabel1、EndpointLabel2、EndpointLabel3</span><span class="sxs-lookup"><span data-stu-id="ae7f5-279">EndpointName, EndpointMake, EndpointModel, EndpointType, EndpointLabel1, EndpointLabel2,  EndpointLabel3</span></span>

  <span data-ttu-id="ae7f5-280">**示例行：**</span><span class="sxs-lookup"><span data-stu-id="ae7f5-280">**Sample row:**</span></span>

  `1409W3534, Fabrikam, Model 123, Laptop, IT designated 2018 Laptop, Asset Tag 5678, Purchase 2018`

## <a name="update-a-building-file"></a><span data-ttu-id="ae7f5-281">更新建筑物文件</span><span class="sxs-lookup"><span data-stu-id="ae7f5-281">Update a building file</span></span>

<span data-ttu-id="ae7f5-282">收集建筑物和子网信息时，管理员通常会在一段时间的多次迭代中上传建筑物文件，并添加新子网及其建筑物信息（可用时）。</span><span class="sxs-lookup"><span data-stu-id="ae7f5-282">While gathering building and subnet information, administrators will often upload the building file in multiple iterations over time, adding new subnets and their building information as it becomes available.</span></span> <span data-ttu-id="ae7f5-283">发生这种情况时，需要重新上传建筑物文件。</span><span class="sxs-lookup"><span data-stu-id="ae7f5-283">When this occurs, you'll need to re-upload your building file.</span></span> <span data-ttu-id="ae7f5-284">此过程与上一部分中所述的初始上传类似，但以下部分介绍了一些例外。</span><span class="sxs-lookup"><span data-stu-id="ae7f5-284">This process is like the initial upload as described in the previous section, with a few exceptions as noted in the following section.</span></span>

> [!Important]
> <span data-ttu-id="ae7f5-285">一次只能有一个建筑物文件处于活动状态。</span><span class="sxs-lookup"><span data-stu-id="ae7f5-285">Only one building file can be active at a time.</span></span> <span data-ttu-id="ae7f5-286">多个建筑物文件不是累积的。</span><span class="sxs-lookup"><span data-stu-id="ae7f5-286">Multiple building files aren't cumulative.</span></span>

## <a name="add-net-new-subnets"></a><span data-ttu-id="ae7f5-287">添加新子网</span><span class="sxs-lookup"><span data-stu-id="ae7f5-287">Add net new subnets</span></span>

<span data-ttu-id="ae7f5-288">有时，需要向 CQD 添加最初不是网络拓扑一部分的新子网。</span><span class="sxs-lookup"><span data-stu-id="ae7f5-288">There are times when you'll need to add net new subnets to CQD that weren't originally part of your network topology.</span></span> <span data-ttu-id="ae7f5-289">若要添加新子网，请从 CQD 中的"租户数据上传"页执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="ae7f5-289">To add net new subnets, do the following from the **Tenant Data Upload** page in CQD:</span></span>

1.  <span data-ttu-id="ae7f5-290">下载原始文件（如果还没有最新副本）。</span><span class="sxs-lookup"><span data-stu-id="ae7f5-290">Download the original file, if you don't already have an up-to-date copy.</span></span>

1.  <span data-ttu-id="ae7f5-291">删除 CQD 中的当前文件。</span><span class="sxs-lookup"><span data-stu-id="ae7f5-291">Remove the current file in CQD.</span></span>

1.  <span data-ttu-id="ae7f5-292">编辑原始建筑物文件，并提供在获取网络新子网前至少一天的结束日期。</span><span class="sxs-lookup"><span data-stu-id="ae7f5-292">Edit the original building file and provide an end date that occurs at least one day before the net new subnets were acquired.</span></span>

1.  <span data-ttu-id="ae7f5-293">将网络新子网追加到原始建筑物文件。</span><span class="sxs-lookup"><span data-stu-id="ae7f5-293">Append the net new subnets to the original building file.</span></span>

1.  <span data-ttu-id="ae7f5-294">上传新修改的建筑物文件，将开始日期设置为前一个建筑物文件结束后的一天。</span><span class="sxs-lookup"><span data-stu-id="ae7f5-294">Upload the newly modified building file, and set the start date for one day after the previous building file ends.</span></span>

## <a name="add-missing-subnets"></a><span data-ttu-id="ae7f5-295">添加缺少的子网</span><span class="sxs-lookup"><span data-stu-id="ae7f5-295">Add missing subnets</span></span>

<span data-ttu-id="ae7f5-296">上传托管网络的建筑物信息后，每个托管网络都应具有建筑物关联。</span><span class="sxs-lookup"><span data-stu-id="ae7f5-296">After you upload building information for managed networks, every managed network should have a building association.</span></span> <span data-ttu-id="ae7f5-297">但是，情况并非总是如此;通常会遗漏几个子网。</span><span class="sxs-lookup"><span data-stu-id="ae7f5-297">However, this won't always be the case; typically, a few subnets are missed.</span></span> <span data-ttu-id="ae7f5-298">若要查找这些缺失的网络，请查看CQD 中"体验质量报告 **"页上的**"缺少子网报告"。</span><span class="sxs-lookup"><span data-stu-id="ae7f5-298">To find these missing networks, review the **Missing Subnet Report** on the **Quality of Experience Reports** page in CQD.</span></span> <span data-ttu-id="ae7f5-299">这会向所有子网显示 10 个或多个音频流，这些音频流未在建筑物数据文件中定义，并且被标记为外部。</span><span class="sxs-lookup"><span data-stu-id="ae7f5-299">This presents all the subnets with 10 or more audio streams that aren't defined in the building data file and are being marked as outside.</span></span> <span data-ttu-id="ae7f5-300">请确保此列表中没有托管网络。</span><span class="sxs-lookup"><span data-stu-id="ae7f5-300">Ensure that there are no managed networks in this list.</span></span> <span data-ttu-id="ae7f5-301">如果缺少子网，请使用以下过程更新原始建筑物数据文件，并将其重新上传到 CQD。</span><span class="sxs-lookup"><span data-stu-id="ae7f5-301">If subnets are missing, use the following procedure to update the original building data file and re-upload it to CQD.</span></span>

1. <span data-ttu-id="ae7f5-302">转到 CQD **中的** "租户数据上传"页。</span><span class="sxs-lookup"><span data-stu-id="ae7f5-302">Go to the **Tenant Data Upload** page in CQD.</span></span>

1. <span data-ttu-id="ae7f5-303">下载原始文件（如果还没有最新副本）。</span><span class="sxs-lookup"><span data-stu-id="ae7f5-303">Download the original file, if you don't already have an up-to-date copy.</span></span>

1. <span data-ttu-id="ae7f5-304">删除 CQD 中的当前文件。</span><span class="sxs-lookup"><span data-stu-id="ae7f5-304">Remove the current file in CQD.</span></span>

1. <span data-ttu-id="ae7f5-305">将新子网追加到原始文件。</span><span class="sxs-lookup"><span data-stu-id="ae7f5-305">Append the new subnets to the original file.</span></span>

1. <span data-ttu-id="ae7f5-306">上传建筑物文件。</span><span class="sxs-lookup"><span data-stu-id="ae7f5-306">Upload the building file.</span></span> <span data-ttu-id="ae7f5-307">请确保将开始日期设置为至少八个月之前，以便 CQD 将处理历史数据。</span><span class="sxs-lookup"><span data-stu-id="ae7f5-307">Be sure to set the start date to at least eight months prior so that CQD will process historical data.</span></span>


> [!IMPORTANT]
> <span data-ttu-id="ae7f5-308">需要将租户 ID 作为第二租户 **ID** 的查询筛选器添加到此报表，以便筛选报表，以便仅查看组织的租户数据。</span><span class="sxs-lookup"><span data-stu-id="ae7f5-308">You'll need to add your tenant ID as a query filter for **Second Tenant ID** to this report to filter the report to view only your organization's tenant data.</span></span> <span data-ttu-id="ae7f5-309">否则，报告会显示联合子网。</span><span class="sxs-lookup"><span data-stu-id="ae7f5-309">Otherwise, the report will show federated subnets.</span></span>

> [!NOTE] 
> <span data-ttu-id="ae7f5-310">请务必将"月份年份"报表筛选器调整为当前月份。</span><span class="sxs-lookup"><span data-stu-id="ae7f5-310">Be sure to adjust the Month Year report filter to the current month.</span></span> <span data-ttu-id="ae7f5-311">选择 **"** 编辑"，然后调整 **"月份年份** "报表筛选器以保存新的默认月份。</span><span class="sxs-lookup"><span data-stu-id="ae7f5-311">Select **Edit**, and adjust the **Month Year** report filter to save the new default month.</span></span>


## <a name="related-topics"></a><span data-ttu-id="ae7f5-312">相关主题</span><span class="sxs-lookup"><span data-stu-id="ae7f5-312">Related topics</span></span>

[<span data-ttu-id="ae7f5-313">为 CQD 创建建筑物地图</span><span class="sxs-lookup"><span data-stu-id="ae7f5-313">Create a building map for CQD</span></span>](CQD-building-mapping.md)

[<span data-ttu-id="ae7f5-314">改进和监视 Teams 的通话质量</span><span class="sxs-lookup"><span data-stu-id="ae7f5-314">Improve and monitor call quality for Teams</span></span>](monitor-call-quality-qos.md)

[<span data-ttu-id="ae7f5-315">什么是 CQD？</span><span class="sxs-lookup"><span data-stu-id="ae7f5-315">What is CQD?</span></span>](CQD-what-is-call-quality-dashboard.md)

[<span data-ttu-id="ae7f5-316">设置呼叫质量仪表板 (CQD) </span><span class="sxs-lookup"><span data-stu-id="ae7f5-316">Set up Call Quality Dashboard (CQD)</span></span>](turning-on-and-using-call-quality-dashboard.md)

[<span data-ttu-id="ae7f5-317">CQD 数据和报表</span><span class="sxs-lookup"><span data-stu-id="ae7f5-317">CQD data and reports</span></span>](CQD-data-and-reports.md)

[<span data-ttu-id="ae7f5-318">使用 CQD 管理呼叫和会议质量</span><span class="sxs-lookup"><span data-stu-id="ae7f5-318">Use CQD to manage call and meeting quality</span></span>](quality-of-experience-review-guide.md)

[<span data-ttu-id="ae7f5-319">CQD 中可用的维度和度量值</span><span class="sxs-lookup"><span data-stu-id="ae7f5-319">Dimensions and measures available in CQD</span></span>](dimensions-and-measures-available-in-call-quality-dashboard.md)

[<span data-ttu-id="ae7f5-320">CQD 中的流分类</span><span class="sxs-lookup"><span data-stu-id="ae7f5-320">Stream Classification in CQD</span></span>](stream-classification-in-call-quality-dashboard.md)

[<span data-ttu-id="ae7f5-321">使用 Power BI 分析 CQD 数据</span><span class="sxs-lookup"><span data-stu-id="ae7f5-321">Use Power BI to analyze CQD data</span></span>](CQD-Power-BI-query-templates.md)
