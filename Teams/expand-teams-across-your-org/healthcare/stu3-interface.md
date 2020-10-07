---
title: 患者应用和 EHR 集成 STU3 界面
author: dstrome
ms.author: dstrome
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
search.appverid: MET150
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Healthcare
appliesto:
- Microsoft Teams
ms.reviewer: anach
description: 了解如何将电子医疗记录集成到 Microsoft 团队患者应用和 STU3 界面规范中。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 177d8d9bb1a05e7fc871b8c11771708099347914
ms.sourcegitcommit: f4f5ad1391b472d64390180c81c2680f011a8a10
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2020
ms.locfileid: "48367642"
---
# <a name="stu3-interface-specification"></a><span data-ttu-id="dde47-103">STU3 接口规范</span><span class="sxs-lookup"><span data-stu-id="dde47-103">STU3 interface specification</span></span>

> [!IMPORTANT]
> <span data-ttu-id="dde47-104">**2020年10月30日生效，患者应用将被否决，用户将无法再从团队应用商店安装。我们鼓励你立即开始使用团队中的 " [列表" 应用](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) 。**</span><span class="sxs-lookup"><span data-stu-id="dde47-104">**Effective October 30, 2020, the Patients app will be deprecated and users will no longer be able to install it from the Teams app store. We encourage you to start using the [Lists app](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) in Teams today.**</span></span>
>
><span data-ttu-id="dde47-105">患者应用数据存储在支持团队的 Office 365 组的组邮箱中。</span><span class="sxs-lookup"><span data-stu-id="dde47-105">Patients app data is stored in the group mailbox of the Office 365 group that backs the team.</span></span> <span data-ttu-id="dde47-106">当患者应用停用时，与之关联的所有数据将保留在此组中，但不能再通过用户界面进行访问。</span><span class="sxs-lookup"><span data-stu-id="dde47-106">When the Patients app is retired, all data associated with it will be retained in this group but can no longer be accessed through the user interface.</span></span> <span data-ttu-id="dde47-107">当前用户可以使用 " [列表" 应用](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db)重新创建其列表。</span><span class="sxs-lookup"><span data-stu-id="dde47-107">Current users can re-create their lists using the [Lists app](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db).</span></span>
>
><span data-ttu-id="dde47-108">" [列表" 应用](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) 为所有团队用户预安装，可在每个团队和频道中用作选项卡。</span><span class="sxs-lookup"><span data-stu-id="dde47-108">The [Lists app](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) is pre-installed for all Teams users and is available as a tab in every team and channel.</span></span> <span data-ttu-id="dde47-109">使用 "列表"，"护理团队" 可以使用内置患者模板、从头开始或通过将数据导入 Excel 来创建患者列表。</span><span class="sxs-lookup"><span data-stu-id="dde47-109">With Lists, care teams can create patient lists using the built-in Patients template, from scratch, or by importing data to Excel.</span></span> <span data-ttu-id="dde47-110">若要了解有关如何管理组织中的列表应用的详细信息，请参阅 [管理列表应用](../../manage-lists-app.md)。</span><span class="sxs-lookup"><span data-stu-id="dde47-110">To learn more about how to manage the Lists app in your organization, see [Manage the Lists app](../../manage-lists-app.md).</span></span>

[!INCLUDE [preview-feature](../../includes/preview-feature.md)]

<span data-ttu-id="dde47-111">设置或重新配置 FHIR 服务器以处理 Microsoft 团队患者应用需要了解应用需要访问的数据。</span><span class="sxs-lookup"><span data-stu-id="dde47-111">Setting up or reconfiguring an FHIR server to work with the Microsoft Teams Patients app requires understanding what data the app needs to access.</span></span> <span data-ttu-id="dde47-112">FHIR 服务器必须使用以下资源的捆绑包支持发布请求：</span><span class="sxs-lookup"><span data-stu-id="dde47-112">The FHIR server must support POST requests using bundles for the following resources:</span></span>

