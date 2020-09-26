---
title: 患者应用和 EHR 集成 DSTU2 界面
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
description: 了解团队中的 DSTU2 界面规范，包括设置或重新配置 FHIR 服务器以使用 Microsoft 团队患者应用。
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: fbbff4eda0eb1426bdf92068d95ccf00abe62a61
ms.sourcegitcommit: a28232f16bfefe6414d1f5a54d5f8c8665eb0e23
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/25/2020
ms.locfileid: "48277268"
---
# <a name="dstu2-interface-specification"></a><span data-ttu-id="613d9-103">DSTU2 接口规范</span><span class="sxs-lookup"><span data-stu-id="613d9-103">DSTU2 interface specification</span></span>

> [!IMPORTANT]
> <span data-ttu-id="613d9-104">**2020年9月30日生效，患者应用将被否决，用户将无法再从团队应用商店安装。我们鼓励你立即开始使用团队中的 " [列表" 应用](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) 。**</span><span class="sxs-lookup"><span data-stu-id="613d9-104">**Effective September 30, 2020, the Patients app will be deprecated and users will no longer be able to install it from the Teams app store. We encourage you to start using the [Lists app](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) in Teams today.**</span></span>
>
><span data-ttu-id="613d9-105">患者应用数据存储在支持团队的 Office 365 组的组邮箱中。</span><span class="sxs-lookup"><span data-stu-id="613d9-105">Patients app data is stored in the group mailbox of the Office 365 group that backs the team.</span></span> <span data-ttu-id="613d9-106">当患者应用停用时，与之关联的所有数据将保留在此组中，但不能再通过用户界面进行访问。</span><span class="sxs-lookup"><span data-stu-id="613d9-106">When the Patients app is retired, all data associated with it will be retained in this group but can no longer be accessed through the user interface.</span></span> <span data-ttu-id="613d9-107">当前用户可以使用 " [列表" 应用](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db)重新创建其列表。</span><span class="sxs-lookup"><span data-stu-id="613d9-107">Current users can re-create their lists using the [Lists app](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db).</span></span>
>
><span data-ttu-id="613d9-108">" [列表" 应用](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) 为所有团队用户预安装，可在每个团队和频道中用作选项卡。</span><span class="sxs-lookup"><span data-stu-id="613d9-108">The [Lists app](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) is pre-installed for all Teams users and is available as a tab in every team and channel.</span></span> <span data-ttu-id="613d9-109">使用 "列表"，"护理团队" 可以使用内置患者模板、从头开始或通过将数据导入 Excel 来创建患者列表。</span><span class="sxs-lookup"><span data-stu-id="613d9-109">With Lists, care teams can create patient lists using the built-in Patients template, from scratch, or by importing data to Excel.</span></span> <span data-ttu-id="613d9-110">若要了解有关如何管理组织中的列表应用的详细信息，请参阅 [管理列表应用](../../manage-lists-app.md)。</span><span class="sxs-lookup"><span data-stu-id="613d9-110">To learn more about how to manage the Lists app in your organization, see [Manage the Lists app](../../manage-lists-app.md).</span></span>

[!INCLUDE [preview-feature](../../includes/preview-feature.md)]

<span data-ttu-id="613d9-111">设置或重新配置 FHIR 服务器以处理 Microsoft 团队患者应用需要了解应用需要访问的数据。</span><span class="sxs-lookup"><span data-stu-id="613d9-111">Setting up or reconfiguring an FHIR server to work with the Microsoft Teams Patients app requires understanding what data the app needs to access.</span></span> <span data-ttu-id="613d9-112">FHIR 服务器必须使用以下资源的捆绑包支持发布请求：</span><span class="sxs-lookup"><span data-stu-id="613d9-112">The FHIR server must support POST requests using bundles for the following resources:</span></span>

