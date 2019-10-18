---
title: 患者应用和 EHR 集成 STU3 界面
author: jambirk
ms.author: jambirk
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
search.appverid: MET150
localization_priority: Normal
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Healthcare
appliesto:
- Microsoft Teams
ms.reviewer: anach
description: Microsoft 团队患者应用 EHR 集成
ms.openlocfilehash: 836c28f339a3936f03315b005c0eedfc49e0f2ba
ms.sourcegitcommit: 0dcd078947a455a388729fd50c7a939dd93b0b61
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2019
ms.locfileid: "37569239"
---
# <a name="stu3-interface-specification"></a><span data-ttu-id="7066e-103">STU3 接口规范</span><span class="sxs-lookup"><span data-stu-id="7066e-103">STU3 interface specification</span></span>

[!INCLUDE [preview-feature](../../includes/preview-feature.md)]

<span data-ttu-id="7066e-104">设置或重新配置 FHIR 服务器以处理 Microsoft 团队患者应用需要了解应用需要访问的数据。</span><span class="sxs-lookup"><span data-stu-id="7066e-104">Setting up or reconfiguring an FHIR server to work with the Microsoft Teams Patients app requires understanding what data the app needs to access.</span></span> <span data-ttu-id="7066e-105">FHIR 服务器必须使用以下资源的捆绑包支持发布请求：</span><span class="sxs-lookup"><span data-stu-id="7066e-105">The FHIR server must support POST requests using bundles for the following resources:</span></span>

