---
title: 患者应用程序和 EHR 集成 STU3 接口
author: jambirk
ms.author: jambirk
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
search.appverid: MET150
localization_priority: Normal
ms.collection: Teams_ITAdmin_PracticalGuidance
appliesto:
- Microsoft Teams
ms.reviewer: anach
description: Microsoft 团队患者 app EHR 集成
ms.openlocfilehash: 34fd6bb1ecaf788a55aca877c671c9a51cb07944
ms.sourcegitcommit: cf2cb5b7e03385b33e34a5ff89719adb882525b1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/06/2019
ms.locfileid: "33643073"
---
# <a name="stu3-interface-specification"></a><span data-ttu-id="c1aa9-103">STU3 接口规范</span><span class="sxs-lookup"><span data-stu-id="c1aa9-103">STU3 interface specification</span></span>

[!INCLUDE [preview-feature](../../includes/preview-feature.md)]

<span data-ttu-id="c1aa9-104">设置或重新配置 FHIR server 以使用 Microsoft 团队患者应用程序需要了解哪些应用程序需要访问的数据。</span><span class="sxs-lookup"><span data-stu-id="c1aa9-104">Setting up or reconfiguring an FHIR server to work with the Microsoft Teams Patients app requires understanding what data the app needs to access.</span></span> <span data-ttu-id="c1aa9-105">FHIR 服务器必须支持的以下资源使用捆绑的 POST 请求：</span><span class="sxs-lookup"><span data-stu-id="c1aa9-105">The FHIR server must support POST requests using bundles for the following resources:</span></span>

