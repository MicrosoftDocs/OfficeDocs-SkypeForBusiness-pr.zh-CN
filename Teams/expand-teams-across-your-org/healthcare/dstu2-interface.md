---
title: " 患者应用程序和 EHR 集成 DSTU2 接口"
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
ms.openlocfilehash: 85fd90fb338f8b19762dc9433fa1dc281f3cedff
ms.sourcegitcommit: cf2cb5b7e03385b33e34a5ff89719adb882525b1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/06/2019
ms.locfileid: "33643071"
---
# <a name="dstu2-interface-specification"></a><span data-ttu-id="474be-103">DSTU2 接口规范</span><span class="sxs-lookup"><span data-stu-id="474be-103">DSTU2 interface specification</span></span>

[!INCLUDE [preview-feature](../../includes/preview-feature.md)]

<span data-ttu-id="474be-104">设置或重新配置 FHIR server 以使用 Microsoft 团队患者应用程序需要了解哪些应用程序需要访问的数据。</span><span class="sxs-lookup"><span data-stu-id="474be-104">Setting up or reconfiguring an FHIR server to work with the Microsoft Teams Patients app requires understanding what data the app needs to access.</span></span> <span data-ttu-id="474be-105">FHIR 服务器必须支持的以下资源使用捆绑的 POST 请求：</span><span class="sxs-lookup"><span data-stu-id="474be-105">The FHIR server must support POST requests using bundles for the following resources:</span></span>