- [<span data-ttu-id="613d9-113">档案</span><span class="sxs-lookup"><span data-stu-id="613d9-113">Patient</span></span>](#patient)
- [<span data-ttu-id="613d9-114">知识产权</span><span class="sxs-lookup"><span data-stu-id="613d9-114">Observation</span></span>](#observation)
- [<span data-ttu-id="613d9-115">条件</span><span class="sxs-lookup"><span data-stu-id="613d9-115">Condition</span></span>](#condition)
- [<span data-ttu-id="613d9-116">产生</span><span class="sxs-lookup"><span data-stu-id="613d9-116">Encounter</span></span>](#encounter)
- [<span data-ttu-id="613d9-117">过敏症 intolerance</span><span class="sxs-lookup"><span data-stu-id="613d9-117">Allergy intolerance</span></span>](#allergyintolerance)
- [<span data-ttu-id="613d9-118">内</span><span class="sxs-lookup"><span data-stu-id="613d9-118">Coverage</span></span>](#coverage)
- [<span data-ttu-id="613d9-119">药物订货</span><span class="sxs-lookup"><span data-stu-id="613d9-119">Medication Order</span></span>](#medication-order)
- [<span data-ttu-id="613d9-120">位置</span><span class="sxs-lookup"><span data-stu-id="613d9-120">Location</span></span>](#location)

> [!NOTE]
> <span data-ttu-id="613d9-121">患者资源是唯一必需的资源 (不会加载应用程序。</span><span class="sxs-lookup"><span data-stu-id="613d9-121">The Patient resource is the only mandatory resource (without which the app will not load at all.</span></span> <span data-ttu-id="613d9-122">但是，建议合作伙伴针对 Microsoft 团队患者应用的最佳最终用户体验，针对以下提供的针对以上提及的所有资源提供支持。</span><span class="sxs-lookup"><span data-stu-id="613d9-122">However, it is recommended that the Partner implement support for all the above mentioned resources per specifications provided below for the best end-user experience with the Microsoft Teams Patients App.</span></span>

<span data-ttu-id="613d9-123">来自 Microsoft 团队患者应用的来自多个资源的查询发布捆绑 (对 FHIR 服务器 URL 的请求的批处理) 。</span><span class="sxs-lookup"><span data-stu-id="613d9-123">Queries from the Microsoft Teams Patients app for more than one resource post a bundle (BATCH) of requests to the FHIR server's URL.</span></span> <span data-ttu-id="613d9-124">服务器处理每个请求，并返回每个请求所匹配的资源的捆绑包。</span><span class="sxs-lookup"><span data-stu-id="613d9-124">The server processes each request and returns a bundle of the resources matched by each request.</span></span> <span data-ttu-id="613d9-125">有关详细信息和示例，请参阅 [https://www.hl7.org/fhir/DSTU2/http.html#transaction](https://www.hl7.org/fhir/DSTU2/http.html#transaction) 。</span><span class="sxs-lookup"><span data-stu-id="613d9-125">For more information and examples, see [https://www.hl7.org/fhir/DSTU2/http.html#transaction](https://www.hl7.org/fhir/DSTU2/http.html#transaction).</span></span>

<span data-ttu-id="613d9-126">所有以下 FHIR 资源应可通过直接资源参考访问。</span><span class="sxs-lookup"><span data-stu-id="613d9-126">All the following FHIR resources should be accessible by direct resource reference.</span></span>

## <a name="conformance-minimum-required-field-set"></a><span data-ttu-id="613d9-127">一致性最低要求字段集</span><span class="sxs-lookup"><span data-stu-id="613d9-127">Conformance minimum required field set</span></span>

 <span data-ttu-id="613d9-128">FHIR 服务器必须实现一致性声明，才能为我们提供其功能的实际摘要。</span><span class="sxs-lookup"><span data-stu-id="613d9-128">The FHIR Server must implement the conformance statement for us to have a factual summary of its capabilities.</span></span> <span data-ttu-id="613d9-129">我们期望 DSTU2 FHIR 服务器中的以下参数：</span><span class="sxs-lookup"><span data-stu-id="613d9-129">We expect the below parameters in a DSTU2 FHIR Server:</span></span>

1. <span data-ttu-id="613d9-130">余下</span><span class="sxs-lookup"><span data-stu-id="613d9-130">REST</span></span>
   1. <span data-ttu-id="613d9-131">众</span><span class="sxs-lookup"><span data-stu-id="613d9-131">Mode</span></span>
   2. <span data-ttu-id="613d9-132">相交</span><span class="sxs-lookup"><span data-stu-id="613d9-132">Interaction</span></span>
   3. <span data-ttu-id="613d9-133">资源：类型</span><span class="sxs-lookup"><span data-stu-id="613d9-133">Resource: Type</span></span>
   4. <span data-ttu-id="613d9-134">安全性： [OAuth uri 的扩展](https://hl7.org/fhir/extension-oauth-uris.html)</span><span class="sxs-lookup"><span data-stu-id="613d9-134">Security: [Extension for OAuth URIs](https://hl7.org/fhir/extension-oauth-uris.html)</span></span>
2. <span data-ttu-id="613d9-135">FhirVersion (我们的代码需要此内容，以了解我们支持多个版本时应透视到的版本。 ) </span><span class="sxs-lookup"><span data-stu-id="613d9-135">FhirVersion (Our code requires this to understand which version we should pivot to as we support multiple versions.)</span></span>

<span data-ttu-id="613d9-136">[https://www.hl7.org/fhir/dstu2/conformance.html](https://www.hl7.org/fhir/dstu2/conformance.html)有关此字段集的其他详细信息，请参阅。</span><span class="sxs-lookup"><span data-stu-id="613d9-136">See [https://www.hl7.org/fhir/dstu2/conformance.html](https://www.hl7.org/fhir/dstu2/conformance.html) for other details on this field set.</span></span>

## <a name="patient"></a><span data-ttu-id="613d9-137">档案</span><span class="sxs-lookup"><span data-stu-id="613d9-137">Patient</span></span>

<span data-ttu-id="613d9-138">以下是 " [Argonaut" 患者档案](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-patient.html) 字段子集的最少必填字段：</span><span class="sxs-lookup"><span data-stu-id="613d9-138">These are the minimum required fields, which are a subset of the [Argonaut patient profile](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-patient.html) fields:</span></span>

1. <span data-ttu-id="613d9-139">名称。家庭</span><span class="sxs-lookup"><span data-stu-id="613d9-139">Name.Family</span></span>
2. <span data-ttu-id="613d9-140">名称。给定</span><span class="sxs-lookup"><span data-stu-id="613d9-140">Name.Given</span></span>
3. <span data-ttu-id="613d9-141">性别</span><span class="sxs-lookup"><span data-stu-id="613d9-141">Gender</span></span>
4. <span data-ttu-id="613d9-142">BirthDate</span><span class="sxs-lookup"><span data-stu-id="613d9-142">BirthDate</span></span>
5. <span data-ttu-id="613d9-143">MRN (标识符) </span><span class="sxs-lookup"><span data-stu-id="613d9-143">MRN (Identifier)</span></span>

<span data-ttu-id="613d9-144">除了 Argonaut 字段，为患者应用提供出色的用户体验还会读取以下字段：</span><span class="sxs-lookup"><span data-stu-id="613d9-144">In addition to the Argonaut fields, for a great user experience the Patients app also reads the following fields:</span></span>

1. <span data-ttu-id="613d9-145">名称。使用</span><span class="sxs-lookup"><span data-stu-id="613d9-145">Name.Use</span></span>
2. <span data-ttu-id="613d9-146">名称。前缀</span><span class="sxs-lookup"><span data-stu-id="613d9-146">Name.Prefix</span></span>
3. <span data-ttu-id="613d9-147">CareProvider (对患者资源的此参考应包括以下示例中所示的显示字段。 ) </span><span class="sxs-lookup"><span data-stu-id="613d9-147">CareProvider (This reference on the Patient resource should include the display fields shown in the following example.)</span></span>

* * *

    <span data-ttu-id="613d9-148">请求：获取 <fhir-服务器>/Patient/<患者 id></span><span class="sxs-lookup"><span data-stu-id="613d9-148">Request: GET <fhir-server>/Patient/<patient-id></span></span>
    
    <span data-ttu-id="613d9-149">回复： {"resourceType"： "患者"，"id"： "<患者 id>"，。</span><span class="sxs-lookup"><span data-stu-id="613d9-149">Response: { "resourceType": "Patient", "id": "<patient-id>", .</span></span>
      <span data-ttu-id="613d9-150">.</span><span class="sxs-lookup"><span data-stu-id="613d9-150">.</span></span>
      <span data-ttu-id="613d9-151">.</span><span class="sxs-lookup"><span data-stu-id="613d9-151">.</span></span>
      <span data-ttu-id="613d9-152">"名称"： [{"使用"： "官方"，"prefix"： ["Mr"]，"family"： ["Chau"]，"Hugh"： [""]}]，"标识符"： [{"使用"： "官方"，"类型"： {"编码"： [{"system" https://hl7.org/fhir/v2/0203 ： "？"，"1234567"}]，"性别"： "男"，"出生日期"： "1957-06-05"，"careProvider"： [{"显示"： "Jane Doe"}]，}</span><span class="sxs-lookup"><span data-stu-id="613d9-152">"name": [ { "use": "official", "prefix": [ "Mr" ], "family": [ "Chau" ], "given": [ "Hugh" ] } ], "identifier": [ { "use": "official", "type": { "coding": [ { "system": "https://hl7.org/fhir/v2/0203", "code": "MR" } ] }, "value": "1234567" } ], "gender": "male", "birthDate": "1957-06-05", "careProvider": [{ "display": "Jane Doe" }], }</span></span>

* * *

<span data-ttu-id="613d9-153">资源搜索在/Patient/_search 使用 POST 方法，并使用以下参数：</span><span class="sxs-lookup"><span data-stu-id="613d9-153">A resource search uses the POST method at /Patient/_search and the following parameters:</span></span>

1. <span data-ttu-id="613d9-154">标识号</span><span class="sxs-lookup"><span data-stu-id="613d9-154">id</span></span>
2. <span data-ttu-id="613d9-155">系列：包含 = (搜索其系列名称包含值的所有患者。 ) </span><span class="sxs-lookup"><span data-stu-id="613d9-155">family:contains=(searches for all patients whose family name contains the value.)</span></span>
3. <span data-ttu-id="613d9-156">给定 =\<substring></span><span class="sxs-lookup"><span data-stu-id="613d9-156">given=\<substring></span></span>
4. <span data-ttu-id="613d9-157">名称 =\<substring></span><span class="sxs-lookup"><span data-stu-id="613d9-157">name=\<substring></span></span>
5. <span data-ttu-id="613d9-158">出生日期 = (完全匹配) </span><span class="sxs-lookup"><span data-stu-id="613d9-158">birthdate=(exact match)</span></span>
6. <span data-ttu-id="613d9-159">\_计数 (应返回的最大结果数) </span><span class="sxs-lookup"><span data-stu-id="613d9-159">\_count (maximum number of results that should be returned)</span></span> <br> <span data-ttu-id="613d9-160">该响应应包含作为搜索结果返回的记录的总数， \_ PatientsApp 将使用该计数来限制返回的记录数。</span><span class="sxs-lookup"><span data-stu-id="613d9-160">The response should contain the total count of records returned as a result of the search, and \_count will be used by the PatientsApp to limit the number of records returned.</span></span>
7. <span data-ttu-id="613d9-161">标识符 =\<mrn></span><span class="sxs-lookup"><span data-stu-id="613d9-161">identifier=\<mrn></span></span>

<span data-ttu-id="613d9-162">目标是能够搜索和筛选患者，如下所示：</span><span class="sxs-lookup"><span data-stu-id="613d9-162">The goal is to be able to search and filter for a patient by the following:</span></span>

- <span data-ttu-id="613d9-163">ID：这是 FHIR 中的每个资源具有的资源 ID。</span><span class="sxs-lookup"><span data-stu-id="613d9-163">ID: This is the resource ID that every resource in FHIR has.</span></span>
- <span data-ttu-id="613d9-164">MRN：这是临床人员将知道的患者的实际标识符。</span><span class="sxs-lookup"><span data-stu-id="613d9-164">MRN: This is the actual identifier for the patient that clinical staff would know.</span></span> <span data-ttu-id="613d9-165">我们理解此 MRN 基于 FHIR 中的标识符资源内的标识符类型</span><span class="sxs-lookup"><span data-stu-id="613d9-165">We understand this MRN is based on the type of identifier inside the identifier resource in FHIR</span></span>
- <span data-ttu-id="613d9-166">名称</span><span class="sxs-lookup"><span data-stu-id="613d9-166">Name</span></span>
- <span data-ttu-id="613d9-167">Birthdate</span><span class="sxs-lookup"><span data-stu-id="613d9-167">Birthdate</span></span>

<span data-ttu-id="613d9-168">请参阅下面的此通话示例。</span><span class="sxs-lookup"><span data-stu-id="613d9-168">See the following example  of this call.</span></span>

* * *

    <span data-ttu-id="613d9-169">请求： POST <fhir-server>/Patient/_search 请求正文：给定 = hugh&家族 = chau</span><span class="sxs-lookup"><span data-stu-id="613d9-169">Request: POST <fhir-server>/Patient/_search Request Body: given=hugh&family=chau</span></span>
    
    <span data-ttu-id="613d9-170">响应： {"resourceType"： "捆绑包"，"id"： "<捆绑包-id>"，。</span><span class="sxs-lookup"><span data-stu-id="613d9-170">Response: { "resourceType": "Bundle", "id": "<bundle-id>", .</span></span>
      <span data-ttu-id="613d9-171">.</span><span class="sxs-lookup"><span data-stu-id="613d9-171">.</span></span>
      <span data-ttu-id="613d9-172">.</span><span class="sxs-lookup"><span data-stu-id="613d9-172">.</span></span>
      <span data-ttu-id="613d9-173">"entry"： [{"资源"： {"resourceType"： "患者"，"id"： "<患者 id>"，"名称"： [{"文本"： "Hugh Chau"，"family"： ["Hugh"]，""： [""]}]，"性别"： "男"，"出生日期"： "1957-06-05</span><span class="sxs-lookup"><span data-stu-id="613d9-173">"entry": [ { "resource": { "resourceType": "Patient", "id": "<patient-id>", "name": [ { "text": "Hugh Chau", "family": [ "Chau" ], "given": [ "Hugh" ] } ], "gender": "male", "birthDate": "1957-06-05" }, "search": { "mode": "match" } } ] }</span></span>

* * *

<span data-ttu-id="613d9-174">[https://www.hl7.org/fhir/DSTU2/Patient.html](https://www.hl7.org/fhir/DSTU2/Patient.html)有关此字段集的其他详细信息，请参阅。</span><span class="sxs-lookup"><span data-stu-id="613d9-174">See [https://www.hl7.org/fhir/DSTU2/Patient.html](https://www.hl7.org/fhir/DSTU2/Patient.html) for other details on this field set.</span></span>

## <a name="observation"></a><span data-ttu-id="613d9-175">知识产权</span><span class="sxs-lookup"><span data-stu-id="613d9-175">Observation</span></span>

<span data-ttu-id="613d9-176">以下是最少的必填字段，这些字段是 Argonaut 的重要符号配置文件的子集：</span><span class="sxs-lookup"><span data-stu-id="613d9-176">These are the minimum required fields, which are a subset of the Argonaut vital signs profile:</span></span>

 1. <span data-ttu-id="613d9-177">有效 (日期时间或期间) </span><span class="sxs-lookup"><span data-stu-id="613d9-177">Effective (date time or period)</span></span>
 2. <span data-ttu-id="613d9-178">编码代码</span><span class="sxs-lookup"><span data-stu-id="613d9-178">Code.Coding.Code</span></span>
 3. <span data-ttu-id="613d9-179">ValueQuantity 值</span><span class="sxs-lookup"><span data-stu-id="613d9-179">ValueQuantity.Value</span></span>

<span data-ttu-id="613d9-180">除了 Argonaut 字段，为患者应用提供出色的用户体验还会读取以下字段：</span><span class="sxs-lookup"><span data-stu-id="613d9-180">In addition to the Argonaut fields, for a great user experience the Patients app also reads the following fields:</span></span>

 1. <span data-ttu-id="613d9-181">代码编码。显示</span><span class="sxs-lookup"><span data-stu-id="613d9-181">Code.Coding.Display</span></span>
 2. <span data-ttu-id="613d9-182">ValueQuantity 单位</span><span class="sxs-lookup"><span data-stu-id="613d9-182">ValueQuantity.Unit</span></span>

<span data-ttu-id="613d9-183">如果使用组件观测值，则相同的逻辑适用于每个组件观察。</span><span class="sxs-lookup"><span data-stu-id="613d9-183">If using component observations, the same logic applies for each component observation.</span></span>

<span data-ttu-id="613d9-184">资源搜索使用 GET 方法和以下参数：</span><span class="sxs-lookup"><span data-stu-id="613d9-184">A resource search uses the GET method and the following parameters:</span></span>

1. <span data-ttu-id="613d9-185">患者 =\<patient id\></span><span class="sxs-lookup"><span data-stu-id="613d9-185">patient=\<patient id\></span></span>
2. <span data-ttu-id="613d9-186">排序： desc =\<field ex. date\></span><span class="sxs-lookup"><span data-stu-id="613d9-186">sort:desc=\<field ex. date\></span></span>

<span data-ttu-id="613d9-187">目标是能够检索患者的最新重要标志 [VitalSigns] (观察？ ) 。</span><span class="sxs-lookup"><span data-stu-id="613d9-187">The goal is to be able to retrieve the latest vital signs for a patient, [VitalSigns.DSTU.saz]  (observation?).</span></span>

* * *

    <span data-ttu-id="613d9-188">请求：获取 <fhir-服务器>/Observation？患者 =<患者 id>&_sort:d esc = 日期&category = 重要标志</span><span class="sxs-lookup"><span data-stu-id="613d9-188">Request: GET <fhir-server>/Observation?patient=<patient-id>&_sort:desc=date&category=vital-signs</span></span>
    
    <span data-ttu-id="613d9-189">响应： {"resourceType"： "捆绑包"，"id"： "<捆绑包-id>"，"键入"： "searchset"，"total"：20，"entry"： [{"resource"： "<资源 id>"，"类别"： {"编码"： [{code "：" 关键签名 "}]，}，" code "： {" 编码 "： [{" system "：" http://loinc.org "，" 代码 "：" 39156-5 "，" display "：" bmi "}]，}，" effectiveDateTime "：" 2009-12-01 "，" valueQuantity "： {" 值 "：34.4，" unit "：" 公斤/m2 "，" system "：" http://unitsofmeasure.org "，" 代码 "：" 公斤/m2 "}}，}。</span><span class="sxs-lookup"><span data-stu-id="613d9-189">Response: { "resourceType": "Bundle", "id": "<bundle-id>", "type": "searchset", "total": 20, "entry": [ { "resource": { "resourceType": "Observation", "id": "<resource-id>", "category": { "coding": [ { code": "vital-signs" } ], }, "code": { "coding": [ { "system": "http://loinc.org", "code": "39156-5", "display": "bmi" } ], }, "effectiveDateTime": "2009-12-01", "valueQuantity": { "value": 34.4, "unit": "kg/m2", "system": "http://unitsofmeasure.org", "code": "kg/m2" } }, }, .</span></span>
        <span data-ttu-id="613d9-190">.</span><span class="sxs-lookup"><span data-stu-id="613d9-190">.</span></span>
        <span data-ttu-id="613d9-191">.</span><span class="sxs-lookup"><span data-stu-id="613d9-191">.</span></span>
      <span data-ttu-id="613d9-192">] }</span><span class="sxs-lookup"><span data-stu-id="613d9-192">] }</span></span>

* * *

<span data-ttu-id="613d9-193">[https://www.hl7.org/fhir/DSTU2/Observation.html](https://www.hl7.org/fhir/DSTU2/Observation.html)有关此字段集的其他详细信息，请参阅。</span><span class="sxs-lookup"><span data-stu-id="613d9-193">See [https://www.hl7.org/fhir/DSTU2/Observation.html](https://www.hl7.org/fhir/DSTU2/Observation.html) for other details on this field set.</span></span>

## <a name="condition"></a><span data-ttu-id="613d9-194">条件</span><span class="sxs-lookup"><span data-stu-id="613d9-194">Condition</span></span>

<span data-ttu-id="613d9-195">下面是 [Argonaut 条件配置文件](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-condition.html)子集的最少必填字段：</span><span class="sxs-lookup"><span data-stu-id="613d9-195">These are the minimum required fields, which are a subset of the [Argonaut condition profile](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-condition.html):</span></span>

1. <span data-ttu-id="613d9-196">代码。编码 [0]。画面</span><span class="sxs-lookup"><span data-stu-id="613d9-196">Code.Coding[0].Display</span></span>

<span data-ttu-id="613d9-197">除了 Argonaut 字段外，还可以为患者应用提供出色的用户体验，还可以读取以下字段：</span><span class="sxs-lookup"><span data-stu-id="613d9-197">In addition to the Argonaut fields, for a great user experience the Patients app can also read the following fields:</span></span>

1. <span data-ttu-id="613d9-198">录制日期</span><span class="sxs-lookup"><span data-stu-id="613d9-198">Date Recorded</span></span>
2. <span data-ttu-id="613d9-199">严重性</span><span class="sxs-lookup"><span data-stu-id="613d9-199">Severity</span></span>

<span data-ttu-id="613d9-200">资源搜索使用 GET 方法和以下参数：</span><span class="sxs-lookup"><span data-stu-id="613d9-200">A resource search uses the GET method and the following parameters:</span></span>

1. <span data-ttu-id="613d9-201">患者 =\<patient id></span><span class="sxs-lookup"><span data-stu-id="613d9-201">patient=\<patient id></span></span>
2. <span data-ttu-id="613d9-202">_count =\<max results></span><span class="sxs-lookup"><span data-stu-id="613d9-202">_count=\<max results></span></span>

<span data-ttu-id="613d9-203">请参阅下面的此呼叫示例：</span><span class="sxs-lookup"><span data-stu-id="613d9-203">See the following example of this call:</span></span>

* * *

    <span data-ttu-id="613d9-204">请求：获取 <fhir-服务器>/Condition？患者 =<患者 id>&_count = 10</span><span class="sxs-lookup"><span data-stu-id="613d9-204">Request: GET <fhir-server>/Condition?patient=<patient-id>&_count=10</span></span>
    
    <span data-ttu-id="613d9-205">响应： {"resourceType"： "捆绑包"，"id"> <： "searchset"： ""，"total"：1，"entry"： [{"资源"： {""： "Condition"，"id"： "<资源 id>"，"代码"： {"编码"： [{"系统"： " http://snomed.info/sct "，"代码"： "386033004"，"显示"： "Neuropathy (nerve 损坏) "}]}，"dateRecorded"： "2018-09-17"，"严重性"： {"编码"： [{"system"： " http://snomed.info/sct "，"代码"： "24484000"，"显示"： "严重"}]}}，}]}</span><span class="sxs-lookup"><span data-stu-id="613d9-205">Response: {   "resourceType": "Bundle",   "id": "<bundle-id>",   "type": "searchset",   "total": 1,   "entry": [     {       "resource": {         "resourceType": "Condition",         "id": "<resource-id>",         "code": {           "coding": [             {               "system": "http://snomed.info/sct",               "code": "386033004",               "display": "Neuropathy (nerve damage)"             }           ]         },         "dateRecorded": "2018-09-17",         "severity": {           "coding": [             {               "system": "http://snomed.info/sct",               "code": "24484000",               "display": "Severe"             }           ]         }       },     }   ] }</span></span>

* * *

<span data-ttu-id="613d9-206">[https://www.hl7.org/fhir/DSTU2/Condition.html](https://www.hl7.org/fhir/DSTU2/Condition.html)有关此字段集的其他详细信息，请参阅。</span><span class="sxs-lookup"><span data-stu-id="613d9-206">See [https://www.hl7.org/fhir/DSTU2/Condition.html](https://www.hl7.org/fhir/DSTU2/Condition.html) for other details on this field set.</span></span>

## <a name="encounter"></a><span data-ttu-id="613d9-207">产生</span><span class="sxs-lookup"><span data-stu-id="613d9-207">Encounter</span></span>

<span data-ttu-id="613d9-208">以下是最少必填字段，这些字段是 "美国核心" 基本配置文件 "必须具有" 字段的子集：</span><span class="sxs-lookup"><span data-stu-id="613d9-208">These are the minimum required fields, which are a subset of the US Core Encounter profile "must have" fields:</span></span>

1. <span data-ttu-id="613d9-209">状态栏</span><span class="sxs-lookup"><span data-stu-id="613d9-209">Status</span></span>
2. <span data-ttu-id="613d9-210">键入 [0]。编码 [0]。画面</span><span class="sxs-lookup"><span data-stu-id="613d9-210">Type[0].Coding[0].Display</span></span>

<span data-ttu-id="613d9-211">此外，美国核心的以下字段会遇到配置文件的 "必须支持" 字段</span><span class="sxs-lookup"><span data-stu-id="613d9-211">In addition, the following fields from US Core Encounter profile's "must support" fields</span></span>

1. <span data-ttu-id="613d9-212">句号。开始</span><span class="sxs-lookup"><span data-stu-id="613d9-212">Period.Start</span></span>
2. <span data-ttu-id="613d9-213">位置 [0]。位置。显示</span><span class="sxs-lookup"><span data-stu-id="613d9-213">Location[0].Location.Display</span></span>

<span data-ttu-id="613d9-214">资源搜索使用 GET 方法和以下参数：</span><span class="sxs-lookup"><span data-stu-id="613d9-214">A resource search uses the GET method and the following parameters:</span></span>

1. <span data-ttu-id="613d9-215">患者 =\<patient id></span><span class="sxs-lookup"><span data-stu-id="613d9-215">patient=\<patient id></span></span>
2. <span data-ttu-id="613d9-216">_sort： desc =\<field ex. date></span><span class="sxs-lookup"><span data-stu-id="613d9-216">_sort:desc=\<field ex. date></span></span>
3. <span data-ttu-id="613d9-217">_count =\<max results></span><span class="sxs-lookup"><span data-stu-id="613d9-217">_count=\<max results></span></span>

<span data-ttu-id="613d9-218">目标是能够检索患者的最后一个已知位置。</span><span class="sxs-lookup"><span data-stu-id="613d9-218">The goal is to be able to retrieve the patient's last known location.</span></span> <span data-ttu-id="613d9-219">每个遇到的都引用一个位置资源。</span><span class="sxs-lookup"><span data-stu-id="613d9-219">Each encounter references a location resource.</span></span> <span data-ttu-id="613d9-220">该引用还应包含位置的显示字段。</span><span class="sxs-lookup"><span data-stu-id="613d9-220">The reference shall also include the location's display field.</span></span> <span data-ttu-id="613d9-221">请参阅下面的此通话示例。</span><span class="sxs-lookup"><span data-stu-id="613d9-221">See the following example of this call.</span></span>
* * *

    <span data-ttu-id="613d9-222">请求：获取 <fhir-服务器>/Encounter？患者 =<患者 id>&_sort:d esc = 日期&_count = 1</span><span class="sxs-lookup"><span data-stu-id="613d9-222">Request: GET <fhir-server>/Encounter?patient=<patient-id>&_sort:desc=date&_count=1</span></span>
    
    <span data-ttu-id="613d9-223">响应： {"resourceType"： "捆绑包"，"类型"： "searchset"，"total"：1，"entry"： [{"id"： "" 遇到 ""，"id"： "<资源 id>"，"标识符"： [{"使用"： "官方"，"值"： " <id> "}]，"状态"： "已到达"，"类型"： [{"编码"： [{"显示"： "约会"}]，}]，"患者"： {"参考"： "患者/<患者 id>"}，"时间段"： {"start"： "09/17/2018 1:00:00 PM"}，"位置"： [{"位置"： {"display"： [{"位置"： {"display"： "ENT"}，}]}}]}</span><span class="sxs-lookup"><span data-stu-id="613d9-223">Response: {   "resourceType": "Bundle",   "type": "searchset",   "total": 1,   "entry": [     {       "resource": {         "resourceType": "Encounter",         "id": "<resource-id>",         "identifier": [{ "use": "official", "value": "<id>" }],         "status": "arrived",         "type": [           {             "coding": [{ "display": "Appointment" }],           }         ],         "patient": { "reference": "Patient/<patient-id>" },         "period": { "start": "09/17/2018 1:00:00 PM" },         "location": [           {             "location": { "display": "Clinic - ENT" },           }         ]       }     }   ] }</span></span>

* * *

<span data-ttu-id="613d9-224">[https://www.hl7.org/fhir/DSTU2/Encounter.htm](https://www.hl7.org/fhir/DSTU2/Encounter.htm)有关此字段集的其他详细信息，请参阅。</span><span class="sxs-lookup"><span data-stu-id="613d9-224">See [https://www.hl7.org/fhir/DSTU2/Encounter.htm](https://www.hl7.org/fhir/DSTU2/Encounter.htm) for other details on this field set.</span></span>

## <a name="allergyintolerance"></a><span data-ttu-id="613d9-225">AllergyIntolerance</span><span class="sxs-lookup"><span data-stu-id="613d9-225">AllergyIntolerance</span></span>

<span data-ttu-id="613d9-226">以下是最少的必填字段，它们是 Argonaut AllergyIntolerance 配置文件的子集：</span><span class="sxs-lookup"><span data-stu-id="613d9-226">These are the minimum required fields, which are a subset of the Argonaut AllergyIntolerance profile:</span></span>

1. <span data-ttu-id="613d9-227">代码。文本</span><span class="sxs-lookup"><span data-stu-id="613d9-227">Code.Text</span></span>
2. <span data-ttu-id="613d9-228">代码。编码 [0]。画面</span><span class="sxs-lookup"><span data-stu-id="613d9-228">Code.Coding[0].Display</span></span>
3. <span data-ttu-id="613d9-229">状态栏</span><span class="sxs-lookup"><span data-stu-id="613d9-229">Status</span></span>

<span data-ttu-id="613d9-230">除了 Argonaut 字段，为患者应用提供出色的用户体验还会读取以下字段：</span><span class="sxs-lookup"><span data-stu-id="613d9-230">In addition to the Argonaut fields, for a great user experience the Patients app also reads the following fields:</span></span>

1. <span data-ttu-id="613d9-231">RecordedDate</span><span class="sxs-lookup"><span data-stu-id="613d9-231">RecordedDate</span></span>
2. <span data-ttu-id="613d9-232">备注。文本</span><span class="sxs-lookup"><span data-stu-id="613d9-232">Note.Text</span></span>
3. <span data-ttu-id="613d9-233">反应 [...]。物质。文本</span><span class="sxs-lookup"><span data-stu-id="613d9-233">Reaction[..].Substance.Text</span></span>
4. <span data-ttu-id="613d9-234">反应 [...]。表现形式 [...]。文本</span><span class="sxs-lookup"><span data-stu-id="613d9-234">Reaction[..].Manifestation[..].Text</span></span>
5. <span data-ttu-id="613d9-235">文本 Div</span><span class="sxs-lookup"><span data-stu-id="613d9-235">Text.Div</span></span>

<span data-ttu-id="613d9-236">资源搜索使用 GET 方法和以下参数：</span><span class="sxs-lookup"><span data-stu-id="613d9-236">A resource search uses the GET method and the following parameters:</span></span>

1. <span data-ttu-id="613d9-237">患者 =  \<patient id></span><span class="sxs-lookup"><span data-stu-id="613d9-237">Patient =  \<patient id></span></span>

<span data-ttu-id="613d9-238">请参阅下面的此呼叫示例：</span><span class="sxs-lookup"><span data-stu-id="613d9-238">See the following example of this call:</span></span>

* * *

    <span data-ttu-id="613d9-239">请求：获取 <fhir-服务器>/AllergyIntolerance？患者 =<患者 id></span><span class="sxs-lookup"><span data-stu-id="613d9-239">Request: GET <fhir-server>/AllergyIntolerance?patient=<patient-id></span></span>
    
    <span data-ttu-id="613d9-240">响应： {"resourceType"： "捆绑包"，"id"> <： "searchset"： ""，"total"：1，"entry"： [{"资源"： {"resourceType"： "AllergyIntolerance"，"id"： "<资源 id>"，"recordedDate"： "2018 日-17T07：00： 00.000 Z"，"物质"： {"text"： "Cashew 螺母"}，"status"： "已确认"，"反应"： [{"物质"： {"文本"： "Cashew 螺母 allergenic 提取 Injectable 产品"}，"表现形式"： [{"文本"： "Anaphylactic 反应"}]}]}</span><span class="sxs-lookup"><span data-stu-id="613d9-240">Response: {   "resourceType": "Bundle",   "id": "<bundle-id>",   "type": "searchset",   "total": 1,   "entry": [     {       "resource": {         "resourceType": "AllergyIntolerance",         "id": "<resource-id>",         "recordedDate": "2018-09-17T07:00:00.000Z",         "substance": {           "text": "Cashew nuts"         },         "status": "confirmed",         "reaction": [           {             "substance": {               "text": "cashew nut allergenic extract Injectable Product"             },             "manifestation": [               {                 "text": "Anaphylactic reaction"               }             ]           }         ]       }     }   ] }</span></span>

* * *

<span data-ttu-id="613d9-241">[https://www.hl7.org/fhir/DSTU2/AllergyIntolerance.html](https://www.hl7.org/fhir/DSTU2/AllergyIntolerance.html)有关此字段集的其他详细信息，请参阅。</span><span class="sxs-lookup"><span data-stu-id="613d9-241">See [https://www.hl7.org/fhir/DSTU2/AllergyIntolerance.html](https://www.hl7.org/fhir/DSTU2/AllergyIntolerance.html) for other details on this field set.</span></span>

## <a name="medication-order"></a><span data-ttu-id="613d9-242">药物订货</span><span class="sxs-lookup"><span data-stu-id="613d9-242">Medication Order</span></span>

<span data-ttu-id="613d9-243">以下是最少的必填字段，它们是 Argonaut MedicationOrder 配置文件的子集：</span><span class="sxs-lookup"><span data-stu-id="613d9-243">These are the minimum required fields, which are a subset of the Argonaut MedicationOrder profile:</span></span>

1. <span data-ttu-id="613d9-244">DateWritten</span><span class="sxs-lookup"><span data-stu-id="613d9-244">DateWritten</span></span>
2. <span data-ttu-id="613d9-245">Prescriber 显示</span><span class="sxs-lookup"><span data-stu-id="613d9-245">Prescriber.Display</span></span>
3. <span data-ttu-id="613d9-246">药物。如果引用) ，则显示 (</span><span class="sxs-lookup"><span data-stu-id="613d9-246">Medication.Display (if reference)</span></span>
4. <span data-ttu-id="613d9-247"> () 概念的 "药物" 文本</span><span class="sxs-lookup"><span data-stu-id="613d9-247">Medication.Text (if concept)</span></span>

<span data-ttu-id="613d9-248">除了 Argonaut 字段外，还可以为患者应用提供出色的用户体验，还可以读取以下字段：</span><span class="sxs-lookup"><span data-stu-id="613d9-248">In addition to the Argonaut fields, for a great user experience the Patients app can also read the following fields:</span></span>

1. <span data-ttu-id="613d9-249">DateEnded</span><span class="sxs-lookup"><span data-stu-id="613d9-249">DateEnded</span></span>
2. <span data-ttu-id="613d9-250">DosageInstruction</span><span class="sxs-lookup"><span data-stu-id="613d9-250">DosageInstruction.Text</span></span>
3. <span data-ttu-id="613d9-251">文本 Div</span><span class="sxs-lookup"><span data-stu-id="613d9-251">Text.Div</span></span>

<span data-ttu-id="613d9-252">资源搜索使用 GET 方法和以下参数：</span><span class="sxs-lookup"><span data-stu-id="613d9-252">A resource search uses the GET method and the following parameters:</span></span>

1. <span data-ttu-id="613d9-253">患者 =\<patient id></span><span class="sxs-lookup"><span data-stu-id="613d9-253">patient=\<patient id></span></span>
2. <span data-ttu-id="613d9-254">_count =\<max results></span><span class="sxs-lookup"><span data-stu-id="613d9-254">_count=\<max results></span></span>

<span data-ttu-id="613d9-255">请参阅下面的此呼叫示例：</span><span class="sxs-lookup"><span data-stu-id="613d9-255">See the following example of this call:</span></span>

* * *

    <span data-ttu-id="613d9-256">请求：获取 <fhir-服务器>/MedicationOrder？患者 =<患者 id>&_count = 10</span><span class="sxs-lookup"><span data-stu-id="613d9-256">Request: GET <fhir-server>/MedicationOrder?patient=<patient-id>&_count=10</span></span>
    
    <span data-ttu-id="613d9-257">响应： {"resourceType"： "捆绑包"，"id"： "<捆绑包-id>"，"type"： "searchset"，"total"：1，"entry"： [{"资源"： {"resourceType"： "MedicationOrder"，"id"： "<资源 id>"，"dateWritten"： "2018-09-17"，"medicationCodeableConcept"： {"text"： "Lisinopril 20 MG 平板电脑"}，"prescriber"： {"display"： "Jane Doe"}，"dosageInstruction"： [{"文本"： "1 天"}]}}]}</span><span class="sxs-lookup"><span data-stu-id="613d9-257">Response: {   "resourceType": "Bundle",   "id": "<bundle-id>",   "type": "searchset",   "total": 1,   "entry": [     {       "resource": {         "resourceType": "MedicationOrder",         "id": "<resource-id>",         "dateWritten": "2018-09-17",         "medicationCodeableConcept": {           "text": "Lisinopril 20 MG Oral Tablet"         },         "prescriber": {           "display": "Jane Doe"         },         "dosageInstruction": [           {             "text": "1 daily"           }         ]       }     }   ] }</span></span>

* * *  

<span data-ttu-id="613d9-258">[https://www.hl7.org/fhir/DSTU2/MedicationOrder.html](https://www.hl7.org/fhir/DSTU2/MedicationOrder.html)有关此字段集的其他详细信息，请参阅。</span><span class="sxs-lookup"><span data-stu-id="613d9-258">See [https://www.hl7.org/fhir/DSTU2/MedicationOrder.html](https://www.hl7.org/fhir/DSTU2/MedicationOrder.html) for other details on this field set.</span></span>

## <a name="coverage"></a><span data-ttu-id="613d9-259">内</span><span class="sxs-lookup"><span data-stu-id="613d9-259">Coverage</span></span>

<span data-ttu-id="613d9-260">以下是 "最少必填字段"，不包含在美国 Core 或 Argonaut 配置文件中：</span><span class="sxs-lookup"><span data-stu-id="613d9-260">These are the minimum required fields, not covered by either US Core or Argonaut profiles:</span></span>

1. <span data-ttu-id="613d9-261">Payor</span><span class="sxs-lookup"><span data-stu-id="613d9-261">Payor</span></span>

<span data-ttu-id="613d9-262">资源搜索使用 GET 方法和以下参数：</span><span class="sxs-lookup"><span data-stu-id="613d9-262">A resource search uses the GET method and the following parameters:</span></span>

1. <span data-ttu-id="613d9-263">患者 =\<patient id></span><span class="sxs-lookup"><span data-stu-id="613d9-263">patient=\<patient id></span></span>

<span data-ttu-id="613d9-264">请参阅下面的此呼叫示例：</span><span class="sxs-lookup"><span data-stu-id="613d9-264">See the following example of this call:</span></span>

* * *

    <span data-ttu-id="613d9-265">请求：获取 <fhir-服务器>/Coverage？患者 =<患者 id></span><span class="sxs-lookup"><span data-stu-id="613d9-265">Request: GET <fhir-server>/Coverage?patient=<patient-id></span></span>
    
    <span data-ttu-id="613d9-266">响应： {"resourceType"： "捆绑包"，"键入"： "searchset"，"total"：1，"entry"： [{"resource"： "<资源 id>"，"计划"： "没有主保险"，"订阅"： {"reference"： "患者/<患者 id>"}}]}</span><span class="sxs-lookup"><span data-stu-id="613d9-266">Response: {   "resourceType": "Bundle",   "type": "searchset",   "total": 1,   "entry": [     {       "resource": {         "resourceType": "Coverage",         "id": "<resource-id>",         "plan": "No Primary Insurance",         "subscriber": { "reference": "Patient/<patient-id>" }       }     }   ] }</span></span>

* * *

<span data-ttu-id="613d9-267">[https://www.hl7.org/fhir/DSTU2/Coverage.html](https://www.hl7.org/fhir/DSTU2/Coverage.html)有关此字段集的其他详细信息，请参阅。</span><span class="sxs-lookup"><span data-stu-id="613d9-267">See [https://www.hl7.org/fhir/DSTU2/Coverage.html](https://www.hl7.org/fhir/DSTU2/Coverage.html) for other details on this field set.</span></span>

## <a name="location"></a><span data-ttu-id="613d9-268">位置</span><span class="sxs-lookup"><span data-stu-id="613d9-268">Location</span></span>

<span data-ttu-id="613d9-269">此资源仅用作 " [遇到](#encounter) " 资源的参考。</span><span class="sxs-lookup"><span data-stu-id="613d9-269">This resource is only being used as a reference on the [Encounter](#encounter) resource.</span></span>

<span data-ttu-id="613d9-270">[https://www.hl7.org/fhir/DSTU2/Location.html](https://www.hl7.org/fhir/DSTU2/Location.html)有关此字段集的其他详细信息，请参阅。</span><span class="sxs-lookup"><span data-stu-id="613d9-270">See [https://www.hl7.org/fhir/DSTU2/Location.html](https://www.hl7.org/fhir/DSTU2/Location.html) for other details on this field set.</span></span>