- [<span data-ttu-id="c1aa9-106">患者</span><span class="sxs-lookup"><span data-stu-id="c1aa9-106">Patient</span></span>](#patient)
- [<span data-ttu-id="c1aa9-107">观察值</span><span class="sxs-lookup"><span data-stu-id="c1aa9-107">Observation</span></span>](#observation)
- [<span data-ttu-id="c1aa9-108">条件</span><span class="sxs-lookup"><span data-stu-id="c1aa9-108">Condition</span></span>](#condition)
- [<span data-ttu-id="c1aa9-109">遇到</span><span class="sxs-lookup"><span data-stu-id="c1aa9-109">Encounter</span></span>](#encounter)
- [<span data-ttu-id="c1aa9-110">过敏 Intolerance</span><span class="sxs-lookup"><span data-stu-id="c1aa9-110">Allergy Intolerance</span></span>](#allergyintolerance)
- [<span data-ttu-id="c1aa9-111">覆盖范围</span><span class="sxs-lookup"><span data-stu-id="c1aa9-111">Coverage</span></span>](#coverage)
- <span data-ttu-id="c1aa9-112">[用药语句](#medication-request)（替换 PatientsApp DSTU2 版本 MedicationOrder）</span><span class="sxs-lookup"><span data-stu-id="c1aa9-112">[Medication Statement](#medication-request) (replaces the MedicationOrder in the DSTU2 version of the PatientsApp)</span></span>
- <span data-ttu-id="c1aa9-113">（信息需要从此资源可以包括在遇到） 的位置</span><span class="sxs-lookup"><span data-stu-id="c1aa9-113">Location (the information needed from this resource can be included in Encounter)</span></span>

> [!NOTE]
> <span data-ttu-id="c1aa9-114">患者资源是唯一的必填资源 （该应用程序将不会加载根本）;但是，建议合作伙伴实现支持的每个规范下面提供的 Microsoft 团队患者 App 最佳最终用户体验的所有上面提到资源。</span><span class="sxs-lookup"><span data-stu-id="c1aa9-114">The Patient resource is the only mandatory resource (without which the app will not load at all); However, it is recommended that the Partner implement support for all the above mentioned resources per specifications provided below for the best end-user experience with the Microsoft Teams Patients App.</span></span>

<span data-ttu-id="c1aa9-115">从多个资源的 Microsoft 团队患者应用程序的查询应发布到 FHIR 服务器的 URL 的请求的绑定 （批次）。</span><span class="sxs-lookup"><span data-stu-id="c1aa9-115">Queries from the Microsoft Teams Patients app for more than one resource shall post a bundle (BATCH) of requests to the FHIR server's URL.</span></span> <span data-ttu-id="c1aa9-116">服务器应处理每个请求，并将返回匹配的每个请求的资源的绑定。</span><span class="sxs-lookup"><span data-stu-id="c1aa9-116">The server shall process each request and return a bundle of the resources matched by each request.</span></span> <span data-ttu-id="c1aa9-117">有关详细信息和示例，请参阅[https://www.hl7.org/fhir/STU3/http.html#transaction](https://www.hl7.org/fhir/STU3/http.html#transaction)。</span><span class="sxs-lookup"><span data-stu-id="c1aa9-117">For more information and examples, see [https://www.hl7.org/fhir/STU3/http.html#transaction](https://www.hl7.org/fhir/STU3/http.html#transaction).</span></span>

## <a name="capability-statement"></a><span data-ttu-id="c1aa9-118">功能语句</span><span class="sxs-lookup"><span data-stu-id="c1aa9-118">Capability Statement</span></span>

<span data-ttu-id="c1aa9-119">这是最小的必填的字段：</span><span class="sxs-lookup"><span data-stu-id="c1aa9-119">These are the minimum required fields:</span></span>

1. <span data-ttu-id="c1aa9-120">REST</span><span class="sxs-lookup"><span data-stu-id="c1aa9-120">REST</span></span>
   1. <span data-ttu-id="c1aa9-121">模式</span><span class="sxs-lookup"><span data-stu-id="c1aa9-121">Mode</span></span>
   2. <span data-ttu-id="c1aa9-122">交互</span><span class="sxs-lookup"><span data-stu-id="c1aa9-122">Interaction</span></span>
   3. <span data-ttu-id="c1aa9-123">资源： 类型</span><span class="sxs-lookup"><span data-stu-id="c1aa9-123">Resource: Type</span></span>
   4. <span data-ttu-id="c1aa9-124">安全性：[扩展的 OAuth Uri](http://hl7.org/fhir/extension-oauth-uris.html)</span><span class="sxs-lookup"><span data-stu-id="c1aa9-124">Security: [Extension for OAuth URIs](http://hl7.org/fhir/extension-oauth-uris.html)</span></span>
2. <span data-ttu-id="c1aa9-125">FhirVersion （我们的代码需要此选项可了解我们应该侧重于哪个版本。）</span><span class="sxs-lookup"><span data-stu-id="c1aa9-125">FhirVersion (Our code requires this to understand which version we should pivot to.)</span></span>

<span data-ttu-id="c1aa9-126">请参阅[https://www.hl7.org/fhir/stu3/capabilitystatement.html](https://www.hl7.org/fhir/stu3/capabilitystatement.html)有关此字段的其他详细信息设置。</span><span class="sxs-lookup"><span data-stu-id="c1aa9-126">See [https://www.hl7.org/fhir/stu3/capabilitystatement.html](https://www.hl7.org/fhir/stu3/capabilitystatement.html) for other details on this field set.</span></span>

## <a name="patient"></a><span data-ttu-id="c1aa9-127">患者</span><span class="sxs-lookup"><span data-stu-id="c1aa9-127">Patient</span></span>

<span data-ttu-id="c1aa9-128">下面是最小的必填的字段，它们是 Argonaut 患者的配置文件字段的子集：</span><span class="sxs-lookup"><span data-stu-id="c1aa9-128">Here are the minimum required fields, which are a subset of the Argonaut patient profile fields:</span></span>

1. <span data-ttu-id="c1aa9-129">Name.Given</span><span class="sxs-lookup"><span data-stu-id="c1aa9-129">Name.Given</span></span>
2. <span data-ttu-id="c1aa9-130">Name.Family</span><span class="sxs-lookup"><span data-stu-id="c1aa9-130">Name.Family</span></span>
3. <span data-ttu-id="c1aa9-131">性别</span><span class="sxs-lookup"><span data-stu-id="c1aa9-131">Gender</span></span>
4. <span data-ttu-id="c1aa9-132">出生日期</span><span class="sxs-lookup"><span data-stu-id="c1aa9-132">BirthDate</span></span>
5. <span data-ttu-id="c1aa9-133">MRN （标识符）</span><span class="sxs-lookup"><span data-stu-id="c1aa9-133">MRN (Identifier)</span></span>

<span data-ttu-id="c1aa9-134">除了[Argonaut 字段](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-patient.html)中，为出色的用户体验患者应用程序还可以阅读以下字段：</span><span class="sxs-lookup"><span data-stu-id="c1aa9-134">In addition to the [Argonaut fields](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-patient.html), for a great user experience the Patients app can also read the following fields:</span></span>

1. <span data-ttu-id="c1aa9-135">Name.Use</span><span class="sxs-lookup"><span data-stu-id="c1aa9-135">Name.Use</span></span>
2. <span data-ttu-id="c1aa9-136">Name.Prefix</span><span class="sxs-lookup"><span data-stu-id="c1aa9-136">Name.Prefix</span></span>
3. <span data-ttu-id="c1aa9-137">[GeneralPractitioner]-GeneralPractitioner 引用应包含在患者资源 （仅显示字段）</span><span class="sxs-lookup"><span data-stu-id="c1aa9-137">[GeneralPractitioner] - The GeneralPractitioner reference should be included in the Patient resource (display field only)</span></span>

<span data-ttu-id="c1aa9-138">资源搜索使用 POST 方法 /Patient/_search 和以下参数：</span><span class="sxs-lookup"><span data-stu-id="c1aa9-138">A resource search uses the POST method at /Patient/_search and the following parameters:</span></span>

1. <span data-ttu-id="c1aa9-139">id</span><span class="sxs-lookup"><span data-stu-id="c1aa9-139">id</span></span>
2. <span data-ttu-id="c1aa9-140">系列 = （搜索系列名称中包含值的所有患者）</span><span class="sxs-lookup"><span data-stu-id="c1aa9-140">family=(searches for all patients whose family name contains the value)</span></span>
3. <span data-ttu-id="c1aa9-141">给定 =\<substring></span><span class="sxs-lookup"><span data-stu-id="c1aa9-141">given=\<substring></span></span>
4. <span data-ttu-id="c1aa9-142">出生日期 =(exact match)</span><span class="sxs-lookup"><span data-stu-id="c1aa9-142">birthdate=(exact match)</span></span>
5. <span data-ttu-id="c1aa9-143">性别 = （正在管理性别之一的值）</span><span class="sxs-lookup"><span data-stu-id="c1aa9-143">gender=(values being one of the administrative-gender)</span></span>
6. <span data-ttu-id="c1aa9-144">\_计数 （最大应返回的结果数）</span><span class="sxs-lookup"><span data-stu-id="c1aa9-144">\_count (maximum number of results that should be returned)</span></span> <br> <span data-ttu-id="c1aa9-145">响应应该包含由于搜索返回的记录的总计数和\_计数将由 PatientsApp 以限制返回的记录数。</span><span class="sxs-lookup"><span data-stu-id="c1aa9-145">The response should contain the total count of records returned as a result of the search and \_count will be used by the PatientsApp to limit the number of records returned.</span></span>
7. <span data-ttu-id="c1aa9-146">标识符 =\<mrn></span><span class="sxs-lookup"><span data-stu-id="c1aa9-146">identifier=\<mrn></span></span>

<span data-ttu-id="c1aa9-147">目标是能够搜索和筛选由以下患者：</span><span class="sxs-lookup"><span data-stu-id="c1aa9-147">The goal is to be able to search and filter for a patient by the following:</span></span>

- <span data-ttu-id="c1aa9-148">ID： 这是每个资源 FHIR 中的包含的资源 ID。</span><span class="sxs-lookup"><span data-stu-id="c1aa9-148">ID: This is the resource ID that every resource in FHIR has.</span></span>
- <span data-ttu-id="c1aa9-149">MRN： 这是患者临床人员自己知道的实际标识符。</span><span class="sxs-lookup"><span data-stu-id="c1aa9-149">MRN: This is the actual identifier for the patient that clinical staff would know.</span></span> <span data-ttu-id="c1aa9-150">我们了解此 MRN 基于内 FHIR 标识符资源的标识符的类型。</span><span class="sxs-lookup"><span data-stu-id="c1aa9-150">We understand this MRN is based on the type of identifier inside the identifier resource in FHIR.</span></span>
- <span data-ttu-id="c1aa9-151">名称</span><span class="sxs-lookup"><span data-stu-id="c1aa9-151">Name</span></span>
- <span data-ttu-id="c1aa9-152">出生日期</span><span class="sxs-lookup"><span data-stu-id="c1aa9-152">Birthdate</span></span>

<span data-ttu-id="c1aa9-153">请参阅下面的示例的呼叫：</span><span class="sxs-lookup"><span data-stu-id="c1aa9-153">See the following example of the call:</span></span>

* * *

    <span data-ttu-id="c1aa9-154">请求： POST <fhir-server>/患者/_search 请求正文： 给定 = ruth&family = 黑色</span><span class="sxs-lookup"><span data-stu-id="c1aa9-154">Request: POST <fhir-server>/Patient/_search Request Body: given=ruth&family=black</span></span>
    
    <span data-ttu-id="c1aa9-155">响应: {"resourceType":"捆绑"、"id":"<bundle id>"、"元数据": {"上次更新":"2019年-01-14T23:44:45.052 + 00:00"}，"类型":"searchset"，"total": 1，"链接": [{"关系":"自助"、"url": <fhir-server>/患者/_search"}]，entry: [{"fullUrl": <fhir-server>/患者/<patient-id>"，"资源": {"resourceType":"患者"，"id":"<patient id>"、"元数据": {"versionId":"1"的"上次更新":"2017年-10-18T18:32:37.000 + 00:00"}，"text": {"状态":"生成"、"div": "</span><span class="sxs-lookup"><span data-stu-id="c1aa9-155">Response: { "resourceType": "Bundle", "id": "<bundle-id>", "meta": { "lastUpdated": "2019-01-14T23:44:45.052+00:00" }, "type": "searchset", "total": 1, "link": [ { "relation": "self", "url": <fhir-server>/Patient/_search" } ], "entry": [ { "fullUrl": <fhir-server>/Patient/<patient-id>", "resource": { "resourceType": "Patient", "id": "<patient-id>", "meta": { "versionId": "1", "lastUpdated": "2017-10-18T18:32:37.000+00:00" }, "text": { "status": "generated", "div": "</span></span><div><span data-ttu-id="c1aa9-156">\n</span><span class="sxs-lookup"><span data-stu-id="c1aa9-156">\n</span></span>        <p><span data-ttu-id="c1aa9-157">有所黑色</span><span class="sxs-lookup"><span data-stu-id="c1aa9-157">Ruth Black</span></span></p><span data-ttu-id="c1aa9-158">\n</span><span class="sxs-lookup"><span data-stu-id="c1aa9-158">\n</span></span>      </div><span data-ttu-id="c1aa9-159">"}，"标识符": [{"使用":"常用"的"类型": {"编码": [{"系统":"http://hl7.org/fhir/v2/0203"，"代码":"MR"，"显示":"医疗记录号"、"userSelected": false}]，"text":"医疗记录号"}，"系统":"http://hospital.smarthealthit.org"，"value":"1234567"}]、"活动": 为 true，则"名称": [{"使用":"正式"，"系列":"黑色"，"授予": ["有所"，"c"。</span><span class="sxs-lookup"><span data-stu-id="c1aa9-159">" }, "identifier": [ { "use": "usual", "type": { "coding": [ { "system": "http://hl7.org/fhir/v2/0203", "code": "MR", "display": "Medical record number", "userSelected": false } ], "text": "Medical record number" }, "system": "http://hospital.smarthealthit.org", "value": "1234567" } ], "active": true, "name": [ { "use": "official", "family": "Black", "given": [ "Ruth", "C."</span></span>
    <span data-ttu-id="c1aa9-160">]}]，"电信": [{"系统":"电话"，"value":"800-599-2739"，"使用":"主页"}，{"系统":"电话"，"value":"800-808-7785"，"使用":"移动"}，{"系统":"电子邮件"、"value":"ruth.black@example.com"}]，"性别":"女"，"出生日期":"1951年-08-23"，"address": [{"使用":"主页"，"线条": ["26 南部 RdApt 22"]，"city":"Sapulpa"，"state":"OK"，"postalCode":"74066"，"country":"美国"}]}，"搜索": {"模式":"匹配"}}]}</span><span class="sxs-lookup"><span data-stu-id="c1aa9-160">] } ], "telecom": [ { "system": "phone", "value": "800-599-2739", "use": "home" }, { "system": "phone", "value": "800-808-7785", "use": "mobile" }, { "system": "email", "value": "ruth.black@example.com" } ], "gender": "female", "birthDate": "1951-08-23", "address": [ { "use": "home", "line": [ "26 South RdApt 22" ], "city": "Sapulpa", "state": "OK", "postalCode": "74066", "country": "USA" } ] }, "search": { "mode": "match" } } ] }</span></span>