- [<span data-ttu-id="474be-106">患者</span><span class="sxs-lookup"><span data-stu-id="474be-106">Patient</span></span>](#patient)
- [<span data-ttu-id="474be-107">观察值</span><span class="sxs-lookup"><span data-stu-id="474be-107">Observation</span></span>](#observation)
- [<span data-ttu-id="474be-108">条件</span><span class="sxs-lookup"><span data-stu-id="474be-108">Condition</span></span>](#condition)
- [<span data-ttu-id="474be-109">遇到</span><span class="sxs-lookup"><span data-stu-id="474be-109">Encounter</span></span>](#encounter)
- [<span data-ttu-id="474be-110">过敏 intolerance</span><span class="sxs-lookup"><span data-stu-id="474be-110">Allergy intolerance</span></span>](#allergyintolerance)
- [<span data-ttu-id="474be-111">覆盖范围</span><span class="sxs-lookup"><span data-stu-id="474be-111">Coverage</span></span>](#coverage)
- [<span data-ttu-id="474be-112">用药顺序</span><span class="sxs-lookup"><span data-stu-id="474be-112">Medication Order</span></span>](#medication-order)
- [<span data-ttu-id="474be-113">位置</span><span class="sxs-lookup"><span data-stu-id="474be-113">Location</span></span>](#location)

> [!NOTE]
> <span data-ttu-id="474be-114">患者资源是唯一的必填资源 （该应用程序将不会加载根本。</span><span class="sxs-lookup"><span data-stu-id="474be-114">The Patient resource is the only mandatory resource (without which the app will not load at all.</span></span> <span data-ttu-id="474be-115">但是，建议合作伙伴实现支持的每个规范下面提供的 Microsoft 团队患者 App 最佳最终用户体验的所有上面提到资源。</span><span class="sxs-lookup"><span data-stu-id="474be-115">However, it is recommended that the Partner implement support for all the above mentioned resources per specifications provided below for the best end-user experience with the Microsoft Teams Patients App.</span></span>

<span data-ttu-id="474be-116">查询从多个资源的 Microsoft 团队患者应用程序发布到 FHIR 服务器的 URL 的请求的绑定 （批次）。</span><span class="sxs-lookup"><span data-stu-id="474be-116">Queries from the Microsoft Teams Patients app for more than one resource post a bundle (BATCH) of requests to the FHIR server's URL.</span></span> <span data-ttu-id="474be-117">该服务器处理每个请求，并返回匹配的每个请求的资源的绑定。</span><span class="sxs-lookup"><span data-stu-id="474be-117">The server processes each request and returns a bundle of the resources matched by each request.</span></span> <span data-ttu-id="474be-118">有关详细信息和示例，请参阅[https://www.hl7.org/fhir/DSTU2/http.html#transaction](https://www.hl7.org/fhir/DSTU2/http.html#transaction)。</span><span class="sxs-lookup"><span data-stu-id="474be-118">For more information and examples, see [https://www.hl7.org/fhir/DSTU2/http.html#transaction](https://www.hl7.org/fhir/DSTU2/http.html#transaction).</span></span>

<span data-ttu-id="474be-119">下列所有 FHIR 资源应都可访问的直接资源引用。</span><span class="sxs-lookup"><span data-stu-id="474be-119">All the following FHIR resources should be accessible by direct resource reference.</span></span>

## <a name="conformance-minimum-required-field-set"></a><span data-ttu-id="474be-120">一致性声明最低必填的字段设置</span><span class="sxs-lookup"><span data-stu-id="474be-120">Conformance minimum required field set</span></span>

 <span data-ttu-id="474be-121">FHIR 服务器必须实现一致性的我们可以真实其功能的摘要。</span><span class="sxs-lookup"><span data-stu-id="474be-121">The FHIR Server must implement the conformance statement for us to have a factual summary of its capabilities.</span></span> <span data-ttu-id="474be-122">我们期望 DSTU2 FHIR 服务器中的参数如下：</span><span class="sxs-lookup"><span data-stu-id="474be-122">We expect the below parameters in a DSTU2 FHIR Server:</span></span>

1. <span data-ttu-id="474be-123">REST</span><span class="sxs-lookup"><span data-stu-id="474be-123">REST</span></span>
   1. <span data-ttu-id="474be-124">模式</span><span class="sxs-lookup"><span data-stu-id="474be-124">Mode</span></span>
   2. <span data-ttu-id="474be-125">交互</span><span class="sxs-lookup"><span data-stu-id="474be-125">Interaction</span></span>
   3. <span data-ttu-id="474be-126">资源： 类型</span><span class="sxs-lookup"><span data-stu-id="474be-126">Resource: Type</span></span>
   4. <span data-ttu-id="474be-127">安全性：[扩展的 OAuth Uri](http://hl7.org/fhir/extension-oauth-uris.html)</span><span class="sxs-lookup"><span data-stu-id="474be-127">Security: [Extension for OAuth URIs](http://hl7.org/fhir/extension-oauth-uris.html)</span></span>
2. <span data-ttu-id="474be-128">FhirVersion （我们的代码需要此选项可了解我们应该因为我们支持多个版本侧重于哪个版本。）</span><span class="sxs-lookup"><span data-stu-id="474be-128">FhirVersion (Our code requires this to understand which version we should pivot to as we support multiple versions.)</span></span>

<span data-ttu-id="474be-129">请参阅[https://www.hl7.org/fhir/dstu2/conformance.html](https://www.hl7.org/fhir/dstu2/conformance.html)有关此字段的其他详细信息设置。</span><span class="sxs-lookup"><span data-stu-id="474be-129">See [https://www.hl7.org/fhir/dstu2/conformance.html](https://www.hl7.org/fhir/dstu2/conformance.html) for other details on this field set.</span></span>

## <a name="patient"></a><span data-ttu-id="474be-130">患者</span><span class="sxs-lookup"><span data-stu-id="474be-130">Patient</span></span>

<span data-ttu-id="474be-131">这是最小的必填的字段，它们是[Argonaut 患者配置文件](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-patient.html)字段的子集：</span><span class="sxs-lookup"><span data-stu-id="474be-131">These are the minimum required fields, which are a subset of the [Argonaut patient profile](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-patient.html) fields:</span></span>

1. <span data-ttu-id="474be-132">Name.Family</span><span class="sxs-lookup"><span data-stu-id="474be-132">Name.Family</span></span>
2. <span data-ttu-id="474be-133">Name.Given</span><span class="sxs-lookup"><span data-stu-id="474be-133">Name.Given</span></span>
3. <span data-ttu-id="474be-134">性别</span><span class="sxs-lookup"><span data-stu-id="474be-134">Gender</span></span>
4. <span data-ttu-id="474be-135">出生日期</span><span class="sxs-lookup"><span data-stu-id="474be-135">BirthDate</span></span>
5. <span data-ttu-id="474be-136">MRN （标识符）</span><span class="sxs-lookup"><span data-stu-id="474be-136">MRN (Identifier)</span></span>

<span data-ttu-id="474be-137">除了 Argonaut 字段中，对于出色的用户体验患者应用程序还读取以下字段：</span><span class="sxs-lookup"><span data-stu-id="474be-137">In addition to the Argonaut fields, for a great user experience the Patients app also reads the following fields:</span></span>

1. <span data-ttu-id="474be-138">Name.Use</span><span class="sxs-lookup"><span data-stu-id="474be-138">Name.Use</span></span>
2. <span data-ttu-id="474be-139">Name.Prefix</span><span class="sxs-lookup"><span data-stu-id="474be-139">Name.Prefix</span></span>
3. <span data-ttu-id="474be-140">CareProvider （对患者资源本参考应包含在以下示例中所示的显示字段）。</span><span class="sxs-lookup"><span data-stu-id="474be-140">CareProvider (This reference on the Patient resource should include the display fields shown in the following example.)</span></span>

* * *

    <span data-ttu-id="474be-141">请求： 获取 <fhir-server>/患者/<patient-id></span><span class="sxs-lookup"><span data-stu-id="474be-141">Request: GET <fhir-server>/Patient/<patient-id></span></span>
    
    <span data-ttu-id="474be-142">响应: {"resourceType":"患者"，"id":"<patient-id>"。</span><span class="sxs-lookup"><span data-stu-id="474be-142">Response: { "resourceType": "Patient", "id": "<patient-id>", .</span></span>
      <span data-ttu-id="474be-143">.</span><span class="sxs-lookup"><span data-stu-id="474be-143"></span></span>
      <span data-ttu-id="474be-144">.</span><span class="sxs-lookup"><span data-stu-id="474be-144"></span></span>
      <span data-ttu-id="474be-145">"名称": [{"使用":"正式"，"前缀":"Mr""系列":"Chau""授予":"Hugh"}]，"标识符": [{"使用":"正式"，"类型": {"编码": [{"系统":"http://hl7.org/fhir/v2/0203"，"代码":"MR"}]}，"value":"1234567"}]，"性别":"男"，"出生日期": 1957年"-06-05"，"careProvider": [{"显示":"Jane Doe"}]，}</span><span class="sxs-lookup"><span data-stu-id="474be-145">"name": [ { "use": "official", "prefix": [ "Mr" ], "family": [ "Chau" ], "given": [ "Hugh" ] } ], "identifier": [ { "use": "official", "type": { "coding": [ { "system": "http://hl7.org/fhir/v2/0203", "code": "MR" } ] }, "value": "1234567" } ], "gender": "male", "birthDate": "1957-06-05", "careProvider": [{ "display": "Jane Doe" }], }</span></span>

* * *

<span data-ttu-id="474be-146">资源搜索使用 POST 方法 /Patient/_search 和以下参数：</span><span class="sxs-lookup"><span data-stu-id="474be-146">A resource search uses the POST method at /Patient/_search and the following parameters:</span></span>

1. <span data-ttu-id="474be-147">id</span><span class="sxs-lookup"><span data-stu-id="474be-147">id</span></span>
2. <span data-ttu-id="474be-148">系列： 包含 = （系列名称中包含值的所有患者搜索）。</span><span class="sxs-lookup"><span data-stu-id="474be-148">family:contains=(searches for all patients whose family name contains the value.)</span></span>
3. <span data-ttu-id="474be-149">给定 =\<substring></span><span class="sxs-lookup"><span data-stu-id="474be-149">given=\<substring></span></span>
4. <span data-ttu-id="474be-150">名称 =\<substring></span><span class="sxs-lookup"><span data-stu-id="474be-150">name=\<substring></span></span>
5. <span data-ttu-id="474be-151">出生日期 =(exact match)</span><span class="sxs-lookup"><span data-stu-id="474be-151">birthdate=(exact match)</span></span>
6. <span data-ttu-id="474be-152">\_计数 （最大应返回的结果数）</span><span class="sxs-lookup"><span data-stu-id="474be-152">\_count (maximum number of results that should be returned)</span></span> <br> <span data-ttu-id="474be-153">响应应包含的搜索，由于返回记录的总计数和\_计数将由 PatientsApp 以限制返回的记录数。</span><span class="sxs-lookup"><span data-stu-id="474be-153">The response should contain the total count of records returned as a result of the search, and \_count will be used by the PatientsApp to limit the number of records returned.</span></span>
7. <span data-ttu-id="474be-154">标识符 =\<mrn></span><span class="sxs-lookup"><span data-stu-id="474be-154">identifier=\<mrn></span></span>

<span data-ttu-id="474be-155">目标是能够搜索和筛选由以下患者：</span><span class="sxs-lookup"><span data-stu-id="474be-155">The goal is to be able to search and filter for a patient by the following:</span></span>

- <span data-ttu-id="474be-156">ID： 这是每个资源 FHIR 中的包含的资源 ID。</span><span class="sxs-lookup"><span data-stu-id="474be-156">ID: This is the resource ID that every resource in FHIR has.</span></span>
- <span data-ttu-id="474be-157">MRN： 这是患者临床人员自己知道的实际标识符。</span><span class="sxs-lookup"><span data-stu-id="474be-157">MRN: This is the actual identifier for the patient that clinical staff would know.</span></span> <span data-ttu-id="474be-158">我们了解此 MRN 基于内 FHIR 标识符资源的标识符的类型</span><span class="sxs-lookup"><span data-stu-id="474be-158">We understand this MRN is based on the type of identifier inside the identifier resource in FHIR</span></span>
- <span data-ttu-id="474be-159">名称</span><span class="sxs-lookup"><span data-stu-id="474be-159">Name</span></span>
- <span data-ttu-id="474be-160">出生日期</span><span class="sxs-lookup"><span data-stu-id="474be-160">Birthdate</span></span>

<span data-ttu-id="474be-161">请参阅下面的示例的此呼叫。</span><span class="sxs-lookup"><span data-stu-id="474be-161">See the following example  of this call.</span></span>

* * *

    <span data-ttu-id="474be-162">请求： POST <fhir-server>/患者/_search 请求正文： 给定 = hugh&family = chau</span><span class="sxs-lookup"><span data-stu-id="474be-162">Request: POST <fhir-server>/Patient/_search Request Body: given=hugh&family=chau</span></span>
    
    <span data-ttu-id="474be-163">响应: {"resourceType":"捆绑"、"id":"<bundle-id>"。</span><span class="sxs-lookup"><span data-stu-id="474be-163">Response: { "resourceType": "Bundle", "id": "<bundle-id>", .</span></span>
      <span data-ttu-id="474be-164">.</span><span class="sxs-lookup"><span data-stu-id="474be-164"></span></span>
      <span data-ttu-id="474be-165">.</span><span class="sxs-lookup"><span data-stu-id="474be-165"></span></span>
      <span data-ttu-id="474be-166">entry: [{"资源": {"resourceType":"患者"，"id":"<patient id>"、"name": [{"text":"Hugh Chau"，在"系列":"Chau""授予":"Hugh"}]，"性别":"男"，"出生日期":"1957年 06 05"}，"搜索": {"模式":"匹配"}}]}</span><span class="sxs-lookup"><span data-stu-id="474be-166">"entry": [ { "resource": { "resourceType": "Patient", "id": "<patient-id>", "name": [ { "text": "Hugh Chau", "family": [ "Chau" ], "given": [ "Hugh" ] } ], "gender": "male", "birthDate": "1957-06-05" }, "search": { "mode": "match" } } ] }</span></span>

* * *

<span data-ttu-id="474be-167">请参阅[https://www.hl7.org/fhir/DSTU2/Patient.html](https://www.hl7.org/fhir/DSTU2/Patient.html)有关此字段的其他详细信息设置。</span><span class="sxs-lookup"><span data-stu-id="474be-167">See [https://www.hl7.org/fhir/DSTU2/Patient.html](https://www.hl7.org/fhir/DSTU2/Patient.html) for other details on this field set.</span></span>

## <a name="observation"></a><span data-ttu-id="474be-168">观察值</span><span class="sxs-lookup"><span data-stu-id="474be-168">Observation</span></span>

<span data-ttu-id="474be-169">这是最小必填的字段，是 Argonaut 重要征兆配置文件的子集：</span><span class="sxs-lookup"><span data-stu-id="474be-169">These are the minimum required fields, which are a subset of the Argonaut vital signs profile:</span></span>

 1. <span data-ttu-id="474be-170">有效 （日期时间或段）</span><span class="sxs-lookup"><span data-stu-id="474be-170">Effective (date time or period)</span></span>
 2. <span data-ttu-id="474be-171">Code.Coding.Code</span><span class="sxs-lookup"><span data-stu-id="474be-171">Code.Coding.Code</span></span>
 3. <span data-ttu-id="474be-172">ValueQuantity.Value</span><span class="sxs-lookup"><span data-stu-id="474be-172">ValueQuantity.Value</span></span>

<span data-ttu-id="474be-173">除了 Argonaut 字段中，对于出色的用户体验患者应用程序还读取以下字段：</span><span class="sxs-lookup"><span data-stu-id="474be-173">In addition to the Argonaut fields, for a great user experience the Patients app also reads the following fields:</span></span>

 1. <span data-ttu-id="474be-174">Code.Coding.Display</span><span class="sxs-lookup"><span data-stu-id="474be-174">Code.Coding.Display</span></span>
 2. <span data-ttu-id="474be-175">ValueQuantity.Unit</span><span class="sxs-lookup"><span data-stu-id="474be-175">ValueQuantity.Unit</span></span>

<span data-ttu-id="474be-176">如果使用组件观察，相同的逻辑将适用于每个组件观察值。</span><span class="sxs-lookup"><span data-stu-id="474be-176">If using component observations, the same logic applies for each component observation.</span></span>

<span data-ttu-id="474be-177">资源搜索使用 GET 方法并使用以下参数：</span><span class="sxs-lookup"><span data-stu-id="474be-177">A resource search uses the GET method and the following parameters:</span></span>

1. <span data-ttu-id="474be-178">患者 =\<患者 id\></span><span class="sxs-lookup"><span data-stu-id="474be-178">patient=\<patient id\></span></span>
2. <span data-ttu-id="474be-179">排序： desc =\<ex 字段。</span><span class="sxs-lookup"><span data-stu-id="474be-179">sort:desc=\<field ex.</span></span> <span data-ttu-id="474be-180">日期\></span><span class="sxs-lookup"><span data-stu-id="474be-180">date\></span></span>

<span data-ttu-id="474be-181">目标是能够检索为患者，[VitalSigns.DSTU.saz] （观察？） 的最新的重要标志。</span><span class="sxs-lookup"><span data-stu-id="474be-181">The goal is to be able to retrieve the latest vital signs for a patient, [VitalSigns.DSTU.saz]  (observation?).</span></span>

* * *

    <span data-ttu-id="474be-182">请求： 获取观察值 <fhir-server>？ 患者 = <patient-id>&_sort:desc = date&category = 重要迹象</span><span class="sxs-lookup"><span data-stu-id="474be-182">Request: GET <fhir-server>/Observation?patient=<patient-id>&_sort:desc=date&category=vital-signs</span></span>
    
    <span data-ttu-id="474be-183">响应: {"resourceType":"捆绑"、"id":"<bundle id>"、"类型":"searchset"，"total": 20，entry: [{"资源": {"resourceType":"观察值"、"id":"<resource id>"、"category": {"编码": [{代码":"重要迹象"}]，}，"代码": {"编码": [{"系统":"http://loinc.org"，"代码":"39156-5"，"显示":"bmi"}]，}，"effectiveDateTime":"2009年-12-01"，"valueQuantity": {"value": 34.4，"单位":"千克/m2"、"系统":"http://unitsofmeasure.org"，"代码":"千克/m2"}}，}。</span><span class="sxs-lookup"><span data-stu-id="474be-183">Response: { "resourceType": "Bundle", "id": "<bundle-id>", "type": "searchset", "total": 20, "entry": [ { "resource": { "resourceType": "Observation", "id": "<resource-id>", "category": { "coding": [ { code": "vital-signs" } ], }, "code": { "coding": [ { "system": "http://loinc.org", "code": "39156-5", "display": "bmi" } ], }, "effectiveDateTime": "2009-12-01", "valueQuantity": { "value": 34.4, "unit": "kg/m2", "system": "http://unitsofmeasure.org", "code": "kg/m2" } }, }, .</span></span>
        <span data-ttu-id="474be-184">.</span><span class="sxs-lookup"><span data-stu-id="474be-184"></span></span>
        <span data-ttu-id="474be-185">.</span><span class="sxs-lookup"><span data-stu-id="474be-185"></span></span>
      <span data-ttu-id="474be-186">] }</span><span class="sxs-lookup"><span data-stu-id="474be-186"></span></span>

* * *

<span data-ttu-id="474be-187">请参阅[https://www.hl7.org/fhir/DSTU2/Observation.html](https://www.hl7.org/fhir/DSTU2/Observation.html)有关此字段的其他详细信息设置。</span><span class="sxs-lookup"><span data-stu-id="474be-187">See [https://www.hl7.org/fhir/DSTU2/Observation.html](https://www.hl7.org/fhir/DSTU2/Observation.html) for other details on this field set.</span></span>

## <a name="condition"></a><span data-ttu-id="474be-188">条件</span><span class="sxs-lookup"><span data-stu-id="474be-188">Condition</span></span>

<span data-ttu-id="474be-189">这是最小必填的字段，是[Argonaut 条件配置文件](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-condition.html)的子集：</span><span class="sxs-lookup"><span data-stu-id="474be-189">These are the minimum required fields, which are a subset of the [Argonaut condition profile](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-condition.html):</span></span>

1. <span data-ttu-id="474be-190">Code.Coding[0]。显示</span><span class="sxs-lookup"><span data-stu-id="474be-190">Code.Coding[0].Display</span></span>

<span data-ttu-id="474be-191">除了 Argonaut 字段中，为出色的用户体验患者应用程序还可以阅读以下字段：</span><span class="sxs-lookup"><span data-stu-id="474be-191">In addition to the Argonaut fields, for a great user experience the Patients app can also read the following fields:</span></span>

1. <span data-ttu-id="474be-192">记录日期</span><span class="sxs-lookup"><span data-stu-id="474be-192">Date Recorded</span></span>
2. <span data-ttu-id="474be-193">严重级别</span><span class="sxs-lookup"><span data-stu-id="474be-193">Severity</span></span>

<span data-ttu-id="474be-194">资源搜索使用 GET 方法并使用以下参数：</span><span class="sxs-lookup"><span data-stu-id="474be-194">A resource search uses the GET method and the following parameters:</span></span>

1. <span data-ttu-id="474be-195">患者 =\<患者 id></span><span class="sxs-lookup"><span data-stu-id="474be-195">patient=\<patient id></span></span>
2. <span data-ttu-id="474be-196">_count =\<最大 results></span><span class="sxs-lookup"><span data-stu-id="474be-196">_count=\<max results></span></span>

<span data-ttu-id="474be-197">请参阅下面的示例，此呼叫的：</span><span class="sxs-lookup"><span data-stu-id="474be-197">See the following example of this call:</span></span>

* * *

    <span data-ttu-id="474be-198">请求： 获取 <fhir server>/条件？ 患者 = <patient id>&_count = 10</span><span class="sxs-lookup"><span data-stu-id="474be-198">Request: GET <fhir-server>/Condition?patient=<patient-id>&_count=10</span></span>
    
    <span data-ttu-id="474be-199">响应: {"resourceType":"捆绑"、"id":"<bundle id>"、"类型":"searchset"，"total": 1，entry: [{"资源": {"resourceType":"条件"、"id":"<resource id>"、"代码": {"编码": [{              "系统":"http://snomed.info/sct"，"代码":"386033004"，"显示":"Neuropathy （神经损害）"}]}，"dateRecorded":"2018年-09-17"，"severity": {"编码": [{"system":"http://snomed.info/sct"，"代码":"24484000"，"显示":"严重"}]}}，}]}</span><span class="sxs-lookup"><span data-stu-id="474be-199">Response: {   "resourceType": "Bundle",   "id": "<bundle-id>",   "type": "searchset",   "total": 1,   "entry": [     {       "resource": {         "resourceType": "Condition",         "id": "<resource-id>",         "code": {           "coding": [             {               "system": "http://snomed.info/sct",               "code": "386033004",               "display": "Neuropathy (nerve damage)"             }           ]         },         "dateRecorded": "2018-09-17",         "severity": {           "coding": [             {               "system": "http://snomed.info/sct",               "code": "24484000",               "display": "Severe"             }           ]         }       },     }   ] }</span></span>

* * *

<span data-ttu-id="474be-200">请参阅[https://www.hl7.org/fhir/DSTU2/Condition.html](https://www.hl7.org/fhir/DSTU2/Condition.html)有关此字段的其他详细信息设置。</span><span class="sxs-lookup"><span data-stu-id="474be-200">See [https://www.hl7.org/fhir/DSTU2/Condition.html](https://www.hl7.org/fhir/DSTU2/Condition.html) for other details on this field set.</span></span>

## <a name="encounter"></a><span data-ttu-id="474be-201">遇到</span><span class="sxs-lookup"><span data-stu-id="474be-201">Encounter</span></span>

<span data-ttu-id="474be-202">这是最小的必填的字段，它们是美国核心遇到的配置文件"必须具有"字段的子集：</span><span class="sxs-lookup"><span data-stu-id="474be-202">These are the minimum required fields, which are a subset of the US Core Encounter profile “must have” fields:</span></span>

1. <span data-ttu-id="474be-203">状态</span><span class="sxs-lookup"><span data-stu-id="474be-203">Status</span></span>
2. <span data-ttu-id="474be-204">类型 [0]。编码 [0]。显示</span><span class="sxs-lookup"><span data-stu-id="474be-204">Type[0].Coding[0].Display</span></span>

<span data-ttu-id="474be-205">此外，从美国核心遇到配置文件的以下字段"必须支持"字段</span><span class="sxs-lookup"><span data-stu-id="474be-205">In addition, the following fields from US Core Encounter profile’s “must support” fields</span></span>

1. <span data-ttu-id="474be-206">Period.Start</span><span class="sxs-lookup"><span data-stu-id="474be-206">Period.Start</span></span>
2. <span data-ttu-id="474be-207">位置 [0]。Location.Display</span><span class="sxs-lookup"><span data-stu-id="474be-207">Location[0].Location.Display</span></span>

<span data-ttu-id="474be-208">资源搜索使用 GET 方法并使用以下参数：</span><span class="sxs-lookup"><span data-stu-id="474be-208">A resource search uses the GET method and the following parameters:</span></span>

1. <span data-ttu-id="474be-209">患者 =\<患者 id></span><span class="sxs-lookup"><span data-stu-id="474be-209">patient=\<patient id></span></span>
2. <span data-ttu-id="474be-210">_sort:desc =\<ex 字段。</span><span class="sxs-lookup"><span data-stu-id="474be-210">_sort:desc=\<field ex.</span></span> <span data-ttu-id="474be-211">date></span><span class="sxs-lookup"><span data-stu-id="474be-211">date></span></span>
3. <span data-ttu-id="474be-212">_count =\<最大 results></span><span class="sxs-lookup"><span data-stu-id="474be-212">_count=\<max results></span></span>

<span data-ttu-id="474be-213">目标是能够检索患者的最后一个已知的位置。</span><span class="sxs-lookup"><span data-stu-id="474be-213">The goal is to be able to retrieve the patient’s last known location.</span></span> <span data-ttu-id="474be-214">每个遇到引用的位置资源。</span><span class="sxs-lookup"><span data-stu-id="474be-214">Each encounter references a location resource.</span></span> <span data-ttu-id="474be-215">引用还应包括的位置显示字段。</span><span class="sxs-lookup"><span data-stu-id="474be-215">The reference shall also include the location’s display field.</span></span> <span data-ttu-id="474be-216">请参阅下面的示例的此呼叫。</span><span class="sxs-lookup"><span data-stu-id="474be-216">See the following example of this call.</span></span>
* * *

    <span data-ttu-id="474be-217">请求： 获取 <fhir-server>/遇到？ 患者 = <patient-id>&_sort:desc = date&_count = 1</span><span class="sxs-lookup"><span data-stu-id="474be-217">Request: GET <fhir-server>/Encounter?patient=<patient-id>&_sort:desc=date&_count=1</span></span>
    
    <span data-ttu-id="474be-218">响应: {"resourceType":"绑定"，"类型":"searchset"，"total": 1，entry: [{"资源": {"resourceType":"遇到"、"id":"<resource id>"、"标识符": [{"使用":"正式"，"value":"<id>"}]，"状态":"访问"，"键入": [{"编码": [{"显示":"约会"}]，}]、"患者": {"参考":"<patient/患者-id>"}，"时间段": {"启动":"09/17/2018年 1:00:00"}，"位置": [{             "位置": {"显示":"培训班-企业"}，}]}}]}</span><span class="sxs-lookup"><span data-stu-id="474be-218">Response: {   "resourceType": "Bundle",   "type": "searchset",   "total": 1,   "entry": [     {       "resource": {         "resourceType": "Encounter",         "id": "<resource-id>",         "identifier": [{ "use": "official", "value": "<id>" }],         "status": "arrived",         "type": [           {             "coding": [{ "display": "Appointment" }],           }         ],         "patient": { "reference": "Patient/<patient-id>" },         "period": { "start": "09/17/2018 1:00:00 PM" },         "location": [           {             "location": { "display": "Clinic - ENT" },           }         ]       }     }   ] }</span></span>

* * *

<span data-ttu-id="474be-219">请参阅[https://www.hl7.org/fhir/DSTU2/Encounter.htm](https://www.hl7.org/fhir/DSTU2/Encounter.htm)有关此字段的其他详细信息设置。</span><span class="sxs-lookup"><span data-stu-id="474be-219">See [https://www.hl7.org/fhir/DSTU2/Encounter.htm](https://www.hl7.org/fhir/DSTU2/Encounter.htm) for other details on this field set.</span></span>

## <a name="allergyintolerance"></a><span data-ttu-id="474be-220">AllergyIntolerance</span><span class="sxs-lookup"><span data-stu-id="474be-220">AllergyIntolerance</span></span>

<span data-ttu-id="474be-221">这是最小必填的字段，是 Argonaut AllergyIntolerance 配置文件的子集：</span><span class="sxs-lookup"><span data-stu-id="474be-221">These are the minimum required fields, which are a subset of the Argonaut AllergyIntolerance profile:</span></span>

1. <span data-ttu-id="474be-222">Code.Text</span><span class="sxs-lookup"><span data-stu-id="474be-222">Code.Text</span></span>
2. <span data-ttu-id="474be-223">Code.Coding[0]。显示</span><span class="sxs-lookup"><span data-stu-id="474be-223">Code.Coding[0].Display</span></span>
3. <span data-ttu-id="474be-224">状态</span><span class="sxs-lookup"><span data-stu-id="474be-224">Status</span></span>

<span data-ttu-id="474be-225">除了 Argonaut 字段中，对于出色的用户体验患者应用程序还读取以下字段：</span><span class="sxs-lookup"><span data-stu-id="474be-225">In addition to the Argonaut fields, for a great user experience the Patients app also reads the following fields:</span></span>

1. <span data-ttu-id="474be-226">RecordedDate</span><span class="sxs-lookup"><span data-stu-id="474be-226">RecordedDate</span></span>
2. <span data-ttu-id="474be-227">Note.Text</span><span class="sxs-lookup"><span data-stu-id="474be-227">Note.Text</span></span>
3. <span data-ttu-id="474be-228">[.] 的反应。Substance.Text</span><span class="sxs-lookup"><span data-stu-id="474be-228">Reaction[..].Substance.Text</span></span>
4. <span data-ttu-id="474be-229">[.] 的反应。体现 [.]。文本</span><span class="sxs-lookup"><span data-stu-id="474be-229">Reaction[..].Manifestation[..].Text</span></span>
5. <span data-ttu-id="474be-230">Text.Div</span><span class="sxs-lookup"><span data-stu-id="474be-230">Text.Div</span></span>

<span data-ttu-id="474be-231">资源搜索使用 GET 方法并使用以下参数：</span><span class="sxs-lookup"><span data-stu-id="474be-231">A resource search uses the GET method and the following parameters:</span></span>

1. <span data-ttu-id="474be-232">患者 =\<患者 id></span><span class="sxs-lookup"><span data-stu-id="474be-232">Patient =  \<patient id></span></span>

<span data-ttu-id="474be-233">请参阅下面的示例，此呼叫的：</span><span class="sxs-lookup"><span data-stu-id="474be-233">See the following example of this call:</span></span>

* * *

    <span data-ttu-id="474be-234">请求： 获取 <fhir-server>/AllergyIntolerance？ 患者 = <patient id></span><span class="sxs-lookup"><span data-stu-id="474be-234">Request: GET <fhir-server>/AllergyIntolerance?patient=<patient-id></span></span>
    
    <span data-ttu-id="474be-235">响应: {"resourceType":"捆绑"、"id":"<bundle id>"、"类型":"searchset"，"total": 1，entry: [{"资源": {"resourceType":"AllergyIntolerance"，"id":"<resource id>"、"recordedDate":"2018年-09-17T07:00:00.000Z"，"材料": {"text":"Cashew 具体"}，"状态":"确认"，"反应": [{"材料": {"text":"cashew 螺母 allergenic 提取注射产品"}，"manifestati在": [{"text":"Anaphylactic 反应"}]}]}}]}</span><span class="sxs-lookup"><span data-stu-id="474be-235">Response: {   "resourceType": "Bundle",   "id": "<bundle-id>",   "type": "searchset",   "total": 1,   "entry": [     {       "resource": {         "resourceType": "AllergyIntolerance",         "id": "<resource-id>",         "recordedDate": "2018-09-17T07:00:00.000Z",         "substance": {           "text": "Cashew nuts"         },         "status": "confirmed",         "reaction": [           {             "substance": {               "text": "cashew nut allergenic extract Injectable Product"             },             "manifestation": [               {                 "text": "Anaphylactic reaction"               }             ]           }         ]       }     }   ] }</span></span>

* * *

<span data-ttu-id="474be-236">请参阅[https://www.hl7.org/fhir/DSTU2/AllergyIntolerance.html](https://www.hl7.org/fhir/DSTU2/AllergyIntolerance.html)有关此字段的其他详细信息设置。</span><span class="sxs-lookup"><span data-stu-id="474be-236">See [https://www.hl7.org/fhir/DSTU2/AllergyIntolerance.html](https://www.hl7.org/fhir/DSTU2/AllergyIntolerance.html) for other details on this field set.</span></span>

## <a name="medication-order"></a><span data-ttu-id="474be-237">用药顺序</span><span class="sxs-lookup"><span data-stu-id="474be-237">Medication Order</span></span>

<span data-ttu-id="474be-238">这是最小必填的字段，是 Argonaut MedicationOrder 配置文件的子集：</span><span class="sxs-lookup"><span data-stu-id="474be-238">These are the minimum required fields, which are a subset of the Argonaut MedicationOrder profile:</span></span>

1. <span data-ttu-id="474be-239">DateWritten</span><span class="sxs-lookup"><span data-stu-id="474be-239">DateWritten</span></span>
2. <span data-ttu-id="474be-240">Prescriber.Display</span><span class="sxs-lookup"><span data-stu-id="474be-240">Prescriber.Display</span></span>
3. <span data-ttu-id="474be-241">Medication.Display (如果引用)</span><span class="sxs-lookup"><span data-stu-id="474be-241">Medication.Display (if reference)</span></span>
4. <span data-ttu-id="474be-242">Medication.Text (如果概念)</span><span class="sxs-lookup"><span data-stu-id="474be-242">Medication.Text (if concept)</span></span>

<span data-ttu-id="474be-243">除了 Argonaut 字段中，为出色的用户体验患者应用程序还可以阅读以下字段：</span><span class="sxs-lookup"><span data-stu-id="474be-243">In addition to the Argonaut fields, for a great user experience the Patients app can also read the following fields:</span></span>

1. <span data-ttu-id="474be-244">DateEnded</span><span class="sxs-lookup"><span data-stu-id="474be-244">DateEnded</span></span>
2. <span data-ttu-id="474be-245">DosageInstruction.Text</span><span class="sxs-lookup"><span data-stu-id="474be-245">DosageInstruction.Text</span></span>
3. <span data-ttu-id="474be-246">Text.Div</span><span class="sxs-lookup"><span data-stu-id="474be-246">Text.Div</span></span>

<span data-ttu-id="474be-247">资源搜索使用 GET 方法并使用以下参数：</span><span class="sxs-lookup"><span data-stu-id="474be-247">A resource search uses the GET method and the following parameters:</span></span>

1. <span data-ttu-id="474be-248">患者 =\<患者 id></span><span class="sxs-lookup"><span data-stu-id="474be-248">patient=\<patient id></span></span>
2. <span data-ttu-id="474be-249">_count =\<最大 results></span><span class="sxs-lookup"><span data-stu-id="474be-249">_count=\<max results></span></span>

<span data-ttu-id="474be-250">请参阅下面的示例，此呼叫的：</span><span class="sxs-lookup"><span data-stu-id="474be-250">See the following example of this call:</span></span>

* * *

    <span data-ttu-id="474be-251">请求： 获取 <fhir-server>/MedicationOrder？ 患者 = <patient id>&_count = 10</span><span class="sxs-lookup"><span data-stu-id="474be-251">Request: GET <fhir-server>/MedicationOrder?patient=<patient-id>&_count=10</span></span>
    
    <span data-ttu-id="474be-252">响应: {"resourceType":"捆绑"、"id":"<bundle id>"、"类型":"searchset"，"total": 1，entry: [{"资源": {"resourceType":"MedicationOrder"，"id":"<resource id>"、"dateWritten":"2018年-09-17"，"媒体cationCodeableConcept": {"text":"Lisinopril 20 MG 口头 Tablet"}，"prescriber": {"显示":"Jane Doe"}，"dosageInstruction": [{"text":"1 每天"}]}}]}</span><span class="sxs-lookup"><span data-stu-id="474be-252">Response: {   "resourceType": "Bundle",   "id": "<bundle-id>",   "type": "searchset",   "total": 1,   "entry": [     {       "resource": {         "resourceType": "MedicationOrder",         "id": "<resource-id>",         "dateWritten": "2018-09-17",         "medicationCodeableConcept": {           "text": "Lisinopril 20 MG Oral Tablet"         },         "prescriber": {           "display": "Jane Doe"         },         "dosageInstruction": [           {             "text": "1 daily"           }         ]       }     }   ] }</span></span>

* * *  

<span data-ttu-id="474be-253">请参阅[https://www.hl7.org/fhir/DSTU2/MedicationOrder.html](https://www.hl7.org/fhir/DSTU2/MedicationOrder.html)有关此字段的其他详细信息设置。</span><span class="sxs-lookup"><span data-stu-id="474be-253">See [https://www.hl7.org/fhir/DSTU2/MedicationOrder.html](https://www.hl7.org/fhir/DSTU2/MedicationOrder.html) for other details on this field set.</span></span>

## <a name="coverage"></a><span data-ttu-id="474be-254">覆盖范围</span><span class="sxs-lookup"><span data-stu-id="474be-254">Coverage</span></span>

<span data-ttu-id="474be-255">这是最小的必填的字段，不受美国核心或 Argonaut 配置文件：</span><span class="sxs-lookup"><span data-stu-id="474be-255">These are the minimum required fields, not covered by either US Core or Argonaut profiles:</span></span>

1. <span data-ttu-id="474be-256">付款方</span><span class="sxs-lookup"><span data-stu-id="474be-256">Payor</span></span>

<span data-ttu-id="474be-257">资源搜索使用 GET 方法并使用以下参数：</span><span class="sxs-lookup"><span data-stu-id="474be-257">A resource search uses the GET method and the following parameters:</span></span>

1. <span data-ttu-id="474be-258">患者 =\<患者 id></span><span class="sxs-lookup"><span data-stu-id="474be-258">patient=\<patient id></span></span>

<span data-ttu-id="474be-259">请参阅下面的示例，此呼叫的：</span><span class="sxs-lookup"><span data-stu-id="474be-259">See the following example of this call:</span></span>

* * *

    <span data-ttu-id="474be-260">请求： 获取覆盖范围 <fhir-server>？ 患者 = <patient id></span><span class="sxs-lookup"><span data-stu-id="474be-260">Request: GET <fhir-server>/Coverage?patient=<patient-id></span></span>
    
    <span data-ttu-id="474be-261">响应: {"resourceType":"绑定"，"类型":"searchset"，"total": 1，entry: [{"资源": {"resourceType":"覆盖"，"id":"<resource id>"、"计划":"无主保险"、"订阅者": {"参考":"患者 /<patient id>"}}}]}</span><span class="sxs-lookup"><span data-stu-id="474be-261">Response: {   "resourceType": "Bundle",   "type": "searchset",   "total": 1,   "entry": [     {       "resource": {         "resourceType": "Coverage",         "id": "<resource-id>",         "plan": "No Primary Insurance",         "subscriber": { "reference": "Patient/<patient-id>" }       }     }   ] }</span></span>

* * *

<span data-ttu-id="474be-262">请参阅[https://www.hl7.org/fhir/DSTU2/Coverage.html](https://www.hl7.org/fhir/DSTU2/Coverage.html)有关此字段的其他详细信息设置。</span><span class="sxs-lookup"><span data-stu-id="474be-262">See [https://www.hl7.org/fhir/DSTU2/Coverage.html](https://www.hl7.org/fhir/DSTU2/Coverage.html) for other details on this field set.</span></span>

## <a name="location"></a><span data-ttu-id="474be-263">位置</span><span class="sxs-lookup"><span data-stu-id="474be-263">Location</span></span>

<span data-ttu-id="474be-264">此资源仅用作[遇到](#encounter)资源的引用。</span><span class="sxs-lookup"><span data-stu-id="474be-264">This resource is only being used as a reference on the [Encounter](#encounter) resource.</span></span>

<span data-ttu-id="474be-265">请参阅[https://www.hl7.org/fhir/DSTU2/Location.html](https://www.hl7.org/fhir/DSTU2/Location.html)有关此字段的其他详细信息设置。</span><span class="sxs-lookup"><span data-stu-id="474be-265">See [https://www.hl7.org/fhir/DSTU2/Location.html](https://www.hl7.org/fhir/DSTU2/Location.html) for other details on this field set.</span></span>
