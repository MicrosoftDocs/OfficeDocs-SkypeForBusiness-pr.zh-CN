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
ms.openlocfilehash: f09f43af431b3f0cc6d9f984171206f2549a550a
ms.sourcegitcommit: cddaacf1e8dbcdfd3f94deee7057c89cee0e5699
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/03/2020
ms.locfileid: "43136952"
---
# <a name="dstu2-interface-specification"></a><span data-ttu-id="1e420-103">DSTU2 接口规范</span><span class="sxs-lookup"><span data-stu-id="1e420-103">DSTU2 interface specification</span></span>

[!INCLUDE [preview-feature](../../includes/preview-feature.md)]

<span data-ttu-id="1e420-104">设置或重新配置 FHIR 服务器以处理 Microsoft 团队患者应用需要了解应用需要访问的数据。</span><span class="sxs-lookup"><span data-stu-id="1e420-104">Setting up or reconfiguring an FHIR server to work with the Microsoft Teams Patients app requires understanding what data the app needs to access.</span></span> <span data-ttu-id="1e420-105">FHIR 服务器必须使用以下资源的捆绑包支持发布请求：</span><span class="sxs-lookup"><span data-stu-id="1e420-105">The FHIR server must support POST requests using bundles for the following resources:</span></span>

- [<span data-ttu-id="1e420-106">档案</span><span class="sxs-lookup"><span data-stu-id="1e420-106">Patient</span></span>](#patient)
- [<span data-ttu-id="1e420-107">知识产权</span><span class="sxs-lookup"><span data-stu-id="1e420-107">Observation</span></span>](#observation)
- [<span data-ttu-id="1e420-108">条件</span><span class="sxs-lookup"><span data-stu-id="1e420-108">Condition</span></span>](#condition)
- [<span data-ttu-id="1e420-109">产生</span><span class="sxs-lookup"><span data-stu-id="1e420-109">Encounter</span></span>](#encounter)
- [<span data-ttu-id="1e420-110">过敏症 intolerance</span><span class="sxs-lookup"><span data-stu-id="1e420-110">Allergy intolerance</span></span>](#allergyintolerance)
- [<span data-ttu-id="1e420-111">内</span><span class="sxs-lookup"><span data-stu-id="1e420-111">Coverage</span></span>](#coverage)
- [<span data-ttu-id="1e420-112">药物订货</span><span class="sxs-lookup"><span data-stu-id="1e420-112">Medication Order</span></span>](#medication-order)
- [<span data-ttu-id="1e420-113">位置</span><span class="sxs-lookup"><span data-stu-id="1e420-113">Location</span></span>](#location)

> [!NOTE]
> <span data-ttu-id="1e420-114">患者资源是唯一必需的资源（根本不会加载应用程序）。</span><span class="sxs-lookup"><span data-stu-id="1e420-114">The Patient resource is the only mandatory resource (without which the app will not load at all.</span></span> <span data-ttu-id="1e420-115">但是，建议合作伙伴针对 Microsoft 团队患者应用的最佳最终用户体验，针对以下提供的针对以上提及的所有资源提供支持。</span><span class="sxs-lookup"><span data-stu-id="1e420-115">However, it is recommended that the Partner implement support for all the above mentioned resources per specifications provided below for the best end-user experience with the Microsoft Teams Patients App.</span></span>

<span data-ttu-id="1e420-116">来自 Microsoft 团队患者应用的来自多个资源的查询向 FHIR 服务器的 URL 发布一个捆绑（批处理）请求。</span><span class="sxs-lookup"><span data-stu-id="1e420-116">Queries from the Microsoft Teams Patients app for more than one resource post a bundle (BATCH) of requests to the FHIR server's URL.</span></span> <span data-ttu-id="1e420-117">服务器处理每个请求，并返回每个请求所匹配的资源的捆绑包。</span><span class="sxs-lookup"><span data-stu-id="1e420-117">The server processes each request and returns a bundle of the resources matched by each request.</span></span> <span data-ttu-id="1e420-118">有关详细信息和示例，请[https://www.hl7.org/fhir/DSTU2/http.html#transaction](https://www.hl7.org/fhir/DSTU2/http.html#transaction)参阅。</span><span class="sxs-lookup"><span data-stu-id="1e420-118">For more information and examples, see [https://www.hl7.org/fhir/DSTU2/http.html#transaction](https://www.hl7.org/fhir/DSTU2/http.html#transaction).</span></span>

<span data-ttu-id="1e420-119">所有以下 FHIR 资源应可通过直接资源参考访问。</span><span class="sxs-lookup"><span data-stu-id="1e420-119">All the following FHIR resources should be accessible by direct resource reference.</span></span>

## <a name="conformance-minimum-required-field-set"></a><span data-ttu-id="1e420-120">一致性最低要求字段集</span><span class="sxs-lookup"><span data-stu-id="1e420-120">Conformance minimum required field set</span></span>

 <span data-ttu-id="1e420-121">FHIR 服务器必须实现一致性声明，才能为我们提供其功能的实际摘要。</span><span class="sxs-lookup"><span data-stu-id="1e420-121">The FHIR Server must implement the conformance statement for us to have a factual summary of its capabilities.</span></span> <span data-ttu-id="1e420-122">我们期望 DSTU2 FHIR 服务器中的以下参数：</span><span class="sxs-lookup"><span data-stu-id="1e420-122">We expect the below parameters in a DSTU2 FHIR Server:</span></span>

1. <span data-ttu-id="1e420-123">余下</span><span class="sxs-lookup"><span data-stu-id="1e420-123">REST</span></span>
   1. <span data-ttu-id="1e420-124">众</span><span class="sxs-lookup"><span data-stu-id="1e420-124">Mode</span></span>
   2. <span data-ttu-id="1e420-125">相交</span><span class="sxs-lookup"><span data-stu-id="1e420-125">Interaction</span></span>
   3. <span data-ttu-id="1e420-126">资源：类型</span><span class="sxs-lookup"><span data-stu-id="1e420-126">Resource: Type</span></span>
   4. <span data-ttu-id="1e420-127">安全性： [OAuth uri 的扩展](https://hl7.org/fhir/extension-oauth-uris.html)</span><span class="sxs-lookup"><span data-stu-id="1e420-127">Security: [Extension for OAuth URIs](https://hl7.org/fhir/extension-oauth-uris.html)</span></span>
2. <span data-ttu-id="1e420-128">FhirVersion （我们的代码需要此内容才能了解我们支持多个版本时应透视到的版本。）</span><span class="sxs-lookup"><span data-stu-id="1e420-128">FhirVersion (Our code requires this to understand which version we should pivot to as we support multiple versions.)</span></span>

<span data-ttu-id="1e420-129">有关[https://www.hl7.org/fhir/dstu2/conformance.html](https://www.hl7.org/fhir/dstu2/conformance.html)此字段集的其他详细信息，请参阅。</span><span class="sxs-lookup"><span data-stu-id="1e420-129">See [https://www.hl7.org/fhir/dstu2/conformance.html](https://www.hl7.org/fhir/dstu2/conformance.html) for other details on this field set.</span></span>

## <a name="patient"></a><span data-ttu-id="1e420-130">档案</span><span class="sxs-lookup"><span data-stu-id="1e420-130">Patient</span></span>

<span data-ttu-id="1e420-131">以下是 " [Argonaut" 患者档案](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-patient.html)字段子集的最少必填字段：</span><span class="sxs-lookup"><span data-stu-id="1e420-131">These are the minimum required fields, which are a subset of the [Argonaut patient profile](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-patient.html) fields:</span></span>

1. <span data-ttu-id="1e420-132">名称。家庭</span><span class="sxs-lookup"><span data-stu-id="1e420-132">Name.Family</span></span>
2. <span data-ttu-id="1e420-133">名称。给定</span><span class="sxs-lookup"><span data-stu-id="1e420-133">Name.Given</span></span>
3. <span data-ttu-id="1e420-134">性别</span><span class="sxs-lookup"><span data-stu-id="1e420-134">Gender</span></span>
4. <span data-ttu-id="1e420-135">BirthDate</span><span class="sxs-lookup"><span data-stu-id="1e420-135">BirthDate</span></span>
5. <span data-ttu-id="1e420-136">MRN （标识符）</span><span class="sxs-lookup"><span data-stu-id="1e420-136">MRN (Identifier)</span></span>

<span data-ttu-id="1e420-137">除了 Argonaut 字段，为患者应用提供出色的用户体验还会读取以下字段：</span><span class="sxs-lookup"><span data-stu-id="1e420-137">In addition to the Argonaut fields, for a great user experience the Patients app also reads the following fields:</span></span>

1. <span data-ttu-id="1e420-138">名称。使用</span><span class="sxs-lookup"><span data-stu-id="1e420-138">Name.Use</span></span>
2. <span data-ttu-id="1e420-139">名称。前缀</span><span class="sxs-lookup"><span data-stu-id="1e420-139">Name.Prefix</span></span>
3. <span data-ttu-id="1e420-140">CareProvider （此对患者资源的参考应包括以下示例中所示的显示字段。）</span><span class="sxs-lookup"><span data-stu-id="1e420-140">CareProvider (This reference on the Patient resource should include the display fields shown in the following example.)</span></span>

* * *

    <span data-ttu-id="1e420-141">请求：获取 <fhir-服务器>/Patient/<患者 id></span><span class="sxs-lookup"><span data-stu-id="1e420-141">Request: GET <fhir-server>/Patient/<patient-id></span></span>
    
    <span data-ttu-id="1e420-142">回复： {"resourceType"： "患者"，"id"： "<患者 id>"，。</span><span class="sxs-lookup"><span data-stu-id="1e420-142">Response: { "resourceType": "Patient", "id": "<patient-id>", .</span></span>
      <span data-ttu-id="1e420-143">.</span><span class="sxs-lookup"><span data-stu-id="1e420-143">.</span></span>
      <span data-ttu-id="1e420-144">.</span><span class="sxs-lookup"><span data-stu-id="1e420-144">.</span></span>
      <span data-ttu-id="1e420-145">"名称"： [{"使用"： "官方"，"prefix"： ["Mr"]，"family"： ["Chau"]，"Hugh"： [""]}]，"标识符"： [{"使用"： "官方"，"类型"： {"编码"： [{"systemhttps://hl7.org/fhir/v2/0203"： "？"，"1234567"}]，"性别"： "男"，"出生日期"： "1957-06-05"，"careProvider"： [{"显示"： "Jane Doe"}]，}</span><span class="sxs-lookup"><span data-stu-id="1e420-145">"name": [ { "use": "official", "prefix": [ "Mr" ], "family": [ "Chau" ], "given": [ "Hugh" ] } ], "identifier": [ { "use": "official", "type": { "coding": [ { "system": "https://hl7.org/fhir/v2/0203", "code": "MR" } ] }, "value": "1234567" } ], "gender": "male", "birthDate": "1957-06-05", "careProvider": [{ "display": "Jane Doe" }], }</span></span>

* * *

<span data-ttu-id="1e420-146">资源搜索在/Patient/_search 使用 POST 方法，并使用以下参数：</span><span class="sxs-lookup"><span data-stu-id="1e420-146">A resource search uses the POST method at /Patient/_search and the following parameters:</span></span>

1. <span data-ttu-id="1e420-147">标识号</span><span class="sxs-lookup"><span data-stu-id="1e420-147">id</span></span>
2. <span data-ttu-id="1e420-148">系列：包含 = （搜索其系列名称包含该值的所有患者。）</span><span class="sxs-lookup"><span data-stu-id="1e420-148">family:contains=(searches for all patients whose family name contains the value.)</span></span>
3. <span data-ttu-id="1e420-149">给定 =\<substring></span><span class="sxs-lookup"><span data-stu-id="1e420-149">given=\<substring></span></span>
4. <span data-ttu-id="1e420-150">name =\<substring></span><span class="sxs-lookup"><span data-stu-id="1e420-150">name=\<substring></span></span>
5. <span data-ttu-id="1e420-151">出生日期 = （完全匹配）</span><span class="sxs-lookup"><span data-stu-id="1e420-151">birthdate=(exact match)</span></span>
6. <span data-ttu-id="1e420-152">\_计数（应返回的最大结果数）</span><span class="sxs-lookup"><span data-stu-id="1e420-152">\_count (maximum number of results that should be returned)</span></span> <br> <span data-ttu-id="1e420-153">该响应应包含作为搜索结果返回的记录的总数，PatientsApp 将使用该\_计数来限制返回的记录数。</span><span class="sxs-lookup"><span data-stu-id="1e420-153">The response should contain the total count of records returned as a result of the search, and \_count will be used by the PatientsApp to limit the number of records returned.</span></span>
7. <span data-ttu-id="1e420-154">标识符 =\<mrn></span><span class="sxs-lookup"><span data-stu-id="1e420-154">identifier=\<mrn></span></span>

<span data-ttu-id="1e420-155">目标是能够搜索和筛选患者，如下所示：</span><span class="sxs-lookup"><span data-stu-id="1e420-155">The goal is to be able to search and filter for a patient by the following:</span></span>

- <span data-ttu-id="1e420-156">ID：这是 FHIR 中的每个资源具有的资源 ID。</span><span class="sxs-lookup"><span data-stu-id="1e420-156">ID: This is the resource ID that every resource in FHIR has.</span></span>
- <span data-ttu-id="1e420-157">MRN：这是临床人员将知道的患者的实际标识符。</span><span class="sxs-lookup"><span data-stu-id="1e420-157">MRN: This is the actual identifier for the patient that clinical staff would know.</span></span> <span data-ttu-id="1e420-158">我们理解此 MRN 基于 FHIR 中的标识符资源内的标识符类型</span><span class="sxs-lookup"><span data-stu-id="1e420-158">We understand this MRN is based on the type of identifier inside the identifier resource in FHIR</span></span>
- <span data-ttu-id="1e420-159">名称</span><span class="sxs-lookup"><span data-stu-id="1e420-159">Name</span></span>
- <span data-ttu-id="1e420-160">Birthdate</span><span class="sxs-lookup"><span data-stu-id="1e420-160">Birthdate</span></span>

<span data-ttu-id="1e420-161">请参阅下面的此通话示例。</span><span class="sxs-lookup"><span data-stu-id="1e420-161">See the following example  of this call.</span></span>

* * *

    <span data-ttu-id="1e420-162">请求： POST <fhir-server>/Patient/_search 请求正文：给定 = hugh&家族 = chau</span><span class="sxs-lookup"><span data-stu-id="1e420-162">Request: POST <fhir-server>/Patient/_search Request Body: given=hugh&family=chau</span></span>
    
    <span data-ttu-id="1e420-163">响应： {"resourceType"： "捆绑包"，"id"： "<捆绑包-id>"，。</span><span class="sxs-lookup"><span data-stu-id="1e420-163">Response: { "resourceType": "Bundle", "id": "<bundle-id>", .</span></span>
      <span data-ttu-id="1e420-164">.</span><span class="sxs-lookup"><span data-stu-id="1e420-164">.</span></span>
      <span data-ttu-id="1e420-165">.</span><span class="sxs-lookup"><span data-stu-id="1e420-165">.</span></span>
      <span data-ttu-id="1e420-166">"entry"： [{"资源"： {"resourceType"： "患者"，"id"： "<患者 id>"，"名称"： [{"文本"： "Hugh Chau"，"family"： ["Hugh"]，""： [""]}]，"性别"： "男"，"出生日期"： "1957-06-05</span><span class="sxs-lookup"><span data-stu-id="1e420-166">"entry": [ { "resource": { "resourceType": "Patient", "id": "<patient-id>", "name": [ { "text": "Hugh Chau", "family": [ "Chau" ], "given": [ "Hugh" ] } ], "gender": "male", "birthDate": "1957-06-05" }, "search": { "mode": "match" } } ] }</span></span>

* * *

<span data-ttu-id="1e420-167">有关[https://www.hl7.org/fhir/DSTU2/Patient.html](https://www.hl7.org/fhir/DSTU2/Patient.html)此字段集的其他详细信息，请参阅。</span><span class="sxs-lookup"><span data-stu-id="1e420-167">See [https://www.hl7.org/fhir/DSTU2/Patient.html](https://www.hl7.org/fhir/DSTU2/Patient.html) for other details on this field set.</span></span>

## <a name="observation"></a><span data-ttu-id="1e420-168">知识产权</span><span class="sxs-lookup"><span data-stu-id="1e420-168">Observation</span></span>

<span data-ttu-id="1e420-169">以下是最少的必填字段，这些字段是 Argonaut 的重要符号配置文件的子集：</span><span class="sxs-lookup"><span data-stu-id="1e420-169">These are the minimum required fields, which are a subset of the Argonaut vital signs profile:</span></span>

 1. <span data-ttu-id="1e420-170">有效（日期时间或周期）</span><span class="sxs-lookup"><span data-stu-id="1e420-170">Effective (date time or period)</span></span>
 2. <span data-ttu-id="1e420-171">编码代码</span><span class="sxs-lookup"><span data-stu-id="1e420-171">Code.Coding.Code</span></span>
 3. <span data-ttu-id="1e420-172">ValueQuantity 值</span><span class="sxs-lookup"><span data-stu-id="1e420-172">ValueQuantity.Value</span></span>

<span data-ttu-id="1e420-173">除了 Argonaut 字段，为患者应用提供出色的用户体验还会读取以下字段：</span><span class="sxs-lookup"><span data-stu-id="1e420-173">In addition to the Argonaut fields, for a great user experience the Patients app also reads the following fields:</span></span>

 1. <span data-ttu-id="1e420-174">代码编码。显示</span><span class="sxs-lookup"><span data-stu-id="1e420-174">Code.Coding.Display</span></span>
 2. <span data-ttu-id="1e420-175">ValueQuantity 单位</span><span class="sxs-lookup"><span data-stu-id="1e420-175">ValueQuantity.Unit</span></span>

<span data-ttu-id="1e420-176">如果使用组件观测值，则相同的逻辑适用于每个组件观察。</span><span class="sxs-lookup"><span data-stu-id="1e420-176">If using component observations, the same logic applies for each component observation.</span></span>

<span data-ttu-id="1e420-177">资源搜索使用 GET 方法和以下参数：</span><span class="sxs-lookup"><span data-stu-id="1e420-177">A resource search uses the GET method and the following parameters:</span></span>

1. <span data-ttu-id="1e420-178">患者 =\<患者 id\></span><span class="sxs-lookup"><span data-stu-id="1e420-178">patient=\<patient id\></span></span>
2. <span data-ttu-id="1e420-179">排序： desc =\<field ex</span><span class="sxs-lookup"><span data-stu-id="1e420-179">sort:desc=\<field ex.</span></span> <span data-ttu-id="1e420-180">状态\></span><span class="sxs-lookup"><span data-stu-id="1e420-180">date\></span></span>

<span data-ttu-id="1e420-181">目标是能够检索患者的最新重要标志 [DSTU saz] （"VitalSigns"）。</span><span class="sxs-lookup"><span data-stu-id="1e420-181">The goal is to be able to retrieve the latest vital signs for a patient, [VitalSigns.DSTU.saz]  (observation?).</span></span>

* * *

    <span data-ttu-id="1e420-182">请求：获取 <fhir-服务器>/Observation？患者 =<患者 id>&_sort:d esc = 日期&category = 重要标志</span><span class="sxs-lookup"><span data-stu-id="1e420-182">Request: GET <fhir-server>/Observation?patient=<patient-id>&_sort:desc=date&category=vital-signs</span></span>
    
    <span data-ttu-id="1e420-183">响应： {"resourceType"： "捆绑包"，"id"： "<捆绑包-id>"，"键入"： "searchset"，"total"：20，"entry"： [{"resource"： "<资源 id>"，"类别"： {"编码"： [{code "：" 关键签名 "}]，}，" code "： {" 编码 "： [{" system "："http://loinc.org"，" 代码 "：" 39156-5 "，" display "：" bmi "}]，}，" effectiveDateTime "：" 2009-12-01 "，" valueQuantity "： {" 值 "：34.4，" unit "：" 公斤/m2 "，" system "："http://unitsofmeasure.org"，" 代码 "：" 公斤/m2 "}}，}。</span><span class="sxs-lookup"><span data-stu-id="1e420-183">Response: { "resourceType": "Bundle", "id": "<bundle-id>", "type": "searchset", "total": 20, "entry": [ { "resource": { "resourceType": "Observation", "id": "<resource-id>", "category": { "coding": [ { code": "vital-signs" } ], }, "code": { "coding": [ { "system": "http://loinc.org", "code": "39156-5", "display": "bmi" } ], }, "effectiveDateTime": "2009-12-01", "valueQuantity": { "value": 34.4, "unit": "kg/m2", "system": "http://unitsofmeasure.org", "code": "kg/m2" } }, }, .</span></span>
        <span data-ttu-id="1e420-184">.</span><span class="sxs-lookup"><span data-stu-id="1e420-184">.</span></span>
        <span data-ttu-id="1e420-185">.</span><span class="sxs-lookup"><span data-stu-id="1e420-185">.</span></span>
      <span data-ttu-id="1e420-186">] }</span><span class="sxs-lookup"><span data-stu-id="1e420-186">] }</span></span>

* * *

<span data-ttu-id="1e420-187">有关[https://www.hl7.org/fhir/DSTU2/Observation.html](https://www.hl7.org/fhir/DSTU2/Observation.html)此字段集的其他详细信息，请参阅。</span><span class="sxs-lookup"><span data-stu-id="1e420-187">See [https://www.hl7.org/fhir/DSTU2/Observation.html](https://www.hl7.org/fhir/DSTU2/Observation.html) for other details on this field set.</span></span>

## <a name="condition"></a><span data-ttu-id="1e420-188">条件</span><span class="sxs-lookup"><span data-stu-id="1e420-188">Condition</span></span>

<span data-ttu-id="1e420-189">下面是[Argonaut 条件配置文件](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-condition.html)子集的最少必填字段：</span><span class="sxs-lookup"><span data-stu-id="1e420-189">These are the minimum required fields, which are a subset of the [Argonaut condition profile](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-condition.html):</span></span>

1. <span data-ttu-id="1e420-190">代码。编码 [0]。画面</span><span class="sxs-lookup"><span data-stu-id="1e420-190">Code.Coding[0].Display</span></span>

<span data-ttu-id="1e420-191">除了 Argonaut 字段外，还可以为患者应用提供出色的用户体验，还可以读取以下字段：</span><span class="sxs-lookup"><span data-stu-id="1e420-191">In addition to the Argonaut fields, for a great user experience the Patients app can also read the following fields:</span></span>

1. <span data-ttu-id="1e420-192">录制日期</span><span class="sxs-lookup"><span data-stu-id="1e420-192">Date Recorded</span></span>
2. <span data-ttu-id="1e420-193">严重性</span><span class="sxs-lookup"><span data-stu-id="1e420-193">Severity</span></span>

<span data-ttu-id="1e420-194">资源搜索使用 GET 方法和以下参数：</span><span class="sxs-lookup"><span data-stu-id="1e420-194">A resource search uses the GET method and the following parameters:</span></span>

1. <span data-ttu-id="1e420-195">患者 =\<患者 id></span><span class="sxs-lookup"><span data-stu-id="1e420-195">patient=\<patient id></span></span>
2. <span data-ttu-id="1e420-196">_count =\<最大结果></span><span class="sxs-lookup"><span data-stu-id="1e420-196">_count=\<max results></span></span>

<span data-ttu-id="1e420-197">请参阅下面的此呼叫示例：</span><span class="sxs-lookup"><span data-stu-id="1e420-197">See the following example of this call:</span></span>

* * *

    <span data-ttu-id="1e420-198">请求：获取 <fhir-服务器>/Condition？患者 =<患者 id>&_count = 10</span><span class="sxs-lookup"><span data-stu-id="1e420-198">Request: GET <fhir-server>/Condition?patient=<patient-id>&_count=10</span></span>
    
    <span data-ttu-id="1e420-199">响应： {"resourceType"： "捆绑包"，"id"> <： "searchset"： ""，"total"：1，"entry"： [{"资源"： {""： "Condition"，"id"： "<资源 id>"，"代码"： {"编码"： [{"system"： "http://snomed.info/sct"，"代码"： "386033004"，"显示"： "Neuropathy （nerve 损坏）"}]}，"dateRecorded"： "2018-09-17"，"严重性"： {"编码"： [{"system"： "http://snomed.info/sct"，"代码"： "24484000"，"显示"： "严重"}]}}，}]}</span><span class="sxs-lookup"><span data-stu-id="1e420-199">Response: {   "resourceType": "Bundle",   "id": "<bundle-id>",   "type": "searchset",   "total": 1,   "entry": [     {       "resource": {         "resourceType": "Condition",         "id": "<resource-id>",         "code": {           "coding": [             {               "system": "http://snomed.info/sct",               "code": "386033004",               "display": "Neuropathy (nerve damage)"             }           ]         },         "dateRecorded": "2018-09-17",         "severity": {           "coding": [             {               "system": "http://snomed.info/sct",               "code": "24484000",               "display": "Severe"             }           ]         }       },     }   ] }</span></span>

* * *

<span data-ttu-id="1e420-200">有关[https://www.hl7.org/fhir/DSTU2/Condition.html](https://www.hl7.org/fhir/DSTU2/Condition.html)此字段集的其他详细信息，请参阅。</span><span class="sxs-lookup"><span data-stu-id="1e420-200">See [https://www.hl7.org/fhir/DSTU2/Condition.html](https://www.hl7.org/fhir/DSTU2/Condition.html) for other details on this field set.</span></span>

## <a name="encounter"></a><span data-ttu-id="1e420-201">产生</span><span class="sxs-lookup"><span data-stu-id="1e420-201">Encounter</span></span>

<span data-ttu-id="1e420-202">以下是最少必填字段，这些字段是 "美国核心" 基本配置文件 "必须具有" 字段的子集：</span><span class="sxs-lookup"><span data-stu-id="1e420-202">These are the minimum required fields, which are a subset of the US Core Encounter profile "must have" fields:</span></span>

1. <span data-ttu-id="1e420-203">状态栏</span><span class="sxs-lookup"><span data-stu-id="1e420-203">Status</span></span>
2. <span data-ttu-id="1e420-204">键入 [0]。编码 [0]。画面</span><span class="sxs-lookup"><span data-stu-id="1e420-204">Type[0].Coding[0].Display</span></span>

<span data-ttu-id="1e420-205">此外，美国核心的以下字段会遇到配置文件的 "必须支持" 字段</span><span class="sxs-lookup"><span data-stu-id="1e420-205">In addition, the following fields from US Core Encounter profile's "must support" fields</span></span>

1. <span data-ttu-id="1e420-206">句号。开始</span><span class="sxs-lookup"><span data-stu-id="1e420-206">Period.Start</span></span>
2. <span data-ttu-id="1e420-207">位置 [0]。位置。显示</span><span class="sxs-lookup"><span data-stu-id="1e420-207">Location[0].Location.Display</span></span>

<span data-ttu-id="1e420-208">资源搜索使用 GET 方法和以下参数：</span><span class="sxs-lookup"><span data-stu-id="1e420-208">A resource search uses the GET method and the following parameters:</span></span>

1. <span data-ttu-id="1e420-209">患者 =\<患者 id></span><span class="sxs-lookup"><span data-stu-id="1e420-209">patient=\<patient id></span></span>
2. <span data-ttu-id="1e420-210">_sort： desc =\<field （ex）</span><span class="sxs-lookup"><span data-stu-id="1e420-210">_sort:desc=\<field ex.</span></span> <span data-ttu-id="1e420-211">日期></span><span class="sxs-lookup"><span data-stu-id="1e420-211">date></span></span>
3. <span data-ttu-id="1e420-212">_count =\<最大结果></span><span class="sxs-lookup"><span data-stu-id="1e420-212">_count=\<max results></span></span>

<span data-ttu-id="1e420-213">目标是能够检索患者的最后一个已知位置。</span><span class="sxs-lookup"><span data-stu-id="1e420-213">The goal is to be able to retrieve the patient's last known location.</span></span> <span data-ttu-id="1e420-214">每个遇到的都引用一个位置资源。</span><span class="sxs-lookup"><span data-stu-id="1e420-214">Each encounter references a location resource.</span></span> <span data-ttu-id="1e420-215">该引用还应包含位置的显示字段。</span><span class="sxs-lookup"><span data-stu-id="1e420-215">The reference shall also include the location's display field.</span></span> <span data-ttu-id="1e420-216">请参阅下面的此通话示例。</span><span class="sxs-lookup"><span data-stu-id="1e420-216">See the following example of this call.</span></span>
* * *

    <span data-ttu-id="1e420-217">请求：获取 <fhir-服务器>/Encounter？患者 =<患者 id>&_sort:d esc = 日期&_count = 1</span><span class="sxs-lookup"><span data-stu-id="1e420-217">Request: GET <fhir-server>/Encounter?patient=<patient-id>&_sort:desc=date&_count=1</span></span>
    
    <span data-ttu-id="1e420-218">响应： {"resourceType"： "捆绑包"，"类型"： "searchset"，"total"：1，"entry"： [{"id"： "" 遇到 ""，"id"： "<资源 id>"，"标识符"： [{"使用"： "官方"，"值"： "<id>"}]，"状态"： "已到达"，"类型"： [{"编码"： [{"显示"： "约会"}]，}]，"患者"： {"参考"： "患者/<患者 id>"}，"时间段"： {"start"： "09/17/2018 1:00:00 PM"}，"位置"： [{"位置"： {"display"： [{"位置"： {"display"： "ENT"}，}]}}]}</span><span class="sxs-lookup"><span data-stu-id="1e420-218">Response: {   "resourceType": "Bundle",   "type": "searchset",   "total": 1,   "entry": [     {       "resource": {         "resourceType": "Encounter",         "id": "<resource-id>",         "identifier": [{ "use": "official", "value": "<id>" }],         "status": "arrived",         "type": [           {             "coding": [{ "display": "Appointment" }],           }         ],         "patient": { "reference": "Patient/<patient-id>" },         "period": { "start": "09/17/2018 1:00:00 PM" },         "location": [           {             "location": { "display": "Clinic - ENT" },           }         ]       }     }   ] }</span></span>

* * *

<span data-ttu-id="1e420-219">有关[https://www.hl7.org/fhir/DSTU2/Encounter.htm](https://www.hl7.org/fhir/DSTU2/Encounter.htm)此字段集的其他详细信息，请参阅。</span><span class="sxs-lookup"><span data-stu-id="1e420-219">See [https://www.hl7.org/fhir/DSTU2/Encounter.htm](https://www.hl7.org/fhir/DSTU2/Encounter.htm) for other details on this field set.</span></span>

## <a name="allergyintolerance"></a><span data-ttu-id="1e420-220">AllergyIntolerance</span><span class="sxs-lookup"><span data-stu-id="1e420-220">AllergyIntolerance</span></span>

<span data-ttu-id="1e420-221">以下是最少的必填字段，它们是 Argonaut AllergyIntolerance 配置文件的子集：</span><span class="sxs-lookup"><span data-stu-id="1e420-221">These are the minimum required fields, which are a subset of the Argonaut AllergyIntolerance profile:</span></span>

1. <span data-ttu-id="1e420-222">代码。文本</span><span class="sxs-lookup"><span data-stu-id="1e420-222">Code.Text</span></span>
2. <span data-ttu-id="1e420-223">代码。编码 [0]。画面</span><span class="sxs-lookup"><span data-stu-id="1e420-223">Code.Coding[0].Display</span></span>
3. <span data-ttu-id="1e420-224">状态栏</span><span class="sxs-lookup"><span data-stu-id="1e420-224">Status</span></span>

<span data-ttu-id="1e420-225">除了 Argonaut 字段，为患者应用提供出色的用户体验还会读取以下字段：</span><span class="sxs-lookup"><span data-stu-id="1e420-225">In addition to the Argonaut fields, for a great user experience the Patients app also reads the following fields:</span></span>

1. <span data-ttu-id="1e420-226">RecordedDate</span><span class="sxs-lookup"><span data-stu-id="1e420-226">RecordedDate</span></span>
2. <span data-ttu-id="1e420-227">备注。文本</span><span class="sxs-lookup"><span data-stu-id="1e420-227">Note.Text</span></span>
3. <span data-ttu-id="1e420-228">反应 [...]。物质。文本</span><span class="sxs-lookup"><span data-stu-id="1e420-228">Reaction[..].Substance.Text</span></span>
4. <span data-ttu-id="1e420-229">反应 [...]。表现形式 [...]。文本</span><span class="sxs-lookup"><span data-stu-id="1e420-229">Reaction[..].Manifestation[..].Text</span></span>
5. <span data-ttu-id="1e420-230">文本 Div</span><span class="sxs-lookup"><span data-stu-id="1e420-230">Text.Div</span></span>

<span data-ttu-id="1e420-231">资源搜索使用 GET 方法和以下参数：</span><span class="sxs-lookup"><span data-stu-id="1e420-231">A resource search uses the GET method and the following parameters:</span></span>

1. <span data-ttu-id="1e420-232">患者 = \<患者 id></span><span class="sxs-lookup"><span data-stu-id="1e420-232">Patient =  \<patient id></span></span>

<span data-ttu-id="1e420-233">请参阅下面的此呼叫示例：</span><span class="sxs-lookup"><span data-stu-id="1e420-233">See the following example of this call:</span></span>

* * *

    <span data-ttu-id="1e420-234">请求：获取 <fhir-服务器>/AllergyIntolerance？患者 =<患者 id></span><span class="sxs-lookup"><span data-stu-id="1e420-234">Request: GET <fhir-server>/AllergyIntolerance?patient=<patient-id></span></span>
    
    <span data-ttu-id="1e420-235">响应： {"resourceType"： "捆绑包"，"id"> <： "searchset"： ""，"total"：1，"entry"： [{"资源"： {"resourceType"： "AllergyIntolerance"，"id"： "<资源 id>"，"recordedDate"： "2018 日-17T07：00： 00.000 Z"，"物质"： {"text"： "Cashew 螺母"}，"status"： "已确认"，"反应"： [{"物质"： {"文本"： "Cashew 螺母 allergenic 提取 Injectable 产品"}，"表现形式"： [{"文本"： "Anaphylactic 反应"}]}]}</span><span class="sxs-lookup"><span data-stu-id="1e420-235">Response: {   "resourceType": "Bundle",   "id": "<bundle-id>",   "type": "searchset",   "total": 1,   "entry": [     {       "resource": {         "resourceType": "AllergyIntolerance",         "id": "<resource-id>",         "recordedDate": "2018-09-17T07:00:00.000Z",         "substance": {           "text": "Cashew nuts"         },         "status": "confirmed",         "reaction": [           {             "substance": {               "text": "cashew nut allergenic extract Injectable Product"             },             "manifestation": [               {                 "text": "Anaphylactic reaction"               }             ]           }         ]       }     }   ] }</span></span>

* * *

<span data-ttu-id="1e420-236">有关[https://www.hl7.org/fhir/DSTU2/AllergyIntolerance.html](https://www.hl7.org/fhir/DSTU2/AllergyIntolerance.html)此字段集的其他详细信息，请参阅。</span><span class="sxs-lookup"><span data-stu-id="1e420-236">See [https://www.hl7.org/fhir/DSTU2/AllergyIntolerance.html](https://www.hl7.org/fhir/DSTU2/AllergyIntolerance.html) for other details on this field set.</span></span>

## <a name="medication-order"></a><span data-ttu-id="1e420-237">药物订货</span><span class="sxs-lookup"><span data-stu-id="1e420-237">Medication Order</span></span>

<span data-ttu-id="1e420-238">以下是最少的必填字段，它们是 Argonaut MedicationOrder 配置文件的子集：</span><span class="sxs-lookup"><span data-stu-id="1e420-238">These are the minimum required fields, which are a subset of the Argonaut MedicationOrder profile:</span></span>

1. <span data-ttu-id="1e420-239">DateWritten</span><span class="sxs-lookup"><span data-stu-id="1e420-239">DateWritten</span></span>
2. <span data-ttu-id="1e420-240">Prescriber 显示</span><span class="sxs-lookup"><span data-stu-id="1e420-240">Prescriber.Display</span></span>
3. <span data-ttu-id="1e420-241">药物的显示（如果参考）</span><span class="sxs-lookup"><span data-stu-id="1e420-241">Medication.Display (if reference)</span></span>
4. <span data-ttu-id="1e420-242">药物文本（如果概念）</span><span class="sxs-lookup"><span data-stu-id="1e420-242">Medication.Text (if concept)</span></span>

<span data-ttu-id="1e420-243">除了 Argonaut 字段外，还可以为患者应用提供出色的用户体验，还可以读取以下字段：</span><span class="sxs-lookup"><span data-stu-id="1e420-243">In addition to the Argonaut fields, for a great user experience the Patients app can also read the following fields:</span></span>

1. <span data-ttu-id="1e420-244">DateEnded</span><span class="sxs-lookup"><span data-stu-id="1e420-244">DateEnded</span></span>
2. <span data-ttu-id="1e420-245">DosageInstruction</span><span class="sxs-lookup"><span data-stu-id="1e420-245">DosageInstruction.Text</span></span>
3. <span data-ttu-id="1e420-246">文本 Div</span><span class="sxs-lookup"><span data-stu-id="1e420-246">Text.Div</span></span>

<span data-ttu-id="1e420-247">资源搜索使用 GET 方法和以下参数：</span><span class="sxs-lookup"><span data-stu-id="1e420-247">A resource search uses the GET method and the following parameters:</span></span>

1. <span data-ttu-id="1e420-248">患者 =\<患者 id></span><span class="sxs-lookup"><span data-stu-id="1e420-248">patient=\<patient id></span></span>
2. <span data-ttu-id="1e420-249">_count =\<最大结果></span><span class="sxs-lookup"><span data-stu-id="1e420-249">_count=\<max results></span></span>

<span data-ttu-id="1e420-250">请参阅下面的此呼叫示例：</span><span class="sxs-lookup"><span data-stu-id="1e420-250">See the following example of this call:</span></span>

* * *

    <span data-ttu-id="1e420-251">请求：获取 <fhir-服务器>/MedicationOrder？患者 =<患者 id>&_count = 10</span><span class="sxs-lookup"><span data-stu-id="1e420-251">Request: GET <fhir-server>/MedicationOrder?patient=<patient-id>&_count=10</span></span>
    
    <span data-ttu-id="1e420-252">响应： {"resourceType"： "捆绑包"，"id"： "<捆绑包-id>"，"type"： "searchset"，"total"：1，"entry"： [{"资源"： {"resourceType"： "MedicationOrder"，"id"： "<资源 id>"，"dateWritten"： "2018-09-17"，"medicationCodeableConcept"： {"text"： "Lisinopril 20 MG 平板电脑"}，"prescriber"： {"display"： "Jane Doe"}，"dosageInstruction"： [{"文本"： "1 天"}]}}]}</span><span class="sxs-lookup"><span data-stu-id="1e420-252">Response: {   "resourceType": "Bundle",   "id": "<bundle-id>",   "type": "searchset",   "total": 1,   "entry": [     {       "resource": {         "resourceType": "MedicationOrder",         "id": "<resource-id>",         "dateWritten": "2018-09-17",         "medicationCodeableConcept": {           "text": "Lisinopril 20 MG Oral Tablet"         },         "prescriber": {           "display": "Jane Doe"         },         "dosageInstruction": [           {             "text": "1 daily"           }         ]       }     }   ] }</span></span>

* * *  

<span data-ttu-id="1e420-253">有关[https://www.hl7.org/fhir/DSTU2/MedicationOrder.html](https://www.hl7.org/fhir/DSTU2/MedicationOrder.html)此字段集的其他详细信息，请参阅。</span><span class="sxs-lookup"><span data-stu-id="1e420-253">See [https://www.hl7.org/fhir/DSTU2/MedicationOrder.html](https://www.hl7.org/fhir/DSTU2/MedicationOrder.html) for other details on this field set.</span></span>

## <a name="coverage"></a><span data-ttu-id="1e420-254">内</span><span class="sxs-lookup"><span data-stu-id="1e420-254">Coverage</span></span>

<span data-ttu-id="1e420-255">以下是 "最少必填字段"，不包含在美国 Core 或 Argonaut 配置文件中：</span><span class="sxs-lookup"><span data-stu-id="1e420-255">These are the minimum required fields, not covered by either US Core or Argonaut profiles:</span></span>

1. <span data-ttu-id="1e420-256">Payor</span><span class="sxs-lookup"><span data-stu-id="1e420-256">Payor</span></span>

<span data-ttu-id="1e420-257">资源搜索使用 GET 方法和以下参数：</span><span class="sxs-lookup"><span data-stu-id="1e420-257">A resource search uses the GET method and the following parameters:</span></span>

1. <span data-ttu-id="1e420-258">患者 =\<患者 id></span><span class="sxs-lookup"><span data-stu-id="1e420-258">patient=\<patient id></span></span>

<span data-ttu-id="1e420-259">请参阅下面的此呼叫示例：</span><span class="sxs-lookup"><span data-stu-id="1e420-259">See the following example of this call:</span></span>

* * *

    <span data-ttu-id="1e420-260">请求：获取 <fhir-服务器>/Coverage？患者 =<患者 id></span><span class="sxs-lookup"><span data-stu-id="1e420-260">Request: GET <fhir-server>/Coverage?patient=<patient-id></span></span>
    
    <span data-ttu-id="1e420-261">响应： {"resourceType"： "捆绑包"，"键入"： "searchset"，"total"：1，"entry"： [{"resource"： "<资源 id>"，"计划"： "没有主保险"，"订阅"： {"reference"： "患者/<患者 id>"}}]}</span><span class="sxs-lookup"><span data-stu-id="1e420-261">Response: {   "resourceType": "Bundle",   "type": "searchset",   "total": 1,   "entry": [     {       "resource": {         "resourceType": "Coverage",         "id": "<resource-id>",         "plan": "No Primary Insurance",         "subscriber": { "reference": "Patient/<patient-id>" }       }     }   ] }</span></span>

* * *

<span data-ttu-id="1e420-262">有关[https://www.hl7.org/fhir/DSTU2/Coverage.html](https://www.hl7.org/fhir/DSTU2/Coverage.html)此字段集的其他详细信息，请参阅。</span><span class="sxs-lookup"><span data-stu-id="1e420-262">See [https://www.hl7.org/fhir/DSTU2/Coverage.html](https://www.hl7.org/fhir/DSTU2/Coverage.html) for other details on this field set.</span></span>

## <a name="location"></a><span data-ttu-id="1e420-263">位置</span><span class="sxs-lookup"><span data-stu-id="1e420-263">Location</span></span>

<span data-ttu-id="1e420-264">此资源仅用作 "[遇到](#encounter)" 资源的参考。</span><span class="sxs-lookup"><span data-stu-id="1e420-264">This resource is only being used as a reference on the [Encounter](#encounter) resource.</span></span>

<span data-ttu-id="1e420-265">有关[https://www.hl7.org/fhir/DSTU2/Location.html](https://www.hl7.org/fhir/DSTU2/Location.html)此字段集的其他详细信息，请参阅。</span><span class="sxs-lookup"><span data-stu-id="1e420-265">See [https://www.hl7.org/fhir/DSTU2/Location.html](https://www.hl7.org/fhir/DSTU2/Location.html) for other details on this field set.</span></span>