* * *

    <span data-ttu-id="c1aa9-161">请求： 获取 <fhir-server>/患者/<patient-id></span><span class="sxs-lookup"><span data-stu-id="c1aa9-161">Request: GET <fhir-server>/Patient/<patient-id></span></span>
    
    <span data-ttu-id="c1aa9-162">响应: {"resourceType":"患者"，"id":"<patient id>"、"标识符": [{"使用":"常用"的"类型": {"编码": [{"系统":"http://hl7.org/fhir/v2/0203"，"代码":"MR"}]，"text":"医疗记录号"}，"value":"1234567"}]，"名称": [{"使用":"正式"，"系列":"Adams"，"授予": ["Daniel"、"X。</span><span class="sxs-lookup"><span data-stu-id="c1aa9-162">Response: { "resourceType": "Patient", "id": "<patient-id>", "identifier": [ { "use": "usual", "type": { "coding": [ { "system": "http://hl7.org/fhir/v2/0203", "code": "MR", } ], "text": "Medical record number" }, "value": "1234567" } ], "name": [ { "use": "official", "family": "Adams", "given": [ "Daniel", "X."</span></span> <span data-ttu-id="c1aa9-163">] {}]，"性别":"男"，"出生日期":"1925年-12-23"}</span><span class="sxs-lookup"><span data-stu-id="c1aa9-163">] } ], "gender": "male", "birthDate": "1925-12-23", }</span></span>

* * *

<span data-ttu-id="c1aa9-164">请参阅[http://hl7.org/fhir/stu3/patient.html](http://hl7.org/fhir/stu3/patient.html)有关此字段的其他详细信息设置。</span><span class="sxs-lookup"><span data-stu-id="c1aa9-164">See [http://hl7.org/fhir/stu3/patient.html](http://hl7.org/fhir/stu3/patient.html) for other details on this field set.</span></span>

## <a name="observation"></a><span data-ttu-id="c1aa9-165">观察值</span><span class="sxs-lookup"><span data-stu-id="c1aa9-165">Observation</span></span>

<span data-ttu-id="c1aa9-166">这些是最小必填的字段，是[Argonaut 重要征兆配置文件](https://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-vitalsigns.html)的子集。</span><span class="sxs-lookup"><span data-stu-id="c1aa9-166">These are the minimum required fields, which are a subset of the [Argonaut Vital-Signs profile](https://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-vitalsigns.html).</span></span>

1. <span data-ttu-id="c1aa9-167">有效 （日期时间或段）</span><span class="sxs-lookup"><span data-stu-id="c1aa9-167">Effective (date time or period)</span></span>
2. <span data-ttu-id="c1aa9-168">Code.Coding.Code</span><span class="sxs-lookup"><span data-stu-id="c1aa9-168">Code.Coding.Code</span></span>
3. <span data-ttu-id="c1aa9-169">ValueQuantity.Value</span><span class="sxs-lookup"><span data-stu-id="c1aa9-169">ValueQuantity.Value</span></span>

<span data-ttu-id="c1aa9-170">除了 Argonaut 字段中，为出色的用户体验患者应用程序还可以阅读以下字段：</span><span class="sxs-lookup"><span data-stu-id="c1aa9-170">In addition to the Argonaut fields, for a great user experience the Patients app can also read the following fields:</span></span>

1. <span data-ttu-id="c1aa9-171">Code.Coding.Display</span><span class="sxs-lookup"><span data-stu-id="c1aa9-171">Code.Coding.Display</span></span>
2. <span data-ttu-id="c1aa9-172">ValueQuantity.Unit</span><span class="sxs-lookup"><span data-stu-id="c1aa9-172">ValueQuantity.Unit</span></span>

<span data-ttu-id="c1aa9-173">资源搜索使用 GET 方法并使用以下参数：</span><span class="sxs-lookup"><span data-stu-id="c1aa9-173">A resource search uses the GET method and the following parameters:</span></span>

1. <span data-ttu-id="c1aa9-174">患者 =\<患者 id></span><span class="sxs-lookup"><span data-stu-id="c1aa9-174">patient=\<patient id></span></span>
2. <span data-ttu-id="c1aa9-175">_sort = 日期</span><span class="sxs-lookup"><span data-stu-id="c1aa9-175">_sort=-date</span></span>
3. <span data-ttu-id="c1aa9-176">类别 (我们将查询"类别 = 重要迹象") 以检索重要标志的列表。</span><span class="sxs-lookup"><span data-stu-id="c1aa9-176">category (we will query for “category=vital-signs”) to retrieve the list of vital signs.</span></span>

<span data-ttu-id="c1aa9-177">请参阅本例呼叫：</span><span class="sxs-lookup"><span data-stu-id="c1aa9-177">Refer to this example of the call:</span></span>

* * *

    <span data-ttu-id="c1aa9-178">请求： 获取观察值 <fhir-server>？ 患者 = <patient id>&category = 重要迹象</span><span class="sxs-lookup"><span data-stu-id="c1aa9-178">Request: GET <fhir-server>/Observation?patient=<patient-id>&category=vital-signs</span></span>
    
    <span data-ttu-id="c1aa9-179">响应: {"resourceType":"捆绑"、"id":"<bundle id>"、"类型":"searchset"，"total": 20，entry: [{"资源": {"resourceType":"观察值"、"id":"<resource id>"、"category": [{"编码": [{"系统":"http://hl7.org/fhir/observation-category"，"代码":"重要标记"}]}]，"代码": {"编码": [{"系统":"http://loinc.org"，"代码":"8867-4"，"显示":"heart_rate"}]}，"effectiveDateTime":"2009年-04-08T00:00:00-06:00"，"valueQuantity": {"value": 72.0，"单位":"{优于} / min"，"系统":"http://unitsofmeasure.org"，}}}。</span><span class="sxs-lookup"><span data-stu-id="c1aa9-179">Response: { "resourceType": "Bundle", "id": "<bundle-id>", "type": "searchset", "total": 20, "entry": [ { "resource": { "resourceType": "Observation", "id": "<resource-id>", "category": [ { "coding": [ { "system": "http://hl7.org/fhir/observation-category", "code": "vital-signs" } ], } ], "code": { "coding": [ { "system": "http://loinc.org", "code": "8867-4", "display": "heart_rate" } ] }, "effectiveDateTime": "2009-04-08T00:00:00-06:00", "valueQuantity": { "value": 72.0, "unit": "{beats}/min", "system": "http://unitsofmeasure.org", } } }, .</span></span>
        <span data-ttu-id="c1aa9-180">.</span><span class="sxs-lookup"><span data-stu-id="c1aa9-180"></span></span>
        <span data-ttu-id="c1aa9-181">.</span><span class="sxs-lookup"><span data-stu-id="c1aa9-181"></span></span>
      <span data-ttu-id="c1aa9-182">] }</span><span class="sxs-lookup"><span data-stu-id="c1aa9-182"></span></span>

* * *

<span data-ttu-id="c1aa9-183">请参阅[https://www.hl7.org/fhir/stu3/observation.html](https://www.hl7.org/fhir/stu3/observation.html)有关此字段的其他详细信息设置。</span><span class="sxs-lookup"><span data-stu-id="c1aa9-183">See [https://www.hl7.org/fhir/stu3/observation.html](https://www.hl7.org/fhir/stu3/observation.html) for other details on this field set.</span></span>

## <a name="condition"></a><span data-ttu-id="c1aa9-184">条件</span><span class="sxs-lookup"><span data-stu-id="c1aa9-184">Condition</span></span>

<span data-ttu-id="c1aa9-185">下面是最小必填的字段，是[Argonaut 条件配置文件](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-condition.html)的子集。</span><span class="sxs-lookup"><span data-stu-id="c1aa9-185">Here's the minimum required fields, which are a subset of the [Argonaut condition profile](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-condition.html).</span></span>

1. <span data-ttu-id="c1aa9-186">Code.Coding[0]。显示</span><span class="sxs-lookup"><span data-stu-id="c1aa9-186">Code.Coding[0].Display</span></span>

<span data-ttu-id="c1aa9-187">除了 Argonaut 字段中，为出色的用户体验患者应用程序还可以阅读以下字段：</span><span class="sxs-lookup"><span data-stu-id="c1aa9-187">In addition to the Argonaut fields, for a great user experience the Patients app can also read the following fields:</span></span>

1. <span data-ttu-id="c1aa9-188">AssertedDate</span><span class="sxs-lookup"><span data-stu-id="c1aa9-188">AssertedDate</span></span>
2. <span data-ttu-id="c1aa9-189">严重级别</span><span class="sxs-lookup"><span data-stu-id="c1aa9-189">Severity</span></span>

<span data-ttu-id="c1aa9-190">资源搜索使用 GET 方法并使用以下参数：</span><span class="sxs-lookup"><span data-stu-id="c1aa9-190">A resource search uses the GET method and the following parameters:</span></span>

1. <span data-ttu-id="c1aa9-191">患者 =\<患者 id></span><span class="sxs-lookup"><span data-stu-id="c1aa9-191">patient=\<patient id></span></span>
2. <span data-ttu-id="c1aa9-192">_count =\<最大 results></span><span class="sxs-lookup"><span data-stu-id="c1aa9-192">_count=\<max results></span></span>

<span data-ttu-id="c1aa9-193">请参阅下面的示例，此呼叫的：</span><span class="sxs-lookup"><span data-stu-id="c1aa9-193">See the following example of this call:</span></span>

* * *

    <span data-ttu-id="c1aa9-194">请求： 获取 <fhir server>/条件？ 患者 = <patient id>&_count = 10</span><span class="sxs-lookup"><span data-stu-id="c1aa9-194">Request: GET <fhir-server>/Condition?patient=<patient-id>&_count=10</span></span>
    
    <span data-ttu-id="c1aa9-195">响应: {"resourceType":"捆绑"、"id":"<bundle id>"、"类型":"searchset"，"total": 2，entry: [{"资源": {"resourceType":"条件"、"id":"<resource id>"、"代码": {"编码": [{"系统":"http://snomed.info/sct"，"代码":"185903001"，"显示":"需求流感免疫"}]}，"severity": {"编码": [{"系统":"http://snomed.info/sct"，"代码":"24484000"，"显示":"严重"}]}，"assertedDate":"2018年-04-04"}}。</span><span class="sxs-lookup"><span data-stu-id="c1aa9-195">Response: { "resourceType": "Bundle", "id": "<bundle-id>", "type": "searchset", "total": 2, "entry": [ { "resource": { "resourceType": "Condition", "id": "<resource-id>", "code": { "coding": [ { "system": "http://snomed.info/sct", "code": "185903001", "display": "Needs influenza immunization", } ] }, "severity": { "coding": [ { "system": "http://snomed.info/sct", "code": "24484000", "display": "Severe" } ] }, "assertedDate": "2018-04-04" } }, .</span></span>
        <span data-ttu-id="c1aa9-196">.</span><span class="sxs-lookup"><span data-stu-id="c1aa9-196"></span></span>
        <span data-ttu-id="c1aa9-197">.</span><span class="sxs-lookup"><span data-stu-id="c1aa9-197"></span></span>
      <span data-ttu-id="c1aa9-198">] }</span><span class="sxs-lookup"><span data-stu-id="c1aa9-198"></span></span>

* * *
<span data-ttu-id="c1aa9-199">请参阅[http://hl7.org/fhir/stu3/condition.html](http://hl7.org/fhir/stu3/condition.html)有关此字段的其他详细信息设置。</span><span class="sxs-lookup"><span data-stu-id="c1aa9-199">See [http://hl7.org/fhir/stu3/condition.html](http://hl7.org/fhir/stu3/condition.html) for other details on this field set.</span></span>

## <a name="encounter"></a><span data-ttu-id="c1aa9-200">遇到</span><span class="sxs-lookup"><span data-stu-id="c1aa9-200">Encounter</span></span>

<span data-ttu-id="c1aa9-201">这些是最小的必填的字段，它们是[美国核心遇到配置文件](http://hl7.org/fhir/us/core/2018Jan/StructureDefinition-us-core-encounter.html)"必须具有"字段的子集。）</span><span class="sxs-lookup"><span data-stu-id="c1aa9-201">These are the minimum required fields, which are a subset of the [US Core Encounter profile](http://hl7.org/fhir/us/core/2018Jan/StructureDefinition-us-core-encounter.html) “must have” fields).</span></span>

1. <span data-ttu-id="c1aa9-202">状态</span><span class="sxs-lookup"><span data-stu-id="c1aa9-202">Status</span></span>
2. <span data-ttu-id="c1aa9-203">类型 [0]。编码 [0]。显示</span><span class="sxs-lookup"><span data-stu-id="c1aa9-203">Type[0].Coding[0].Display</span></span>

<span data-ttu-id="c1aa9-204">此外，从美国核心遇到配置文件的以下字段"必须支持"字段：</span><span class="sxs-lookup"><span data-stu-id="c1aa9-204">In addition, the following fields from US Core Encounter profile’s “must support” fields:</span></span>

1. <span data-ttu-id="c1aa9-205">Period.Start</span><span class="sxs-lookup"><span data-stu-id="c1aa9-205">Period.Start</span></span>
2. <span data-ttu-id="c1aa9-206">位置 [0]。Location.Display</span><span class="sxs-lookup"><span data-stu-id="c1aa9-206">Location[0].Location.Display</span></span>

<span data-ttu-id="c1aa9-207">资源搜索使用 GET 方法并使用以下参数：</span><span class="sxs-lookup"><span data-stu-id="c1aa9-207">A resource search uses the GET method and the following parameters:</span></span>

1. <span data-ttu-id="c1aa9-208">患者 =\<患者 id></span><span class="sxs-lookup"><span data-stu-id="c1aa9-208">patient=\<patient id></span></span>
2. <span data-ttu-id="c1aa9-209">_sort:desc =\<ex 字段。</span><span class="sxs-lookup"><span data-stu-id="c1aa9-209">_sort:desc=\<field ex.</span></span> <span data-ttu-id="c1aa9-210">date></span><span class="sxs-lookup"><span data-stu-id="c1aa9-210">date></span></span>
3. <span data-ttu-id="c1aa9-211">_count =\<最大 results></span><span class="sxs-lookup"><span data-stu-id="c1aa9-211">_count=\<max results></span></span>

<span data-ttu-id="c1aa9-212">目标是能够检索患者的最后一个已知的位置。</span><span class="sxs-lookup"><span data-stu-id="c1aa9-212">The goal is to be able to retrieve the patient’s last known location.</span></span> <span data-ttu-id="c1aa9-213">每个遇到引用的位置资源。</span><span class="sxs-lookup"><span data-stu-id="c1aa9-213">Each encounter references a location resource.</span></span> <span data-ttu-id="c1aa9-214">引用还应包括的位置显示字段。</span><span class="sxs-lookup"><span data-stu-id="c1aa9-214">The reference shall also include the location’s display field.</span></span>

<span data-ttu-id="c1aa9-215">请参阅[http://hl7.org/fhir/stu3/encounter.html](http://hl7.org/fhir/stu3/encounter.html)有关此字段的其他详细信息设置。</span><span class="sxs-lookup"><span data-stu-id="c1aa9-215">See [http://hl7.org/fhir/stu3/encounter.html](http://hl7.org/fhir/stu3/encounter.html) for other details on this field set.</span></span>

## <a name="allergyintolerance"></a><span data-ttu-id="c1aa9-216">AllergyIntolerance</span><span class="sxs-lookup"><span data-stu-id="c1aa9-216">AllergyIntolerance</span></span>

<span data-ttu-id="c1aa9-217">这是最小必填的字段，是[Argonaut AllergyIntolerance](https://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-allergyintolerance.html)配置文件的子集：</span><span class="sxs-lookup"><span data-stu-id="c1aa9-217">These are the minimum required fields, which are a subset of the [Argonaut AllergyIntolerance](https://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-allergyintolerance.html) profile:</span></span>

1. <span data-ttu-id="c1aa9-218">Code.Text</span><span class="sxs-lookup"><span data-stu-id="c1aa9-218">Code.Text</span></span>
2. <span data-ttu-id="c1aa9-219">Code.Coding[0]。显示</span><span class="sxs-lookup"><span data-stu-id="c1aa9-219">Code.Coding[0].Display</span></span>
3. <span data-ttu-id="c1aa9-220">ClinicalStatus/VerificationStatus （我们读取两者）</span><span class="sxs-lookup"><span data-stu-id="c1aa9-220">ClinicalStatus/VerificationStatus (we read both)</span></span>

<span data-ttu-id="c1aa9-221">除了 Argonaut 字段中，为出色的用户体验患者应用程序还可以阅读以下字段：</span><span class="sxs-lookup"><span data-stu-id="c1aa9-221">In addition to the Argonaut fields, for a great user experience the Patients app can also read the following field:</span></span>

1. <span data-ttu-id="c1aa9-222">AssertedDate</span><span class="sxs-lookup"><span data-stu-id="c1aa9-222">AssertedDate</span></span>
2. <span data-ttu-id="c1aa9-223">Note.Text</span><span class="sxs-lookup"><span data-stu-id="c1aa9-223">Note.Text</span></span>
3. <span data-ttu-id="c1aa9-224">反应</span><span class="sxs-lookup"><span data-stu-id="c1aa9-224">Reaction</span></span>
    1. <span data-ttu-id="c1aa9-225">材料 （一个编码元素）</span><span class="sxs-lookup"><span data-stu-id="c1aa9-225">Substance (one coding element)</span></span>
    2. <span data-ttu-id="c1aa9-226">体现 （一个编码元素）</span><span class="sxs-lookup"><span data-stu-id="c1aa9-226">Manifestation (one coding element)</span></span>

<span data-ttu-id="c1aa9-227">资源搜索使用 GET 方法并使用以下参数：</span><span class="sxs-lookup"><span data-stu-id="c1aa9-227">A resource search uses the GET method and the following parameters:</span></span>

1. <span data-ttu-id="c1aa9-228">患者 =\<患者 id></span><span class="sxs-lookup"><span data-stu-id="c1aa9-228">Patient =  \<patient id></span></span>

<span data-ttu-id="c1aa9-229">请参阅下面的示例的呼叫：</span><span class="sxs-lookup"><span data-stu-id="c1aa9-229">See the following example of the call:</span></span> 

* * *

    <span data-ttu-id="c1aa9-230">请求： 获取 <fhir-server>/AllergyIntolerance？ 患者 = <patient id></span><span class="sxs-lookup"><span data-stu-id="c1aa9-230">Request: GET <fhir-server>/AllergyIntolerance?patient=<patient-id></span></span>
    
    <span data-ttu-id="c1aa9-231">响应: {"resourceType":"捆绑"、"id":"<bundle id>"、"类型":"searchset"，"total": 1，entry: [{"资源": {"resourceType":"AllergyIntolerance"，"id":"<resource id>"、"clinicalStatus":"活动"，"verificationStatus":"确认"，"代码": {"编码": [{"系统":"http://rxnav.nlm.nih.gov/REST/Ndfrt"，"代码":"N0000175503"，"显示":"sulfonamide antibacterial"}]，"text":"sulfonamide antibacterial"}，"assertedDate":"2018年-01-01T00:00:00-07:00"，"反应": [{"体现": [{"编码": [{"系统":"http://snomed.info/sct"，"代码": "271807003"，"显示":"外观一连串"}]，"text":"外观一连串"}]，}]}}]}</span><span class="sxs-lookup"><span data-stu-id="c1aa9-231">Response: {   "resourceType": "Bundle",   "id": "<bundle-id>",   "type": "searchset",   "total": 1,   "entry": [     {       "resource": {         "resourceType": "AllergyIntolerance",         "id": "<resource-id>",         "clinicalStatus": "active",         "verificationStatus": "confirmed",         "code": {           "coding": [             {               "system": "http://rxnav.nlm.nih.gov/REST/Ndfrt",               "code": "N0000175503",               "display": "sulfonamide antibacterial",             }           ],           "text": "sulfonamide antibacterial"         },         "assertedDate": "2018-01-01T00:00:00-07:00",         "reaction": [           {             "manifestation": [               {                 "coding": [                   {                     "system": "http://snomed.info/sct",                     "code": "271807003",                     "display": "skin rash",                   }                 ],                 "text": "skin rash"               }             ],           }         ]       }     }   ] }</span></span>

* * *

<span data-ttu-id="c1aa9-232">请参阅[http://hl7.org/fhir/stu3/allergyintolerance.html](http://hl7.org/fhir/stu3/allergyintolerance.html)有关此字段的其他详细信息设置。</span><span class="sxs-lookup"><span data-stu-id="c1aa9-232">See [http://hl7.org/fhir/stu3/allergyintolerance.html](http://hl7.org/fhir/stu3/allergyintolerance.html) for other details on this field set.</span></span>

## <a name="medication-request"></a><span data-ttu-id="c1aa9-233">用药请求</span><span class="sxs-lookup"><span data-stu-id="c1aa9-233">Medication Request</span></span>

<span data-ttu-id="c1aa9-234">这是最小必填的字段，是[美国核心用药请求配置文件](http://www.hl7.org/fhir/us/core/StructureDefinition-us-core-medicationrequest.html)的子集：</span><span class="sxs-lookup"><span data-stu-id="c1aa9-234">These are the minimum required fields, which are a subset of the [US Core Medication Request profile](http://www.hl7.org/fhir/us/core/StructureDefinition-us-core-medicationrequest.html):</span></span>

1. <span data-ttu-id="c1aa9-235">Medication.Display (如果引用)</span><span class="sxs-lookup"><span data-stu-id="c1aa9-235">Medication.Display (if Reference)</span></span>
2. <span data-ttu-id="c1aa9-236">Medication.Text (如果 CodableConcept)</span><span class="sxs-lookup"><span data-stu-id="c1aa9-236">Medication.Text (if CodableConcept)</span></span>
3. <span data-ttu-id="c1aa9-237">AuthoredOn</span><span class="sxs-lookup"><span data-stu-id="c1aa9-237">AuthoredOn</span></span>
4. <span data-ttu-id="c1aa9-238">Requester.Agent.Display</span><span class="sxs-lookup"><span data-stu-id="c1aa9-238">Requester.Agent.Display</span></span>

<span data-ttu-id="c1aa9-239">除了美国核心字段中，为出色的用户体验患者应用程序还可以阅读以下字段：</span><span class="sxs-lookup"><span data-stu-id="c1aa9-239">In addition to the US Core fields, for a great user experience the Patients app can also read the following fields:</span></span>

1. <span data-ttu-id="c1aa9-240">DosageInstruction [.]。文本</span><span class="sxs-lookup"><span data-stu-id="c1aa9-240">DosageInstruction[..].Text</span></span>
2. <span data-ttu-id="c1aa9-241">文本</span><span class="sxs-lookup"><span data-stu-id="c1aa9-241">Text</span></span>

<span data-ttu-id="c1aa9-242">资源搜索使用 GET 方法并使用以下参数：</span><span class="sxs-lookup"><span data-stu-id="c1aa9-242">A resource search uses the GET method and the following parameters:</span></span>

1. <span data-ttu-id="c1aa9-243">患者 =\<患者 id></span><span class="sxs-lookup"><span data-stu-id="c1aa9-243">patient=\<patient id></span></span>
2. <span data-ttu-id="c1aa9-244">_count =\<最大 results></span><span class="sxs-lookup"><span data-stu-id="c1aa9-244">_count=\<max results></span></span>

<span data-ttu-id="c1aa9-245">请参阅[https://www.hl7.org/fhir/medicationrequest.html](https://www.hl7.org/fhir/medicationrequest.html)有关此字段的其他详细信息设置。</span><span class="sxs-lookup"><span data-stu-id="c1aa9-245">See [https://www.hl7.org/fhir/medicationrequest.html](https://www.hl7.org/fhir/medicationrequest.html) for other details on this field set.</span></span>

## <a name="coverage"></a><span data-ttu-id="c1aa9-246">覆盖范围</span><span class="sxs-lookup"><span data-stu-id="c1aa9-246">Coverage</span></span>

<span data-ttu-id="c1aa9-247">这是最小的必填的字段，不受美国核心或 Argonaut 配置文件：</span><span class="sxs-lookup"><span data-stu-id="c1aa9-247">These are the minimum required fields, not covered by either US Core or Argonaut profiles:</span></span>

1. <span data-ttu-id="c1aa9-248">分组，至少一个元素</span><span class="sxs-lookup"><span data-stu-id="c1aa9-248">Grouping, at least one element with</span></span>
    1. <span data-ttu-id="c1aa9-249">GroupDisplay</span><span class="sxs-lookup"><span data-stu-id="c1aa9-249">GroupDisplay</span></span>
    2. <span data-ttu-id="c1aa9-250">PlanDisplay</span><span class="sxs-lookup"><span data-stu-id="c1aa9-250">PlanDisplay</span></span>
2. <span data-ttu-id="c1aa9-251">时间段</span><span class="sxs-lookup"><span data-stu-id="c1aa9-251">Period</span></span>
3. <span data-ttu-id="c1aa9-252">SubscriberId</span><span class="sxs-lookup"><span data-stu-id="c1aa9-252">SubscriberId</span></span>

<span data-ttu-id="c1aa9-253">资源搜索使用 GET 方法并使用以下参数：</span><span class="sxs-lookup"><span data-stu-id="c1aa9-253">A resource search uses the GET method and the following parameters:</span></span>

1. <span data-ttu-id="c1aa9-254">患者 =\<患者 id></span><span class="sxs-lookup"><span data-stu-id="c1aa9-254">Patient = \<patient id></span></span>

<span data-ttu-id="c1aa9-255">请参阅[http://hl7.org/fhir/stu3/coverage.html](https://www.hl7.org/fhir/medicationrequest.html)有关此字段的其他详细信息设置。</span><span class="sxs-lookup"><span data-stu-id="c1aa9-255">See [http://hl7.org/fhir/stu3/coverage.html](https://www.hl7.org/fhir/medicationrequest.html) for other details on this field set.</span></span>