- [<span data-ttu-id="7066e-106">档案</span><span class="sxs-lookup"><span data-stu-id="7066e-106">Patient</span></span>](#patient)
- [<span data-ttu-id="7066e-107">知识产权</span><span class="sxs-lookup"><span data-stu-id="7066e-107">Observation</span></span>](#observation)
- [<span data-ttu-id="7066e-108">条件</span><span class="sxs-lookup"><span data-stu-id="7066e-108">Condition</span></span>](#condition)
- [<span data-ttu-id="7066e-109">产生</span><span class="sxs-lookup"><span data-stu-id="7066e-109">Encounter</span></span>](#encounter)
- [<span data-ttu-id="7066e-110">过敏症 Intolerance</span><span class="sxs-lookup"><span data-stu-id="7066e-110">Allergy Intolerance</span></span>](#allergyintolerance)
- [<span data-ttu-id="7066e-111">内</span><span class="sxs-lookup"><span data-stu-id="7066e-111">Coverage</span></span>](#coverage)
- <span data-ttu-id="7066e-112">[药物对帐单](#medication-request)（替换 PATIENTSAPP 的 DSTU2 版本中的 MedicationOrder）</span><span class="sxs-lookup"><span data-stu-id="7066e-112">[Medication Statement](#medication-request) (replaces the MedicationOrder in the DSTU2 version of the PatientsApp)</span></span>
- <span data-ttu-id="7066e-113">位置（可能会包含此资源所需的信息）</span><span class="sxs-lookup"><span data-stu-id="7066e-113">Location (the information needed from this resource can be included in Encounter)</span></span>

> [!NOTE]
> <span data-ttu-id="7066e-114">患者资源是唯一必需的资源（根本不会加载应用）;但是，建议合作伙伴针对 Microsoft 团队患者应用的最佳最终用户体验，针对以下提供的针对以上提及的所有资源提供支持。</span><span class="sxs-lookup"><span data-stu-id="7066e-114">The Patient resource is the only mandatory resource (without which the app will not load at all); However, it is recommended that the Partner implement support for all the above mentioned resources per specifications provided below for the best end-user experience with the Microsoft Teams Patients App.</span></span>

<span data-ttu-id="7066e-115">来自 Microsoft 团队患者应用的来自多个资源的查询将向 FHIR 服务器的 URL 发布请求的捆绑（批处理）。</span><span class="sxs-lookup"><span data-stu-id="7066e-115">Queries from the Microsoft Teams Patients app for more than one resource shall post a bundle (BATCH) of requests to the FHIR server's URL.</span></span> <span data-ttu-id="7066e-116">服务器应对每个请求进行处理，并返回每个请求所匹配的资源的捆绑包。</span><span class="sxs-lookup"><span data-stu-id="7066e-116">The server shall process each request and return a bundle of the resources matched by each request.</span></span> <span data-ttu-id="7066e-117">有关详细信息和示例，请[https://www.hl7.org/fhir/STU3/http.html#transaction](https://www.hl7.org/fhir/STU3/http.html#transaction)参阅。</span><span class="sxs-lookup"><span data-stu-id="7066e-117">For more information and examples, see [https://www.hl7.org/fhir/STU3/http.html#transaction](https://www.hl7.org/fhir/STU3/http.html#transaction).</span></span>

## <a name="capability-statement"></a><span data-ttu-id="7066e-118">功能陈述</span><span class="sxs-lookup"><span data-stu-id="7066e-118">Capability Statement</span></span>

<span data-ttu-id="7066e-119">以下是最少的必填字段：</span><span class="sxs-lookup"><span data-stu-id="7066e-119">These are the minimum required fields:</span></span>

1. <span data-ttu-id="7066e-120">余下</span><span class="sxs-lookup"><span data-stu-id="7066e-120">REST</span></span>
   1. <span data-ttu-id="7066e-121">众</span><span class="sxs-lookup"><span data-stu-id="7066e-121">Mode</span></span>
   2. <span data-ttu-id="7066e-122">相交</span><span class="sxs-lookup"><span data-stu-id="7066e-122">Interaction</span></span>
   3. <span data-ttu-id="7066e-123">资源：类型</span><span class="sxs-lookup"><span data-stu-id="7066e-123">Resource: Type</span></span>
   4. <span data-ttu-id="7066e-124">安全性： [OAuth uri 的扩展](http://hl7.org/fhir/extension-oauth-uris.html)</span><span class="sxs-lookup"><span data-stu-id="7066e-124">Security: [Extension for OAuth URIs](http://hl7.org/fhir/extension-oauth-uris.html)</span></span>
2. <span data-ttu-id="7066e-125">FhirVersion （我们的代码需要此内容才能了解应将数据透视到哪一个版本。）</span><span class="sxs-lookup"><span data-stu-id="7066e-125">FhirVersion (Our code requires this to understand which version we should pivot to.)</span></span>

<span data-ttu-id="7066e-126">有关[https://www.hl7.org/fhir/stu3/capabilitystatement.html](https://www.hl7.org/fhir/stu3/capabilitystatement.html)此字段集的其他详细信息，请参阅。</span><span class="sxs-lookup"><span data-stu-id="7066e-126">See [https://www.hl7.org/fhir/stu3/capabilitystatement.html](https://www.hl7.org/fhir/stu3/capabilitystatement.html) for other details on this field set.</span></span>

## <a name="patient"></a><span data-ttu-id="7066e-127">档案</span><span class="sxs-lookup"><span data-stu-id="7066e-127">Patient</span></span>

<span data-ttu-id="7066e-128">下面是 "Argonaut" 患者档案字段子集的最少必填字段：</span><span class="sxs-lookup"><span data-stu-id="7066e-128">Here are the minimum required fields, which are a subset of the Argonaut patient profile fields:</span></span>

1. <span data-ttu-id="7066e-129">名称。给定</span><span class="sxs-lookup"><span data-stu-id="7066e-129">Name.Given</span></span>
2. <span data-ttu-id="7066e-130">名称。家庭</span><span class="sxs-lookup"><span data-stu-id="7066e-130">Name.Family</span></span>
3. <span data-ttu-id="7066e-131">性别</span><span class="sxs-lookup"><span data-stu-id="7066e-131">Gender</span></span>
4. <span data-ttu-id="7066e-132">BirthDate</span><span class="sxs-lookup"><span data-stu-id="7066e-132">BirthDate</span></span>
5. <span data-ttu-id="7066e-133">MRN （标识符）</span><span class="sxs-lookup"><span data-stu-id="7066e-133">MRN (Identifier)</span></span>

<span data-ttu-id="7066e-134">除了[Argonaut 字段](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-patient.html)外，还可以为患者应用提供出色的用户体验，还可以读取以下字段：</span><span class="sxs-lookup"><span data-stu-id="7066e-134">In addition to the [Argonaut fields](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-patient.html), for a great user experience the Patients app can also read the following fields:</span></span>

1. <span data-ttu-id="7066e-135">名称。使用</span><span class="sxs-lookup"><span data-stu-id="7066e-135">Name.Use</span></span>
2. <span data-ttu-id="7066e-136">名称。前缀</span><span class="sxs-lookup"><span data-stu-id="7066e-136">Name.Prefix</span></span>
3. <span data-ttu-id="7066e-137">[GeneralPractitioner]-GeneralPractitioner 参考应包括在患者资源中（仅显示字段）</span><span class="sxs-lookup"><span data-stu-id="7066e-137">[GeneralPractitioner] - The GeneralPractitioner reference should be included in the Patient resource (display field only)</span></span>

<span data-ttu-id="7066e-138">资源搜索在/Patient/_search 和以下参数中使用 POST 方法：</span><span class="sxs-lookup"><span data-stu-id="7066e-138">A resource search uses the POST method at /Patient/_search and the following parameters:</span></span>

1. <span data-ttu-id="7066e-139">标识号</span><span class="sxs-lookup"><span data-stu-id="7066e-139">id</span></span>
2. <span data-ttu-id="7066e-140">系列 = （搜索其系列名称包含该值的所有患者）</span><span class="sxs-lookup"><span data-stu-id="7066e-140">family=(searches for all patients whose family name contains the value)</span></span>
3. <span data-ttu-id="7066e-141">给定 =\<substring></span><span class="sxs-lookup"><span data-stu-id="7066e-141">given=\<substring></span></span>
4. <span data-ttu-id="7066e-142">出生日期 = （完全匹配）</span><span class="sxs-lookup"><span data-stu-id="7066e-142">birthdate=(exact match)</span></span>
5. <span data-ttu-id="7066e-143">性别 = （值为管理性别之一）</span><span class="sxs-lookup"><span data-stu-id="7066e-143">gender=(values being one of the administrative-gender)</span></span>
6. <span data-ttu-id="7066e-144">\_计数（应返回的最大结果数）</span><span class="sxs-lookup"><span data-stu-id="7066e-144">\_count (maximum number of results that should be returned)</span></span> <br> <span data-ttu-id="7066e-145">该响应应包含作为搜索和\_计数的结果返回的记录总数，PatientsApp 将使用该计数来限制返回的记录数。</span><span class="sxs-lookup"><span data-stu-id="7066e-145">The response should contain the total count of records returned as a result of the search and \_count will be used by the PatientsApp to limit the number of records returned.</span></span>
7. <span data-ttu-id="7066e-146">标识符 =\<mrn></span><span class="sxs-lookup"><span data-stu-id="7066e-146">identifier=\<mrn></span></span>

<span data-ttu-id="7066e-147">目标是能够搜索和筛选患者，如下所示：</span><span class="sxs-lookup"><span data-stu-id="7066e-147">The goal is to be able to search and filter for a patient by the following:</span></span>

- <span data-ttu-id="7066e-148">ID：这是 FHIR 中的每个资源具有的资源 ID。</span><span class="sxs-lookup"><span data-stu-id="7066e-148">ID: This is the resource ID that every resource in FHIR has.</span></span>
- <span data-ttu-id="7066e-149">MRN：这是临床人员将知道的患者的实际标识符。</span><span class="sxs-lookup"><span data-stu-id="7066e-149">MRN: This is the actual identifier for the patient that clinical staff would know.</span></span> <span data-ttu-id="7066e-150">我们理解此 MRN 基于 FHIR 中的标识符资源内的标识符类型。</span><span class="sxs-lookup"><span data-stu-id="7066e-150">We understand this MRN is based on the type of identifier inside the identifier resource in FHIR.</span></span>
- <span data-ttu-id="7066e-151">名称</span><span class="sxs-lookup"><span data-stu-id="7066e-151">Name</span></span>
- <span data-ttu-id="7066e-152">Birthdate</span><span class="sxs-lookup"><span data-stu-id="7066e-152">Birthdate</span></span>

<span data-ttu-id="7066e-153">请参阅下面的通话示例：</span><span class="sxs-lookup"><span data-stu-id="7066e-153">See the following example of the call:</span></span>

* * *

    <span data-ttu-id="7066e-154">请求： POST <fhir-server>/Patient/_search 请求正文：给定 = ruth&系列 = 黑色</span><span class="sxs-lookup"><span data-stu-id="7066e-154">Request: POST <fhir-server>/Patient/_search Request Body: given=ruth&family=black</span></span>
    
    <span data-ttu-id="7066e-155">响应： {"resourceType"： "捆绑包"，"id"： "<捆绑包-id>"，"meta"： {"lastUpdated"： "2019-01-" type "：" searchset "，" total "：1，" link "： [{" relation "：" self "，" url "： <fhir-服务器>/Patient/_search"}]，"entry"： [{"fullUrl "： <fhir-server>/Patient/<患者 id>"，"资源"： {"resourceType"： "病人"，"id"： "<病人 id>"，"meta"： {"versionId"： "1"，"lastUpdated"： "2017-10-18T18：32： 37.000 + 00： 00"}，"文本"： {"status"，"div"： "</span><span class="sxs-lookup"><span data-stu-id="7066e-155">Response: { "resourceType": "Bundle", "id": "<bundle-id>", "meta": { "lastUpdated": "2019-01-14T23:44:45.052+00:00" }, "type": "searchset", "total": 1, "link": [ { "relation": "self", "url": <fhir-server>/Patient/_search" } ], "entry": [ { "fullUrl": <fhir-server>/Patient/<patient-id>", "resource": { "resourceType": "Patient", "id": "<patient-id>", "meta": { "versionId": "1", "lastUpdated": "2017-10-18T18:32:37.000+00:00" }, "text": { "status": "generated", "div": "</span></span><div><span data-ttu-id="7066e-156">\n</span><span class="sxs-lookup"><span data-stu-id="7066e-156">\n</span></span>        <p><span data-ttu-id="7066e-157">Ruth 黑</span><span class="sxs-lookup"><span data-stu-id="7066e-157">Ruth Black</span></span></p><span data-ttu-id="7066e-158">\n</span><span class="sxs-lookup"><span data-stu-id="7066e-158">\n</span></span>      </div><span data-ttu-id="7066e-159">"}，" 标识符 "： [{" 使用 "：" 常规 "，" 键入 "： {" 编码 "： [{" system "："http://hl7.org/fhir/v2/0203"，" 代码 "：" MR "，" 显示 "：" 医学记录编号 "，" userSelected "： false}]，" 文本 "：" 医学记录号 "}，" 系统 "："http://hospital.smarthealthit.org""，"1234567"}]，"active"： true，"名称 "： [{" 使用 "：" 官方 "，" 族 "：" 黑色 "，" 给定 "： [" Ruth "，" C "。</span><span class="sxs-lookup"><span data-stu-id="7066e-159">" }, "identifier": [ { "use": "usual", "type": { "coding": [ { "system": "http://hl7.org/fhir/v2/0203", "code": "MR", "display": "Medical record number", "userSelected": false } ], "text": "Medical record number" }, "system": "http://hospital.smarthealthit.org", "value": "1234567" } ], "active": true, "name": [ { "use": "official", "family": "Black", "given": [ "Ruth", "C."</span></span>
    <span data-ttu-id="7066e-160">]}]，"电信"： [{"系统"： "电话"，"值"： "800-599-2739"，"使用"： "home"}，{"system"： "phone"，""： "：" 手机 "，" "。"： "ruth.black@example.com"}]，"性别 800-808-7785"： "女"，"出生日期"： "1951-08-23"，"地址 "： [{" 使用 "：" 主页 "，" 行 "： [" 26 RdApt： "Sapulpa"，"省/市/自治区"： "OK"，"邮政编码"： "74066"，"美国"： "美国"}]}，"搜索"： {"mode"}}]}</span><span class="sxs-lookup"><span data-stu-id="7066e-160">] } ], "telecom": [ { "system": "phone", "value": "800-599-2739", "use": "home" }, { "system": "phone", "value": "800-808-7785", "use": "mobile" }, { "system": "email", "value": "ruth.black@example.com" } ], "gender": "female", "birthDate": "1951-08-23", "address": [ { "use": "home", "line": [ "26 South RdApt 22" ], "city": "Sapulpa", "state": "OK", "postalCode": "74066", "country": "USA" } ] }, "search": { "mode": "match" } } ] }</span></span>

* * *

    <span data-ttu-id="7066e-161">请求：获取 <fhir-服务器>/Patient/<患者 id></span><span class="sxs-lookup"><span data-stu-id="7066e-161">Request: GET <fhir-server>/Patient/<patient-id></span></span>
    
    <span data-ttu-id="7066e-162">回复： {"resourceType"： "患者"，"id"： "<患者 id>"，"标识符"： [{"使用"： "常用"，"键入"： {"编码"： [{"systemhttp://hl7.org/fhir/v2/0203"： "？"，"文本"，""，"文本"： "医学记录数字"}，"值"： "1234567"}]，"名称"： [{"，" 官方 "，"。family "：" Adams "，" 给定 "： [" Daniel "，" X "。</span><span class="sxs-lookup"><span data-stu-id="7066e-162">Response: { "resourceType": "Patient", "id": "<patient-id>", "identifier": [ { "use": "usual", "type": { "coding": [ { "system": "http://hl7.org/fhir/v2/0203", "code": "MR", } ], "text": "Medical record number" }, "value": "1234567" } ], "name": [ { "use": "official", "family": "Adams", "given": [ "Daniel", "X."</span></span> <span data-ttu-id="7066e-163">]}]，"性别"： "男"，"出生日期"： "1925-12-23"，}</span><span class="sxs-lookup"><span data-stu-id="7066e-163">] } ], "gender": "male", "birthDate": "1925-12-23", }</span></span>

* * *

<span data-ttu-id="7066e-164">有关[http://hl7.org/fhir/stu3/patient.html](http://hl7.org/fhir/stu3/patient.html)此字段集的其他详细信息，请参阅。</span><span class="sxs-lookup"><span data-stu-id="7066e-164">See [http://hl7.org/fhir/stu3/patient.html](http://hl7.org/fhir/stu3/patient.html) for other details on this field set.</span></span>

## <a name="observation"></a><span data-ttu-id="7066e-165">知识产权</span><span class="sxs-lookup"><span data-stu-id="7066e-165">Observation</span></span>

<span data-ttu-id="7066e-166">以下是最少的必填字段，它们是 Argonaut 的[重要签名配置文件](https://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-vitalsigns.html)的子集。</span><span class="sxs-lookup"><span data-stu-id="7066e-166">These are the minimum required fields, which are a subset of the [Argonaut Vital-Signs profile](https://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-vitalsigns.html).</span></span>

1. <span data-ttu-id="7066e-167">有效（日期时间或周期）</span><span class="sxs-lookup"><span data-stu-id="7066e-167">Effective (date time or period)</span></span>
2. <span data-ttu-id="7066e-168">编码代码</span><span class="sxs-lookup"><span data-stu-id="7066e-168">Code.Coding.Code</span></span>
3. <span data-ttu-id="7066e-169">ValueQuantity 值</span><span class="sxs-lookup"><span data-stu-id="7066e-169">ValueQuantity.Value</span></span>

<span data-ttu-id="7066e-170">除了 Argonaut 字段外，还可以为患者应用提供出色的用户体验，还可以读取以下字段：</span><span class="sxs-lookup"><span data-stu-id="7066e-170">In addition to the Argonaut fields, for a great user experience the Patients app can also read the following fields:</span></span>

1. <span data-ttu-id="7066e-171">代码编码。显示</span><span class="sxs-lookup"><span data-stu-id="7066e-171">Code.Coding.Display</span></span>
2. <span data-ttu-id="7066e-172">ValueQuantity 单位</span><span class="sxs-lookup"><span data-stu-id="7066e-172">ValueQuantity.Unit</span></span>

<span data-ttu-id="7066e-173">资源搜索使用 GET 方法和以下参数：</span><span class="sxs-lookup"><span data-stu-id="7066e-173">A resource search uses the GET method and the following parameters:</span></span>

1. <span data-ttu-id="7066e-174">患者 =\<患者 id></span><span class="sxs-lookup"><span data-stu-id="7066e-174">patient=\<patient id></span></span>
2. <span data-ttu-id="7066e-175">_sort =-date</span><span class="sxs-lookup"><span data-stu-id="7066e-175">_sort=-date</span></span>
3. <span data-ttu-id="7066e-176">类别（我们将查询 "category = 重要标志"）以检索关键签名列表。</span><span class="sxs-lookup"><span data-stu-id="7066e-176">category (we will query for “category=vital-signs”) to retrieve the list of vital signs.</span></span>

<span data-ttu-id="7066e-177">请参阅此通话示例：</span><span class="sxs-lookup"><span data-stu-id="7066e-177">Refer to this example of the call:</span></span>

* * *

    <span data-ttu-id="7066e-178">请求：获取 <fhir-服务器>/Observation？患者 =<患者 id>&类别 = "重要签名"</span><span class="sxs-lookup"><span data-stu-id="7066e-178">Request: GET <fhir-server>/Observation?patient=<patient-id>&category=vital-signs</span></span>
    
    <span data-ttu-id="7066e-179">响应： {"resourceType"： "捆绑包"，"id"： "<捆绑包-id>"，"类型"： "searchset"，"total"：20，"entry"： [{"resource"，"id"： ">"，"id"： "<资源 id"，"类别"： [{"编码"： [{"系统"： "http://hl7.org/fhir/observation-category"，"代码"： ""关键签名 "}]，}]，" 代码 "： {" 编码 "： [{" 系统 "："http://loinc.org"，" 代码 "：" 8867-4 "，" display "：" heart_rate "}]}，" effectiveDateTime "：" 2009 年08T00：00：00： 00 "，" valueQuantity "： {" 值 "：72.0，" unit "：" {节拍} ¢ "，" system "："http://unitsofmeasure.org"，}}}。</span><span class="sxs-lookup"><span data-stu-id="7066e-179">Response: { "resourceType": "Bundle", "id": "<bundle-id>", "type": "searchset", "total": 20, "entry": [ { "resource": { "resourceType": "Observation", "id": "<resource-id>", "category": [ { "coding": [ { "system": "http://hl7.org/fhir/observation-category", "code": "vital-signs" } ], } ], "code": { "coding": [ { "system": "http://loinc.org", "code": "8867-4", "display": "heart_rate" } ] }, "effectiveDateTime": "2009-04-08T00:00:00-06:00", "valueQuantity": { "value": 72.0, "unit": "{beats}/min", "system": "http://unitsofmeasure.org", } } }, .</span></span>
        <span data-ttu-id="7066e-180">.</span><span class="sxs-lookup"><span data-stu-id="7066e-180"></span></span>
        <span data-ttu-id="7066e-181">.</span><span class="sxs-lookup"><span data-stu-id="7066e-181"></span></span>
      <span data-ttu-id="7066e-182">] }</span><span class="sxs-lookup"><span data-stu-id="7066e-182"></span></span>

* * *

<span data-ttu-id="7066e-183">有关[https://www.hl7.org/fhir/stu3/observation.html](https://www.hl7.org/fhir/stu3/observation.html)此字段集的其他详细信息，请参阅。</span><span class="sxs-lookup"><span data-stu-id="7066e-183">See [https://www.hl7.org/fhir/stu3/observation.html](https://www.hl7.org/fhir/stu3/observation.html) for other details on this field set.</span></span>

## <a name="condition"></a><span data-ttu-id="7066e-184">条件</span><span class="sxs-lookup"><span data-stu-id="7066e-184">Condition</span></span>

<span data-ttu-id="7066e-185">下面是[Argonaut 条件配置文件](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-condition.html)子集的最少必填字段。</span><span class="sxs-lookup"><span data-stu-id="7066e-185">Here's the minimum required fields, which are a subset of the [Argonaut condition profile](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-condition.html).</span></span>

1. <span data-ttu-id="7066e-186">代码。编码 [0]。画面</span><span class="sxs-lookup"><span data-stu-id="7066e-186">Code.Coding[0].Display</span></span>

<span data-ttu-id="7066e-187">除了 Argonaut 字段外，还可以为患者应用提供出色的用户体验，还可以读取以下字段：</span><span class="sxs-lookup"><span data-stu-id="7066e-187">In addition to the Argonaut fields, for a great user experience the Patients app can also read the following fields:</span></span>

1. <span data-ttu-id="7066e-188">AssertedDate</span><span class="sxs-lookup"><span data-stu-id="7066e-188">AssertedDate</span></span>
2. <span data-ttu-id="7066e-189">严重性</span><span class="sxs-lookup"><span data-stu-id="7066e-189">Severity</span></span>

<span data-ttu-id="7066e-190">资源搜索使用 GET 方法和以下参数：</span><span class="sxs-lookup"><span data-stu-id="7066e-190">A resource search uses the GET method and the following parameters:</span></span>

1. <span data-ttu-id="7066e-191">患者 =\<患者 id></span><span class="sxs-lookup"><span data-stu-id="7066e-191">patient=\<patient id></span></span>
2. <span data-ttu-id="7066e-192">_count =\<最大结果></span><span class="sxs-lookup"><span data-stu-id="7066e-192">_count=\<max results></span></span>

<span data-ttu-id="7066e-193">请参阅下面的此呼叫示例：</span><span class="sxs-lookup"><span data-stu-id="7066e-193">See the following example of this call:</span></span>

* * *

    <span data-ttu-id="7066e-194">请求：获取 <fhir-服务器>/Condition？患者 =<患者 id>&_count = 10</span><span class="sxs-lookup"><span data-stu-id="7066e-194">Request: GET <fhir-server>/Condition?patient=<patient-id>&_count=10</span></span>
    
    <span data-ttu-id="7066e-195">响应： {"resourceType"： "捆绑包"，"id"： "<捆绑包-id>"，"键入"： "searchset"，"total"：2，"entry"： [{"资源"： "Condition"，"id"： "<资源 id>"，"代码"： {"编码"： [{"系统"： "http://snomed.info/sct"，"代码"： "185903001"，"显示 "：" 需要 influenza 免疫接种 "，}]}，" 严重度 "： {" 编码 "： [{" system "http://snomed.info/sct：" 24484000 "，" 显示 "：" 严重 "}]}，" assertedDate "：" 2018-04-04 "}}。</span><span class="sxs-lookup"><span data-stu-id="7066e-195">Response: { "resourceType": "Bundle", "id": "<bundle-id>", "type": "searchset", "total": 2, "entry": [ { "resource": { "resourceType": "Condition", "id": "<resource-id>", "code": { "coding": [ { "system": "http://snomed.info/sct", "code": "185903001", "display": "Needs influenza immunization", } ] }, "severity": { "coding": [ { "system": "http://snomed.info/sct", "code": "24484000", "display": "Severe" } ] }, "assertedDate": "2018-04-04" } }, .</span></span>
        <span data-ttu-id="7066e-196">.</span><span class="sxs-lookup"><span data-stu-id="7066e-196"></span></span>
        <span data-ttu-id="7066e-197">.</span><span class="sxs-lookup"><span data-stu-id="7066e-197"></span></span>
      <span data-ttu-id="7066e-198">] }</span><span class="sxs-lookup"><span data-stu-id="7066e-198"></span></span>

* * *
<span data-ttu-id="7066e-199">有关[http://hl7.org/fhir/stu3/condition.html](http://hl7.org/fhir/stu3/condition.html)此字段集的其他详细信息，请参阅。</span><span class="sxs-lookup"><span data-stu-id="7066e-199">See [http://hl7.org/fhir/stu3/condition.html](http://hl7.org/fhir/stu3/condition.html) for other details on this field set.</span></span>

## <a name="encounter"></a><span data-ttu-id="7066e-200">产生</span><span class="sxs-lookup"><span data-stu-id="7066e-200">Encounter</span></span>

<span data-ttu-id="7066e-201">以下是最少必填字段，这些字段是 "[美国核心" 基本配置文件](http://hl7.org/fhir/us/core/2018Jan/StructureDefinition-us-core-encounter.html)"必须具有" 字段的子集。</span><span class="sxs-lookup"><span data-stu-id="7066e-201">These are the minimum required fields, which are a subset of the [US Core Encounter profile](http://hl7.org/fhir/us/core/2018Jan/StructureDefinition-us-core-encounter.html) “must have” fields).</span></span>

1. <span data-ttu-id="7066e-202">状态栏</span><span class="sxs-lookup"><span data-stu-id="7066e-202">Status</span></span>
2. <span data-ttu-id="7066e-203">键入 [0]。编码 [0]。画面</span><span class="sxs-lookup"><span data-stu-id="7066e-203">Type[0].Coding[0].Display</span></span>

<span data-ttu-id="7066e-204">此外，美国核心的以下字段会遇到配置文件的 "必须支持" 字段：</span><span class="sxs-lookup"><span data-stu-id="7066e-204">In addition, the following fields from US Core Encounter profile’s “must support” fields:</span></span>

1. <span data-ttu-id="7066e-205">句号。开始</span><span class="sxs-lookup"><span data-stu-id="7066e-205">Period.Start</span></span>
2. <span data-ttu-id="7066e-206">位置 [0]。位置。显示</span><span class="sxs-lookup"><span data-stu-id="7066e-206">Location[0].Location.Display</span></span>

<span data-ttu-id="7066e-207">资源搜索使用 GET 方法和以下参数：</span><span class="sxs-lookup"><span data-stu-id="7066e-207">A resource search uses the GET method and the following parameters:</span></span>

1. <span data-ttu-id="7066e-208">患者 =\<患者 id></span><span class="sxs-lookup"><span data-stu-id="7066e-208">patient=\<patient id></span></span>
2. <span data-ttu-id="7066e-209">_sort： desc =\<field （ex）</span><span class="sxs-lookup"><span data-stu-id="7066e-209">_sort:desc=\<field ex.</span></span> <span data-ttu-id="7066e-210">日期></span><span class="sxs-lookup"><span data-stu-id="7066e-210">date></span></span>
3. <span data-ttu-id="7066e-211">_count =\<最大结果></span><span class="sxs-lookup"><span data-stu-id="7066e-211">_count=\<max results></span></span>

<span data-ttu-id="7066e-212">目标是能够检索患者的最后一个已知位置。</span><span class="sxs-lookup"><span data-stu-id="7066e-212">The goal is to be able to retrieve the patient’s last known location.</span></span> <span data-ttu-id="7066e-213">每个遇到的都引用一个位置资源。</span><span class="sxs-lookup"><span data-stu-id="7066e-213">Each encounter references a location resource.</span></span> <span data-ttu-id="7066e-214">该引用还应包含位置的显示字段。</span><span class="sxs-lookup"><span data-stu-id="7066e-214">The reference shall also include the location’s display field.</span></span>

<span data-ttu-id="7066e-215">有关[http://hl7.org/fhir/stu3/encounter.html](http://hl7.org/fhir/stu3/encounter.html)此字段集的其他详细信息，请参阅。</span><span class="sxs-lookup"><span data-stu-id="7066e-215">See [http://hl7.org/fhir/stu3/encounter.html](http://hl7.org/fhir/stu3/encounter.html) for other details on this field set.</span></span>

## <a name="allergyintolerance"></a><span data-ttu-id="7066e-216">AllergyIntolerance</span><span class="sxs-lookup"><span data-stu-id="7066e-216">AllergyIntolerance</span></span>

<span data-ttu-id="7066e-217">以下是最少的必填字段，它们是[Argonaut AllergyIntolerance](https://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-allergyintolerance.html)配置文件的子集：</span><span class="sxs-lookup"><span data-stu-id="7066e-217">These are the minimum required fields, which are a subset of the [Argonaut AllergyIntolerance](https://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-allergyintolerance.html) profile:</span></span>

1. <span data-ttu-id="7066e-218">代码。文本</span><span class="sxs-lookup"><span data-stu-id="7066e-218">Code.Text</span></span>
2. <span data-ttu-id="7066e-219">代码。编码 [0]。画面</span><span class="sxs-lookup"><span data-stu-id="7066e-219">Code.Coding[0].Display</span></span>
3. <span data-ttu-id="7066e-220">ClinicalStatus/VerificationStatus （我们通读两个）</span><span class="sxs-lookup"><span data-stu-id="7066e-220">ClinicalStatus/VerificationStatus (we read both)</span></span>

<span data-ttu-id="7066e-221">除了 Argonaut 字段外，还可为患者应用提供出色的用户体验，还可以读取以下字段：</span><span class="sxs-lookup"><span data-stu-id="7066e-221">In addition to the Argonaut fields, for a great user experience the Patients app can also read the following field:</span></span>

1. <span data-ttu-id="7066e-222">AssertedDate</span><span class="sxs-lookup"><span data-stu-id="7066e-222">AssertedDate</span></span>
2. <span data-ttu-id="7066e-223">备注。文本</span><span class="sxs-lookup"><span data-stu-id="7066e-223">Note.Text</span></span>
3. <span data-ttu-id="7066e-224">被动</span><span class="sxs-lookup"><span data-stu-id="7066e-224">Reaction</span></span>
    1. <span data-ttu-id="7066e-225">物质（一个编码元素）</span><span class="sxs-lookup"><span data-stu-id="7066e-225">Substance (one coding element)</span></span>
    2. <span data-ttu-id="7066e-226">表现形式（一个编码元素）</span><span class="sxs-lookup"><span data-stu-id="7066e-226">Manifestation (one coding element)</span></span>

<span data-ttu-id="7066e-227">资源搜索使用 GET 方法和以下参数：</span><span class="sxs-lookup"><span data-stu-id="7066e-227">A resource search uses the GET method and the following parameters:</span></span>

1. <span data-ttu-id="7066e-228">患者 = \<患者 id></span><span class="sxs-lookup"><span data-stu-id="7066e-228">Patient =  \<patient id></span></span>

<span data-ttu-id="7066e-229">请参阅下面的通话示例：</span><span class="sxs-lookup"><span data-stu-id="7066e-229">See the following example of the call:</span></span> 

* * *

    <span data-ttu-id="7066e-230">请求：获取 <fhir-服务器>/AllergyIntolerance？患者 =<患者 id></span><span class="sxs-lookup"><span data-stu-id="7066e-230">Request: GET <fhir-server>/AllergyIntolerance?patient=<patient-id></span></span>
    
    <span data-ttu-id="7066e-231">响应： {"resourceType"： "捆绑包"，"id"> <： "searchset"： ""，"total"：1，"entry"： [{"资源"： {""： "AllergyIntolerance"，"id"： "<资源 id>"，"clinicalStatus"： "active"，"verificationStatus "：" 已确认 "，" 代码 "： {" 编码 "： [{" systemhttp://rxnav.nlm.nih.gov/REST/Ndfrt"：" N0000175503 "、" code "：" "、" display "：" sulfonamide antibacterial "，}]，" 文本 "：" sulfonamide antibacterial "}"，"assertedDate"： "2018 日-01： 00"，"反应"： [{"形式"： [{"代码"： [{"系统"： "http://snomed.info/sct"，"代码"： "271807003"，"display"： "皮肤 rash"，}]，"text"： "皮肤 rash"}]，}]}}</span><span class="sxs-lookup"><span data-stu-id="7066e-231">Response: {   "resourceType": "Bundle",   "id": "<bundle-id>",   "type": "searchset",   "total": 1,   "entry": [     {       "resource": {         "resourceType": "AllergyIntolerance",         "id": "<resource-id>",         "clinicalStatus": "active",         "verificationStatus": "confirmed",         "code": {           "coding": [             {               "system": "http://rxnav.nlm.nih.gov/REST/Ndfrt",               "code": "N0000175503",               "display": "sulfonamide antibacterial",             }           ],           "text": "sulfonamide antibacterial"         },         "assertedDate": "2018-01-01T00:00:00-07:00",         "reaction": [           {             "manifestation": [               {                 "coding": [                   {                     "system": "http://snomed.info/sct",                     "code": "271807003",                     "display": "skin rash",                   }                 ],                 "text": "skin rash"               }             ],           }         ]       }     }   ] }</span></span>

* * *

<span data-ttu-id="7066e-232">有关[http://hl7.org/fhir/stu3/allergyintolerance.html](http://hl7.org/fhir/stu3/allergyintolerance.html)此字段集的其他详细信息，请参阅。</span><span class="sxs-lookup"><span data-stu-id="7066e-232">See [http://hl7.org/fhir/stu3/allergyintolerance.html](http://hl7.org/fhir/stu3/allergyintolerance.html) for other details on this field set.</span></span>

## <a name="medication-request"></a><span data-ttu-id="7066e-233">药物请求</span><span class="sxs-lookup"><span data-stu-id="7066e-233">Medication Request</span></span>

<span data-ttu-id="7066e-234">以下是最少的必填字段，这些字段是[美国核心药物请求档案](http://www.hl7.org/fhir/us/core/StructureDefinition-us-core-medicationrequest.html)的子集：</span><span class="sxs-lookup"><span data-stu-id="7066e-234">These are the minimum required fields, which are a subset of the [US Core Medication Request profile](http://www.hl7.org/fhir/us/core/StructureDefinition-us-core-medicationrequest.html):</span></span>

1. <span data-ttu-id="7066e-235">药物的显示（如果参考）</span><span class="sxs-lookup"><span data-stu-id="7066e-235">Medication.Display (if Reference)</span></span>
2. <span data-ttu-id="7066e-236">药物文本（如果 CodableConcept）</span><span class="sxs-lookup"><span data-stu-id="7066e-236">Medication.Text (if CodableConcept)</span></span>
3. <span data-ttu-id="7066e-237">AuthoredOn</span><span class="sxs-lookup"><span data-stu-id="7066e-237">AuthoredOn</span></span>
4. <span data-ttu-id="7066e-238">请求者代理。显示</span><span class="sxs-lookup"><span data-stu-id="7066e-238">Requester.Agent.Display</span></span>

<span data-ttu-id="7066e-239">除了 US 核心字段外，还可为患者应用提供出色的用户体验，还可以读取以下字段：</span><span class="sxs-lookup"><span data-stu-id="7066e-239">In addition to the US Core fields, for a great user experience the Patients app can also read the following fields:</span></span>

1. <span data-ttu-id="7066e-240">DosageInstruction[..].文本</span><span class="sxs-lookup"><span data-stu-id="7066e-240">DosageInstruction[..].Text</span></span>
2. <span data-ttu-id="7066e-241">文本</span><span class="sxs-lookup"><span data-stu-id="7066e-241">Text</span></span>

<span data-ttu-id="7066e-242">资源搜索使用 GET 方法和以下参数：</span><span class="sxs-lookup"><span data-stu-id="7066e-242">A resource search uses the GET method and the following parameters:</span></span>

1. <span data-ttu-id="7066e-243">患者 =\<患者 id></span><span class="sxs-lookup"><span data-stu-id="7066e-243">patient=\<patient id></span></span>
2. <span data-ttu-id="7066e-244">_count =\<最大结果></span><span class="sxs-lookup"><span data-stu-id="7066e-244">_count=\<max results></span></span>

<span data-ttu-id="7066e-245">有关[https://www.hl7.org/fhir/medicationrequest.html](https://www.hl7.org/fhir/medicationrequest.html)此字段集的其他详细信息，请参阅。</span><span class="sxs-lookup"><span data-stu-id="7066e-245">See [https://www.hl7.org/fhir/medicationrequest.html](https://www.hl7.org/fhir/medicationrequest.html) for other details on this field set.</span></span>

## <a name="coverage"></a><span data-ttu-id="7066e-246">内</span><span class="sxs-lookup"><span data-stu-id="7066e-246">Coverage</span></span>

<span data-ttu-id="7066e-247">以下是 "最少必填字段"，不包含在美国 Core 或 Argonaut 配置文件中：</span><span class="sxs-lookup"><span data-stu-id="7066e-247">These are the minimum required fields, not covered by either US Core or Argonaut profiles:</span></span>

1. <span data-ttu-id="7066e-248">组合，至少一个元素具有</span><span class="sxs-lookup"><span data-stu-id="7066e-248">Grouping, at least one element with</span></span>
    1. <span data-ttu-id="7066e-249">GroupDisplay</span><span class="sxs-lookup"><span data-stu-id="7066e-249">GroupDisplay</span></span>
    2. <span data-ttu-id="7066e-250">PlanDisplay</span><span class="sxs-lookup"><span data-stu-id="7066e-250">PlanDisplay</span></span>
2. <span data-ttu-id="7066e-251">试用期</span><span class="sxs-lookup"><span data-stu-id="7066e-251">Period</span></span>
3. <span data-ttu-id="7066e-252">SubscriberId</span><span class="sxs-lookup"><span data-stu-id="7066e-252">SubscriberId</span></span>

<span data-ttu-id="7066e-253">资源搜索使用 GET 方法和以下参数：</span><span class="sxs-lookup"><span data-stu-id="7066e-253">A resource search uses the GET method and the following parameters:</span></span>

1. <span data-ttu-id="7066e-254">患者 = \<患者 id></span><span class="sxs-lookup"><span data-stu-id="7066e-254">Patient = \<patient id></span></span>

<span data-ttu-id="7066e-255">有关[http://hl7.org/fhir/stu3/coverage.html](https://www.hl7.org/fhir/medicationrequest.html)此字段集的其他详细信息，请参阅。</span><span class="sxs-lookup"><span data-stu-id="7066e-255">See [http://hl7.org/fhir/stu3/coverage.html](https://www.hl7.org/fhir/medicationrequest.html) for other details on this field set.</span></span>