- [<span data-ttu-id="dde47-113">档案</span><span class="sxs-lookup"><span data-stu-id="dde47-113">Patient</span></span>](#patient)
- [<span data-ttu-id="dde47-114">知识产权</span><span class="sxs-lookup"><span data-stu-id="dde47-114">Observation</span></span>](#observation)
- [<span data-ttu-id="dde47-115">条件</span><span class="sxs-lookup"><span data-stu-id="dde47-115">Condition</span></span>](#condition)
- [<span data-ttu-id="dde47-116">产生</span><span class="sxs-lookup"><span data-stu-id="dde47-116">Encounter</span></span>](#encounter)
- [<span data-ttu-id="dde47-117">过敏症 Intolerance</span><span class="sxs-lookup"><span data-stu-id="dde47-117">Allergy Intolerance</span></span>](#allergyintolerance)
- [<span data-ttu-id="dde47-118">内</span><span class="sxs-lookup"><span data-stu-id="dde47-118">Coverage</span></span>](#coverage)
- <span data-ttu-id="dde47-119">[药物报表](#medication-request) (替换 PATIENTSAPP 的 DSTU2 版本中的 MedicationOrder) </span><span class="sxs-lookup"><span data-stu-id="dde47-119">[Medication Statement](#medication-request) (replaces the MedicationOrder in the DSTU2 version of the PatientsApp)</span></span>
- <span data-ttu-id="dde47-120">位置 (此资源所需的信息可以包含在 "遇到") </span><span class="sxs-lookup"><span data-stu-id="dde47-120">Location (the information needed from this resource can be included in Encounter)</span></span>

> [!NOTE]
> <span data-ttu-id="dde47-121">患者资源是唯一必需的资源 (不会在所有) 加载的应用;但是，建议合作伙伴针对 Microsoft 团队患者应用的最佳最终用户体验，针对以下提供的针对以上提及的所有资源提供支持。</span><span class="sxs-lookup"><span data-stu-id="dde47-121">The Patient resource is the only mandatory resource (without which the app will not load at all); However, it is recommended that the Partner implement support for all the above mentioned resources per specifications provided below for the best end-user experience with the Microsoft Teams Patients App.</span></span>

<span data-ttu-id="dde47-122">来自 Microsoft 团队患者应用的来自多个资源的查询将发布 (批处理) FHIR 服务器 URL 的捆绑包。</span><span class="sxs-lookup"><span data-stu-id="dde47-122">Queries from the Microsoft Teams Patients app for more than one resource shall post a bundle (BATCH) of requests to the FHIR server's URL.</span></span> <span data-ttu-id="dde47-123">服务器应对每个请求进行处理，并返回每个请求所匹配的资源的捆绑包。</span><span class="sxs-lookup"><span data-stu-id="dde47-123">The server shall process each request and return a bundle of the resources matched by each request.</span></span> <span data-ttu-id="dde47-124">有关详细信息和示例，请参阅 [https://www.hl7.org/fhir/STU3/http.html#transaction](https://www.hl7.org/fhir/STU3/http.html#transaction) 。</span><span class="sxs-lookup"><span data-stu-id="dde47-124">For more information and examples, see [https://www.hl7.org/fhir/STU3/http.html#transaction](https://www.hl7.org/fhir/STU3/http.html#transaction).</span></span>

## <a name="capability-statement"></a><span data-ttu-id="dde47-125">功能陈述</span><span class="sxs-lookup"><span data-stu-id="dde47-125">Capability Statement</span></span>

<span data-ttu-id="dde47-126">以下是最少的必填字段：</span><span class="sxs-lookup"><span data-stu-id="dde47-126">These are the minimum required fields:</span></span>

1. <span data-ttu-id="dde47-127">余下</span><span class="sxs-lookup"><span data-stu-id="dde47-127">REST</span></span>
   1. <span data-ttu-id="dde47-128">众</span><span class="sxs-lookup"><span data-stu-id="dde47-128">Mode</span></span>
   2. <span data-ttu-id="dde47-129">相交</span><span class="sxs-lookup"><span data-stu-id="dde47-129">Interaction</span></span>
   3. <span data-ttu-id="dde47-130">资源：类型</span><span class="sxs-lookup"><span data-stu-id="dde47-130">Resource: Type</span></span>
   4. <span data-ttu-id="dde47-131">安全性： [OAuth uri 的扩展](https://hl7.org/fhir/extension-oauth-uris.html)</span><span class="sxs-lookup"><span data-stu-id="dde47-131">Security: [Extension for OAuth URIs](https://hl7.org/fhir/extension-oauth-uris.html)</span></span>
2. <span data-ttu-id="dde47-132">FhirVersion (我们的代码需要此内容才能了解应将数据透视到哪个版本。 ) </span><span class="sxs-lookup"><span data-stu-id="dde47-132">FhirVersion (Our code requires this to understand which version we should pivot to.)</span></span>

<span data-ttu-id="dde47-133">[https://www.hl7.org/fhir/stu3/capabilitystatement.html](https://www.hl7.org/fhir/stu3/capabilitystatement.html)有关此字段集的其他详细信息，请参阅。</span><span class="sxs-lookup"><span data-stu-id="dde47-133">See [https://www.hl7.org/fhir/stu3/capabilitystatement.html](https://www.hl7.org/fhir/stu3/capabilitystatement.html) for other details on this field set.</span></span>

## <a name="patient"></a><span data-ttu-id="dde47-134">档案</span><span class="sxs-lookup"><span data-stu-id="dde47-134">Patient</span></span>

<span data-ttu-id="dde47-135">下面是 "Argonaut" 患者档案字段子集的最少必填字段：</span><span class="sxs-lookup"><span data-stu-id="dde47-135">Here are the minimum required fields, which are a subset of the Argonaut patient profile fields:</span></span>

1. <span data-ttu-id="dde47-136">名称。给定</span><span class="sxs-lookup"><span data-stu-id="dde47-136">Name.Given</span></span>
2. <span data-ttu-id="dde47-137">名称。家庭</span><span class="sxs-lookup"><span data-stu-id="dde47-137">Name.Family</span></span>
3. <span data-ttu-id="dde47-138">性别</span><span class="sxs-lookup"><span data-stu-id="dde47-138">Gender</span></span>
4. <span data-ttu-id="dde47-139">BirthDate</span><span class="sxs-lookup"><span data-stu-id="dde47-139">BirthDate</span></span>
5. <span data-ttu-id="dde47-140">MRN (标识符) </span><span class="sxs-lookup"><span data-stu-id="dde47-140">MRN (Identifier)</span></span>

<span data-ttu-id="dde47-141">除了 [Argonaut 字段](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-patient.html)外，还可以为患者应用提供出色的用户体验，还可以读取以下字段：</span><span class="sxs-lookup"><span data-stu-id="dde47-141">In addition to the [Argonaut fields](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-patient.html), for a great user experience the Patients app can also read the following fields:</span></span>

1. <span data-ttu-id="dde47-142">名称。使用</span><span class="sxs-lookup"><span data-stu-id="dde47-142">Name.Use</span></span>
2. <span data-ttu-id="dde47-143">名称。前缀</span><span class="sxs-lookup"><span data-stu-id="dde47-143">Name.Prefix</span></span>
3. <span data-ttu-id="dde47-144">[GeneralPractitioner]-GeneralPractitioner 参考应包含在患者资源 (仅限显示字段中) </span><span class="sxs-lookup"><span data-stu-id="dde47-144">[GeneralPractitioner] - The GeneralPractitioner reference should be included in the Patient resource (display field only)</span></span>

<span data-ttu-id="dde47-145">资源搜索在/Patient/_search 使用 POST 方法，并使用以下参数：</span><span class="sxs-lookup"><span data-stu-id="dde47-145">A resource search uses the POST method at /Patient/_search and the following parameters:</span></span>

1. <span data-ttu-id="dde47-146">标识号</span><span class="sxs-lookup"><span data-stu-id="dde47-146">id</span></span>
2. <span data-ttu-id="dde47-147">系列 = (搜索其系列名称包含该值的所有患者) </span><span class="sxs-lookup"><span data-stu-id="dde47-147">family=(searches for all patients whose family name contains the value)</span></span>
3. <span data-ttu-id="dde47-148">给定 =\<substring></span><span class="sxs-lookup"><span data-stu-id="dde47-148">given=\<substring></span></span>
4. <span data-ttu-id="dde47-149">出生日期 = (完全匹配) </span><span class="sxs-lookup"><span data-stu-id="dde47-149">birthdate=(exact match)</span></span>
5. <span data-ttu-id="dde47-150">性别 = (值是一个管理性别) </span><span class="sxs-lookup"><span data-stu-id="dde47-150">gender=(values being one of the administrative-gender)</span></span>
6. <span data-ttu-id="dde47-151">\_计数 (应返回的最大结果数) </span><span class="sxs-lookup"><span data-stu-id="dde47-151">\_count (maximum number of results that should be returned)</span></span> <br> <span data-ttu-id="dde47-152">该响应应包含作为搜索和计数的结果返回的记录总数， \_ PatientsApp 将使用该计数来限制返回的记录数。</span><span class="sxs-lookup"><span data-stu-id="dde47-152">The response should contain the total count of records returned as a result of the search and \_count will be used by the PatientsApp to limit the number of records returned.</span></span>
7. <span data-ttu-id="dde47-153">标识符 =\<mrn></span><span class="sxs-lookup"><span data-stu-id="dde47-153">identifier=\<mrn></span></span>

<span data-ttu-id="dde47-154">目标是能够搜索和筛选患者，如下所示：</span><span class="sxs-lookup"><span data-stu-id="dde47-154">The goal is to be able to search and filter for a patient by the following:</span></span>

- <span data-ttu-id="dde47-155">ID：这是 FHIR 中的每个资源具有的资源 ID。</span><span class="sxs-lookup"><span data-stu-id="dde47-155">ID: This is the resource ID that every resource in FHIR has.</span></span>
- <span data-ttu-id="dde47-156">MRN：这是临床人员将知道的患者的实际标识符。</span><span class="sxs-lookup"><span data-stu-id="dde47-156">MRN: This is the actual identifier for the patient that clinical staff would know.</span></span> <span data-ttu-id="dde47-157">我们理解此 MRN 基于 FHIR 中的标识符资源内的标识符类型。</span><span class="sxs-lookup"><span data-stu-id="dde47-157">We understand this MRN is based on the type of identifier inside the identifier resource in FHIR.</span></span>
- <span data-ttu-id="dde47-158">名称</span><span class="sxs-lookup"><span data-stu-id="dde47-158">Name</span></span>
- <span data-ttu-id="dde47-159">Birthdate</span><span class="sxs-lookup"><span data-stu-id="dde47-159">Birthdate</span></span>

<span data-ttu-id="dde47-160">请参阅下面的通话示例：</span><span class="sxs-lookup"><span data-stu-id="dde47-160">See the following example of the call:</span></span>

* * *

    <span data-ttu-id="dde47-161">请求： POST <fhir-server>/Patient/_search 请求正文：给定 = ruth&家族 = 黑色</span><span class="sxs-lookup"><span data-stu-id="dde47-161">Request: POST <fhir-server>/Patient/_search Request Body: given=ruth&family=black</span></span>
    
    <span data-ttu-id="dde47-162">响应： {"resourceType"： "捆绑包"，"id"： "<捆绑包-id>"，"meta"： {"lastUpdated"： "2019-01-" type "：" searchset "，" total "：1，" link "： [{" relation "：" self "，" url "： <fhir-服务器>/Patient/_search"}]，"entry"： [{"fullUrl"： <fhir-server>/Patient/<患者 id> "，" 资源 "： {" resourceType "：" 患者 "，" id "：" <患者 id> "，" meta "： {" versionId "：" 1 "，" lastUpdated "：" 2017-18T18：32： 37.000 + 00： 00 "}，" text "： {" status "：" 已生成 "，" div "："</span><span class="sxs-lookup"><span data-stu-id="dde47-162">Response: { "resourceType": "Bundle", "id": "<bundle-id>", "meta": { "lastUpdated": "2019-01-14T23:44:45.052+00:00" }, "type": "searchset", "total": 1, "link": [ { "relation": "self", "url": <fhir-server>/Patient/_search" } ], "entry": [ { "fullUrl": <fhir-server>/Patient/<patient-id>", "resource": { "resourceType": "Patient", "id": "<patient-id>", "meta": { "versionId": "1", "lastUpdated": "2017-10-18T18:32:37.000+00:00" }, "text": { "status": "generated", "div": "</span></span><div><span data-ttu-id="dde47-163">\n</span><span class="sxs-lookup"><span data-stu-id="dde47-163">\n</span></span>        <p><span data-ttu-id="dde47-164">Ruth 黑</span><span class="sxs-lookup"><span data-stu-id="dde47-164">Ruth Black</span></span></p><span data-ttu-id="dde47-165">\n</span><span class="sxs-lookup"><span data-stu-id="dde47-165">\n</span></span>      </div><span data-ttu-id="dde47-166">"}，" 标识符 "： [{" 使用 "：" 常规 "，" 键入 "： {" 编码 "： [{" 系统 "：" https://hl7.org/fhir/v2/0203 "，" 代码 "：" "MR"，"代码"： "MR"，"显示"： "userSelected"： false}]，"文本"： "医学记录编号"}，"system"： " http://hospital.smarthealthit.org 1234567"，"name"： [{"：" ""，"name"： [{"：" 官方 "，" 系列 "：" 黑色 "，" 第一个 "： [" Ruth "，" C "。</span><span class="sxs-lookup"><span data-stu-id="dde47-166">" }, "identifier": [ { "use": "usual", "type": { "coding": [ { "system": "https://hl7.org/fhir/v2/0203", "code": "MR", "display": "Medical record number", "userSelected": false } ], "text": "Medical record number" }, "system": "http://hospital.smarthealthit.org", "value": "1234567" } ], "active": true, "name": [ { "use": "official", "family": "Black", "given": [ "Ruth", "C."</span></span>
    <span data-ttu-id="dde47-167">]}]，"电信"： [{"系统"： "电话"，"值"： "800-599-2739"，"使用"： "手机"}，{"系统"： "800-808-7785"，"值"： "ruth.black@example.com"，"使用"： "mobile"}，{"系统"： "电子邮件"，"值"： ""}]，"性别"： "女"，"出生日期"： "1951-08-23"，"地址"： [{"使用"： "开始"，"行"： ["26 RdApt 22"]，"城市"： "Sapulpa"，"状态"： "确定"，"邮政编码"： "74066"，"国家/地区"： "美国"}]}，"search"： {"mode"： "match"}}]}</span><span class="sxs-lookup"><span data-stu-id="dde47-167">] } ], "telecom": [ { "system": "phone", "value": "800-599-2739", "use": "home" }, { "system": "phone", "value": "800-808-7785", "use": "mobile" }, { "system": "email", "value": "ruth.black@example.com" } ], "gender": "female", "birthDate": "1951-08-23", "address": [ { "use": "home", "line": [ "26 South RdApt 22" ], "city": "Sapulpa", "state": "OK", "postalCode": "74066", "country": "USA" } ] }, "search": { "mode": "match" } } ] }</span></span>

* * *

    <span data-ttu-id="dde47-168">请求：获取 <fhir-服务器>/Patient/<患者 id></span><span class="sxs-lookup"><span data-stu-id="dde47-168">Request: GET <fhir-server>/Patient/<patient-id></span></span>
    
    <span data-ttu-id="dde47-169">回复： {"resourceType"： "患者"，"id"： "<患者 id>"，"标识符"： [{"使用"： "常规"，"键入"： {"编码"： [{"系统"： "" https://hl7.org/fhir/v2/0203 ，"代码"： "MR"，}]，"文本"： "医学记录数字"}，"值"： "1234567"}]，"名称"： [{"：" "}]，" 名称 "： [{" "Adams"，"family"： "Daniel"，"X"。</span><span class="sxs-lookup"><span data-stu-id="dde47-169">Response: { "resourceType": "Patient", "id": "<patient-id>", "identifier": [ { "use": "usual", "type": { "coding": [ { "system": "https://hl7.org/fhir/v2/0203", "code": "MR", } ], "text": "Medical record number" }, "value": "1234567" } ], "name": [ { "use": "official", "family": "Adams", "given": [ "Daniel", "X."</span></span> <span data-ttu-id="dde47-170">]}]，"性别"： "男"，"出生日期"： "1925-12-23"，}</span><span class="sxs-lookup"><span data-stu-id="dde47-170">] } ], "gender": "male", "birthDate": "1925-12-23", }</span></span>

* * *

<span data-ttu-id="dde47-171">[https://hl7.org/fhir/stu3/patient.html](https://hl7.org/fhir/stu3/patient.html)有关此字段集的其他详细信息，请参阅。</span><span class="sxs-lookup"><span data-stu-id="dde47-171">See [https://hl7.org/fhir/stu3/patient.html](https://hl7.org/fhir/stu3/patient.html) for other details on this field set.</span></span>

## <a name="observation"></a><span data-ttu-id="dde47-172">知识产权</span><span class="sxs-lookup"><span data-stu-id="dde47-172">Observation</span></span>

<span data-ttu-id="dde47-173">以下是最少的必填字段，它们是 Argonaut 的 [重要签名配置文件](https://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-vitalsigns.html)的子集。</span><span class="sxs-lookup"><span data-stu-id="dde47-173">These are the minimum required fields, which are a subset of the [Argonaut Vital-Signs profile](https://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-vitalsigns.html).</span></span>

1. <span data-ttu-id="dde47-174">有效 (日期时间或期间) </span><span class="sxs-lookup"><span data-stu-id="dde47-174">Effective (date time or period)</span></span>
2. <span data-ttu-id="dde47-175">编码代码</span><span class="sxs-lookup"><span data-stu-id="dde47-175">Code.Coding.Code</span></span>
3. <span data-ttu-id="dde47-176">ValueQuantity 值</span><span class="sxs-lookup"><span data-stu-id="dde47-176">ValueQuantity.Value</span></span>

<span data-ttu-id="dde47-177">除了 Argonaut 字段外，还可以为患者应用提供出色的用户体验，还可以读取以下字段：</span><span class="sxs-lookup"><span data-stu-id="dde47-177">In addition to the Argonaut fields, for a great user experience the Patients app can also read the following fields:</span></span>

1. <span data-ttu-id="dde47-178">代码编码。显示</span><span class="sxs-lookup"><span data-stu-id="dde47-178">Code.Coding.Display</span></span>
2. <span data-ttu-id="dde47-179">ValueQuantity 单位</span><span class="sxs-lookup"><span data-stu-id="dde47-179">ValueQuantity.Unit</span></span>

<span data-ttu-id="dde47-180">资源搜索使用 GET 方法和以下参数：</span><span class="sxs-lookup"><span data-stu-id="dde47-180">A resource search uses the GET method and the following parameters:</span></span>

1. <span data-ttu-id="dde47-181">患者 =\<patient id></span><span class="sxs-lookup"><span data-stu-id="dde47-181">patient=\<patient id></span></span>
2. <span data-ttu-id="dde47-182">_sort =-日期</span><span class="sxs-lookup"><span data-stu-id="dde47-182">_sort=-date</span></span>
3. <span data-ttu-id="dde47-183">类别 (我们将查询 "category = 重要标志" ) 以检索关键签名列表。</span><span class="sxs-lookup"><span data-stu-id="dde47-183">category (we will query for "category=vital-signs") to retrieve the list of vital signs.</span></span>

<span data-ttu-id="dde47-184">请参阅此通话示例：</span><span class="sxs-lookup"><span data-stu-id="dde47-184">Refer to this example of the call:</span></span>

* * *

    <span data-ttu-id="dde47-185">请求：获取 <fhir-服务器>/Observation？患者 =<患者 id>&类别 = "重要签名"</span><span class="sxs-lookup"><span data-stu-id="dde47-185">Request: GET <fhir-server>/Observation?patient=<patient-id>&category=vital-signs</span></span>
    
    <span data-ttu-id="dde47-186">响应： {"resourceType"： "捆绑包"，"id"： "<捆绑包-id>"，"键入"： "searchset"，"total"：20，"entry"： [{"resource"： {""： "观察"，"id"： "<资源 id>"，"类别"： [{"编码"： [{"系统"： " https://hl7.org/fhir/observation-category " "，" 代码 "：" 重要签名 "}]，}]，" 代码 "： {" code "： [{" system "：" http://loinc.org ""，"code"： "8867-4"，"显示"： "heart_rate"}]}，"effectiveDateTime"： "2009 年08T00：00： 00-06： 00"，"valueQuantity"： {"value"：72.0，"unit"： "{节拍} ¢"，"system"： " http://unitsofmeasure.org "，"</span><span class="sxs-lookup"><span data-stu-id="dde47-186">Response: { "resourceType": "Bundle", "id": "<bundle-id>", "type": "searchset", "total": 20, "entry": [ { "resource": { "resourceType": "Observation", "id": "<resource-id>", "category": [ { "coding": [ { "system": "https://hl7.org/fhir/observation-category", "code": "vital-signs" } ], } ], "code": { "coding": [ { "system": "http://loinc.org", "code": "8867-4", "display": "heart_rate" } ] }, "effectiveDateTime": "2009-04-08T00:00:00-06:00", "valueQuantity": { "value": 72.0, "unit": "{beats}/min", "system": "http://unitsofmeasure.org", } } }, .</span></span>
        <span data-ttu-id="dde47-187">.</span><span class="sxs-lookup"><span data-stu-id="dde47-187">.</span></span>
        <span data-ttu-id="dde47-188">.</span><span class="sxs-lookup"><span data-stu-id="dde47-188">.</span></span>
      <span data-ttu-id="dde47-189">] }</span><span class="sxs-lookup"><span data-stu-id="dde47-189">] }</span></span>

* * *

<span data-ttu-id="dde47-190">[https://www.hl7.org/fhir/stu3/observation.html](https://www.hl7.org/fhir/stu3/observation.html)有关此字段集的其他详细信息，请参阅。</span><span class="sxs-lookup"><span data-stu-id="dde47-190">See [https://www.hl7.org/fhir/stu3/observation.html](https://www.hl7.org/fhir/stu3/observation.html) for other details on this field set.</span></span>

## <a name="condition"></a><span data-ttu-id="dde47-191">条件</span><span class="sxs-lookup"><span data-stu-id="dde47-191">Condition</span></span>

<span data-ttu-id="dde47-192">下面是 [Argonaut 条件配置文件](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-condition.html)子集的最少必填字段。</span><span class="sxs-lookup"><span data-stu-id="dde47-192">Here's the minimum required fields, which are a subset of the [Argonaut condition profile](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-condition.html).</span></span>

1. <span data-ttu-id="dde47-193">代码。编码 [0]。画面</span><span class="sxs-lookup"><span data-stu-id="dde47-193">Code.Coding[0].Display</span></span>

<span data-ttu-id="dde47-194">除了 Argonaut 字段外，还可以为患者应用提供出色的用户体验，还可以读取以下字段：</span><span class="sxs-lookup"><span data-stu-id="dde47-194">In addition to the Argonaut fields, for a great user experience the Patients app can also read the following fields:</span></span>

1. <span data-ttu-id="dde47-195">AssertedDate</span><span class="sxs-lookup"><span data-stu-id="dde47-195">AssertedDate</span></span>
2. <span data-ttu-id="dde47-196">严重性</span><span class="sxs-lookup"><span data-stu-id="dde47-196">Severity</span></span>

<span data-ttu-id="dde47-197">资源搜索使用 GET 方法和以下参数：</span><span class="sxs-lookup"><span data-stu-id="dde47-197">A resource search uses the GET method and the following parameters:</span></span>

1. <span data-ttu-id="dde47-198">患者 =\<patient id></span><span class="sxs-lookup"><span data-stu-id="dde47-198">patient=\<patient id></span></span>
2. <span data-ttu-id="dde47-199">_count =\<max results></span><span class="sxs-lookup"><span data-stu-id="dde47-199">_count=\<max results></span></span>

<span data-ttu-id="dde47-200">请参阅下面的此呼叫示例：</span><span class="sxs-lookup"><span data-stu-id="dde47-200">See the following example of this call:</span></span>

* * *

    <span data-ttu-id="dde47-201">请求：获取 <fhir-服务器>/Condition？患者 =<患者 id>&_count = 10</span><span class="sxs-lookup"><span data-stu-id="dde47-201">Request: GET <fhir-server>/Condition?patient=<patient-id>&_count=10</span></span>
    
    <span data-ttu-id="dde47-202">响应： {"resourceType"： "捆绑包"，"id"： "<捆绑包-id>"，"类型"： "searchset"，"total"：2，"entry"： [{"resource"： {"resourceType"： "Condition"，"id"： "<资源 id>"，"代码"： {"编码"： [{"system"： " http://snomed.info/sct "，"代码"： "185903001"，"display"： "需要 influenza 免疫接种"、}]}、"严重性"： {"编码"： [{"system"： " http://snomed.info/sct "，"代码"： "24484000"，"显示"： "严重"}]}，"assertedDate"： "2018-04-04"}}。</span><span class="sxs-lookup"><span data-stu-id="dde47-202">Response: { "resourceType": "Bundle", "id": "<bundle-id>", "type": "searchset", "total": 2, "entry": [ { "resource": { "resourceType": "Condition", "id": "<resource-id>", "code": { "coding": [ { "system": "http://snomed.info/sct", "code": "185903001", "display": "Needs influenza immunization", } ] }, "severity": { "coding": [ { "system": "http://snomed.info/sct", "code": "24484000", "display": "Severe" } ] }, "assertedDate": "2018-04-04" } }, .</span></span>
        <span data-ttu-id="dde47-203">.</span><span class="sxs-lookup"><span data-stu-id="dde47-203">.</span></span>
        <span data-ttu-id="dde47-204">.</span><span class="sxs-lookup"><span data-stu-id="dde47-204">.</span></span>
      <span data-ttu-id="dde47-205">] }</span><span class="sxs-lookup"><span data-stu-id="dde47-205">] }</span></span>

* * *
<span data-ttu-id="dde47-206">[https://hl7.org/fhir/stu3/condition.html](https://hl7.org/fhir/stu3/condition.html)有关此字段集的其他详细信息，请参阅。</span><span class="sxs-lookup"><span data-stu-id="dde47-206">See [https://hl7.org/fhir/stu3/condition.html](https://hl7.org/fhir/stu3/condition.html) for other details on this field set.</span></span>

## <a name="encounter"></a><span data-ttu-id="dde47-207">产生</span><span class="sxs-lookup"><span data-stu-id="dde47-207">Encounter</span></span>

<span data-ttu-id="dde47-208">以下是最少必填字段，这些字段是 [US Core](https://hl7.org/fhir/us/core/2018Jan/StructureDefinition-us-core-encounter.html) "必须有" 字段) 的一个子集。</span><span class="sxs-lookup"><span data-stu-id="dde47-208">These are the minimum required fields, which are a subset of the [US Core Encounter profile](https://hl7.org/fhir/us/core/2018Jan/StructureDefinition-us-core-encounter.html) "must have" fields).</span></span>

1. <span data-ttu-id="dde47-209">状态栏</span><span class="sxs-lookup"><span data-stu-id="dde47-209">Status</span></span>
2. <span data-ttu-id="dde47-210">键入 [0]。编码 [0]。画面</span><span class="sxs-lookup"><span data-stu-id="dde47-210">Type[0].Coding[0].Display</span></span>

<span data-ttu-id="dde47-211">此外，美国核心的以下字段会遇到配置文件的 "必须支持" 字段：</span><span class="sxs-lookup"><span data-stu-id="dde47-211">In addition, the following fields from US Core Encounter profile's "must support" fields:</span></span>

1. <span data-ttu-id="dde47-212">句号。开始</span><span class="sxs-lookup"><span data-stu-id="dde47-212">Period.Start</span></span>
2. <span data-ttu-id="dde47-213">位置 [0]。位置。显示</span><span class="sxs-lookup"><span data-stu-id="dde47-213">Location[0].Location.Display</span></span>

<span data-ttu-id="dde47-214">资源搜索使用 GET 方法和以下参数：</span><span class="sxs-lookup"><span data-stu-id="dde47-214">A resource search uses the GET method and the following parameters:</span></span>

1. <span data-ttu-id="dde47-215">患者 =\<patient id></span><span class="sxs-lookup"><span data-stu-id="dde47-215">patient=\<patient id></span></span>
2. <span data-ttu-id="dde47-216">_sort： desc =\<field ex. date></span><span class="sxs-lookup"><span data-stu-id="dde47-216">_sort:desc=\<field ex. date></span></span>
3. <span data-ttu-id="dde47-217">_count =\<max results></span><span class="sxs-lookup"><span data-stu-id="dde47-217">_count=\<max results></span></span>

<span data-ttu-id="dde47-218">目标是能够检索患者的最后一个已知位置。</span><span class="sxs-lookup"><span data-stu-id="dde47-218">The goal is to be able to retrieve the patient's last known location.</span></span> <span data-ttu-id="dde47-219">每个遇到的都引用一个位置资源。</span><span class="sxs-lookup"><span data-stu-id="dde47-219">Each encounter references a location resource.</span></span> <span data-ttu-id="dde47-220">该引用还应包含位置的显示字段。</span><span class="sxs-lookup"><span data-stu-id="dde47-220">The reference shall also include the location's display field.</span></span>

<span data-ttu-id="dde47-221">[https://hl7.org/fhir/stu3/encounter.html](https://hl7.org/fhir/stu3/encounter.html)有关此字段集的其他详细信息，请参阅。</span><span class="sxs-lookup"><span data-stu-id="dde47-221">See [https://hl7.org/fhir/stu3/encounter.html](https://hl7.org/fhir/stu3/encounter.html) for other details on this field set.</span></span>

## <a name="allergyintolerance"></a><span data-ttu-id="dde47-222">AllergyIntolerance</span><span class="sxs-lookup"><span data-stu-id="dde47-222">AllergyIntolerance</span></span>

<span data-ttu-id="dde47-223">以下是最少的必填字段，它们是 [Argonaut AllergyIntolerance](https://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-allergyintolerance.html) 配置文件的子集：</span><span class="sxs-lookup"><span data-stu-id="dde47-223">These are the minimum required fields, which are a subset of the [Argonaut AllergyIntolerance](https://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-allergyintolerance.html) profile:</span></span>

1. <span data-ttu-id="dde47-224">代码。文本</span><span class="sxs-lookup"><span data-stu-id="dde47-224">Code.Text</span></span>
2. <span data-ttu-id="dde47-225">代码。编码 [0]。画面</span><span class="sxs-lookup"><span data-stu-id="dde47-225">Code.Coding[0].Display</span></span>
3. <span data-ttu-id="dde47-226">ClinicalStatus/VerificationStatus (我们同时阅读) </span><span class="sxs-lookup"><span data-stu-id="dde47-226">ClinicalStatus/VerificationStatus (we read both)</span></span>

<span data-ttu-id="dde47-227">除了 Argonaut 字段外，还可为患者应用提供出色的用户体验，还可以读取以下字段：</span><span class="sxs-lookup"><span data-stu-id="dde47-227">In addition to the Argonaut fields, for a great user experience the Patients app can also read the following field:</span></span>

1. <span data-ttu-id="dde47-228">AssertedDate</span><span class="sxs-lookup"><span data-stu-id="dde47-228">AssertedDate</span></span>
2. <span data-ttu-id="dde47-229">备注。文本</span><span class="sxs-lookup"><span data-stu-id="dde47-229">Note.Text</span></span>
3. <span data-ttu-id="dde47-230">被动</span><span class="sxs-lookup"><span data-stu-id="dde47-230">Reaction</span></span>
    1. <span data-ttu-id="dde47-231"> (一个编码元素) 的物质</span><span class="sxs-lookup"><span data-stu-id="dde47-231">Substance (one coding element)</span></span>
    2. <span data-ttu-id="dde47-232"> (一个编码元素的表现形式) </span><span class="sxs-lookup"><span data-stu-id="dde47-232">Manifestation (one coding element)</span></span>

<span data-ttu-id="dde47-233">资源搜索使用 GET 方法和以下参数：</span><span class="sxs-lookup"><span data-stu-id="dde47-233">A resource search uses the GET method and the following parameters:</span></span>

1. <span data-ttu-id="dde47-234">患者 =  \<patient id></span><span class="sxs-lookup"><span data-stu-id="dde47-234">Patient =  \<patient id></span></span>

<span data-ttu-id="dde47-235">请参阅下面的通话示例：</span><span class="sxs-lookup"><span data-stu-id="dde47-235">See the following example of the call:</span></span> 

* * *

    <span data-ttu-id="dde47-236">请求：获取 <fhir-服务器>/AllergyIntolerance？患者 =<患者 id></span><span class="sxs-lookup"><span data-stu-id="dde47-236">Request: GET <fhir-server>/AllergyIntolerance?patient=<patient-id></span></span>
    
    <span data-ttu-id="dde47-237">响应： {"resourceType"： "捆绑包"，"id"： "<捆绑包 id>"，"键入"： "searchset"，"total"：1，"entry"： [{"资源"： {"resourceType"： "AllergyIntolerance"，"id"： "<资源 id>"，"clinicalStatus"： "active"，"verificationStatus"： "已确认"，"代码"： {"编码"： [{"系统"： " http://rxnav.nlm.nih.gov/REST/Ndfrt "，"代码"： "" N0000175503 "，" 显示 "：" sulfonamide antibacterial "，}]，" text "：" sulfonamide antibacterial "}，" assertedDate "：" 2018 日，01T00：00：00： 00 "，" 反应 "： [{" 表现形式 "： [{" code "： [{" system "：" http://snomed.info/sct "，" 代码 "：" 271807003 "，" display "：" 皮肤 rash "，}]，" text "：" 皮肤 rash "}]，}]}</span><span class="sxs-lookup"><span data-stu-id="dde47-237">Response: {   "resourceType": "Bundle",   "id": "<bundle-id>",   "type": "searchset",   "total": 1,   "entry": [     {       "resource": {         "resourceType": "AllergyIntolerance",         "id": "<resource-id>",         "clinicalStatus": "active",         "verificationStatus": "confirmed",         "code": {           "coding": [             {               "system": "http://rxnav.nlm.nih.gov/REST/Ndfrt",               "code": "N0000175503",               "display": "sulfonamide antibacterial",             }           ],           "text": "sulfonamide antibacterial"         },         "assertedDate": "2018-01-01T00:00:00-07:00",         "reaction": [           {             "manifestation": [               {                 "coding": [                   {                     "system": "http://snomed.info/sct",                     "code": "271807003",                     "display": "skin rash",                   }                 ],                 "text": "skin rash"               }             ],           }         ]       }     }   ] }</span></span>

* * *

<span data-ttu-id="dde47-238">[https://hl7.org/fhir/stu3/allergyintolerance.html](https://hl7.org/fhir/stu3/allergyintolerance.html)有关此字段集的其他详细信息，请参阅。</span><span class="sxs-lookup"><span data-stu-id="dde47-238">See [https://hl7.org/fhir/stu3/allergyintolerance.html](https://hl7.org/fhir/stu3/allergyintolerance.html) for other details on this field set.</span></span>

## <a name="medication-request"></a><span data-ttu-id="dde47-239">药物请求</span><span class="sxs-lookup"><span data-stu-id="dde47-239">Medication Request</span></span>

<span data-ttu-id="dde47-240">以下是最少的必填字段，这些字段是 [美国核心药物请求档案](http://www.hl7.org/fhir/us/core/StructureDefinition-us-core-medicationrequest.html)的子集：</span><span class="sxs-lookup"><span data-stu-id="dde47-240">These are the minimum required fields, which are a subset of the [US Core Medication Request profile](http://www.hl7.org/fhir/us/core/StructureDefinition-us-core-medicationrequest.html):</span></span>

1. <span data-ttu-id="dde47-241">药物。如果引用) ，则显示 (</span><span class="sxs-lookup"><span data-stu-id="dde47-241">Medication.Display (if Reference)</span></span>
2. <span data-ttu-id="dde47-242">如果 CodableConcept) ，则为文本 (</span><span class="sxs-lookup"><span data-stu-id="dde47-242">Medication.Text (if CodableConcept)</span></span>
3. <span data-ttu-id="dde47-243">AuthoredOn</span><span class="sxs-lookup"><span data-stu-id="dde47-243">AuthoredOn</span></span>
4. <span data-ttu-id="dde47-244">请求者代理。显示</span><span class="sxs-lookup"><span data-stu-id="dde47-244">Requester.Agent.Display</span></span>

<span data-ttu-id="dde47-245">除了 US 核心字段外，还可为患者应用提供出色的用户体验，还可以读取以下字段：</span><span class="sxs-lookup"><span data-stu-id="dde47-245">In addition to the US Core fields, for a great user experience the Patients app can also read the following fields:</span></span>

1. <span data-ttu-id="dde47-246">DosageInstruction[..].文本</span><span class="sxs-lookup"><span data-stu-id="dde47-246">DosageInstruction[..].Text</span></span>
2. <span data-ttu-id="dde47-247">文本</span><span class="sxs-lookup"><span data-stu-id="dde47-247">Text</span></span>

<span data-ttu-id="dde47-248">资源搜索使用 GET 方法和以下参数：</span><span class="sxs-lookup"><span data-stu-id="dde47-248">A resource search uses the GET method and the following parameters:</span></span>

1. <span data-ttu-id="dde47-249">患者 =\<patient id></span><span class="sxs-lookup"><span data-stu-id="dde47-249">patient=\<patient id></span></span>
2. <span data-ttu-id="dde47-250">_count =\<max results></span><span class="sxs-lookup"><span data-stu-id="dde47-250">_count=\<max results></span></span>

<span data-ttu-id="dde47-251">[https://www.hl7.org/fhir/medicationrequest.html](https://www.hl7.org/fhir/medicationrequest.html)有关此字段集的其他详细信息，请参阅。</span><span class="sxs-lookup"><span data-stu-id="dde47-251">See [https://www.hl7.org/fhir/medicationrequest.html](https://www.hl7.org/fhir/medicationrequest.html) for other details on this field set.</span></span>

## <a name="coverage"></a><span data-ttu-id="dde47-252">内</span><span class="sxs-lookup"><span data-stu-id="dde47-252">Coverage</span></span>

<span data-ttu-id="dde47-253">以下是 "最少必填字段"，不包含在美国 Core 或 Argonaut 配置文件中：</span><span class="sxs-lookup"><span data-stu-id="dde47-253">These are the minimum required fields, not covered by either US Core or Argonaut profiles:</span></span>

1. <span data-ttu-id="dde47-254">组合，至少一个元素具有</span><span class="sxs-lookup"><span data-stu-id="dde47-254">Grouping, at least one element with</span></span>
    1. <span data-ttu-id="dde47-255">GroupDisplay</span><span class="sxs-lookup"><span data-stu-id="dde47-255">GroupDisplay</span></span>
    2. <span data-ttu-id="dde47-256">PlanDisplay</span><span class="sxs-lookup"><span data-stu-id="dde47-256">PlanDisplay</span></span>
2. <span data-ttu-id="dde47-257">试用期</span><span class="sxs-lookup"><span data-stu-id="dde47-257">Period</span></span>
3. <span data-ttu-id="dde47-258">SubscriberId</span><span class="sxs-lookup"><span data-stu-id="dde47-258">SubscriberId</span></span>

<span data-ttu-id="dde47-259">资源搜索使用 GET 方法和以下参数：</span><span class="sxs-lookup"><span data-stu-id="dde47-259">A resource search uses the GET method and the following parameters:</span></span>

1. <span data-ttu-id="dde47-260">患者 = \<patient id></span><span class="sxs-lookup"><span data-stu-id="dde47-260">Patient = \<patient id></span></span>

<span data-ttu-id="dde47-261">[https://hl7.org/fhir/stu3/coverage.html](https://www.hl7.org/fhir/medicationrequest.html)有关此字段集的其他详细信息，请参阅。</span><span class="sxs-lookup"><span data-stu-id="dde47-261">See [https://hl7.org/fhir/stu3/coverage.html](https://www.hl7.org/fhir/medicationrequest.html) for other details on this field set.</span></span>
