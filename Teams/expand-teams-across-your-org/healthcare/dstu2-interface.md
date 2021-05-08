---
title: 患者应用和 EHR 集成 DSTU2 接口
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
description: 了解应用中的 DSTU2 Teams规范，包括设置或重新配置 FHIR 服务器以使用 Microsoft Teams Patients 应用。
ms.custom: seo-marvel-mar2020
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: 12833ea55977cf7e8d18ee5c10b1f17d898b27b3
ms.sourcegitcommit: beaaee10019f4eda746f348888a4a3c2aaa6f196
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2020
ms.locfileid: "48803480"
---
# <a name="dstu2-interface-specification"></a><span data-ttu-id="dd95e-103">DSTU2 接口规范</span><span class="sxs-lookup"><span data-stu-id="dd95e-103">DSTU2 interface specification</span></span>

> [!NOTE]
> <span data-ttu-id="dd95e-104">从 2020 年 10 月 30 日起，"患者"应用已停用，并替换为 Teams [列表](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) 应用。</span><span class="sxs-lookup"><span data-stu-id="dd95e-104">Effective October 30, 2020, the Patients app has been retired and replaced by the [Lists app](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) in Teams.</span></span> <span data-ttu-id="dd95e-105">患者应用数据存储在支持团队的 Office 365 组的组邮箱中。</span><span class="sxs-lookup"><span data-stu-id="dd95e-105">Patients app data is stored in the group mailbox of the Office 365 group that backs the team.</span></span> <span data-ttu-id="dd95e-106">与该患者应用关联的所有数据将保留在该组，但无法再通过用户界面访问。</span><span class="sxs-lookup"><span data-stu-id="dd95e-106">All data associated with the Patients app is retained in this group but can no longer be accessed through the user interface.</span></span> <span data-ttu-id="dd95e-107">用户可通过"列表"应用或 [重新创建](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db)。</span><span class="sxs-lookup"><span data-stu-id="dd95e-107">Users can re-create their lists using the [Lists app](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db).</span></span>
>
><span data-ttu-id="dd95e-108">借助列表，医疗保健组织中的护理团队可针对各种方案创建患者列表，提供圆形和内联团队会议、常规患者监视等。</span><span class="sxs-lookup"><span data-stu-id="dd95e-108">With Lists, care teams in your healthcare organization can create patient lists for scenarios ranging from rounds and interdisciplinary team meetings to general patient monitoring.</span></span> <span data-ttu-id="dd95e-109">查看列表的"患者"模板以开始使用。</span><span class="sxs-lookup"><span data-stu-id="dd95e-109">Check out the Patients template in Lists to get started.</span></span> <span data-ttu-id="dd95e-110">若要深入了解如何在组织中管理列表应用，请参阅" [列表应用管理](../../manage-lists-app.md)。</span><span class="sxs-lookup"><span data-stu-id="dd95e-110">To learn more about how to manage the Lists app in your organization, see [Manage the Lists app](../../manage-lists-app.md).</span></span>

<span data-ttu-id="dd95e-111">设置或重新配置 FHIR 服务器以使用Microsoft Teams患者应用需要了解应用需要访问哪些数据。</span><span class="sxs-lookup"><span data-stu-id="dd95e-111">Setting up or reconfiguring an FHIR server to work with the Microsoft Teams Patients app requires understanding what data the app needs to access.</span></span> <span data-ttu-id="dd95e-112">FHIR 服务器必须使用捆绑包支持以下资源的 POST 请求：</span><span class="sxs-lookup"><span data-stu-id="dd95e-112">The FHIR server must support POST requests using bundles for the following resources:</span></span>

- [<span data-ttu-id="dd95e-113">Patient</span><span class="sxs-lookup"><span data-stu-id="dd95e-113">Patient</span></span>](#patient)
- [<span data-ttu-id="dd95e-114">观察</span><span class="sxs-lookup"><span data-stu-id="dd95e-114">Observation</span></span>](#observation)
- [<span data-ttu-id="dd95e-115">条件</span><span class="sxs-lookup"><span data-stu-id="dd95e-115">Condition</span></span>](#condition)
- [<span data-ttu-id="dd95e-116">Encounter</span><span class="sxs-lookup"><span data-stu-id="dd95e-116">Encounter</span></span>](#encounter)
- [<span data-ttu-id="dd95e-117">仇恨者</span><span class="sxs-lookup"><span data-stu-id="dd95e-117">Allergy intolerance</span></span>](#allergyintolerance)
- [<span data-ttu-id="dd95e-118">覆盖范围</span><span class="sxs-lookup"><span data-stu-id="dd95e-118">Coverage</span></span>](#coverage)
- [<span data-ttu-id="dd95e-119">药物订单</span><span class="sxs-lookup"><span data-stu-id="dd95e-119">Medication Order</span></span>](#medication-order)
- [<span data-ttu-id="dd95e-120">位置</span><span class="sxs-lookup"><span data-stu-id="dd95e-120">Location</span></span>](#location)

> [!NOTE]
> <span data-ttu-id="dd95e-121">患者资源是唯一必需的 (资源，如果没有该资源，应用将完全无法加载。</span><span class="sxs-lookup"><span data-stu-id="dd95e-121">The Patient resource is the only mandatory resource (without which the app will not load at all.</span></span> <span data-ttu-id="dd95e-122">但是，建议合作伙伴根据下面提供的规范实施对上述所有资源的支持，以获得最佳患者应用最终用户Microsoft Teams体验。</span><span class="sxs-lookup"><span data-stu-id="dd95e-122">However, it is recommended that the Partner implement support for all the above mentioned resources per specifications provided below for the best end-user experience with the Microsoft Teams Patients App.</span></span>

<span data-ttu-id="dd95e-123">从 Microsoft Teams Patients 应用中针对多个资源的查询将捆绑包 (BATCH) FHIR 服务器 URL 的请求发布。</span><span class="sxs-lookup"><span data-stu-id="dd95e-123">Queries from the Microsoft Teams Patients app for more than one resource post a bundle (BATCH) of requests to the FHIR server's URL.</span></span> <span data-ttu-id="dd95e-124">服务器处理每个请求，并返回每个请求匹配的资源捆绑包。</span><span class="sxs-lookup"><span data-stu-id="dd95e-124">The server processes each request and returns a bundle of the resources matched by each request.</span></span> <span data-ttu-id="dd95e-125">有关详细信息和示例，请参阅 [https://www.hl7.org/fhir/DSTU2/http.html#transaction](https://www.hl7.org/fhir/DSTU2/http.html#transaction) 。</span><span class="sxs-lookup"><span data-stu-id="dd95e-125">For more information and examples, see [https://www.hl7.org/fhir/DSTU2/http.html#transaction](https://www.hl7.org/fhir/DSTU2/http.html#transaction).</span></span>

<span data-ttu-id="dd95e-126">以下所有 FHIR 资源都应可通过直接资源引用访问。</span><span class="sxs-lookup"><span data-stu-id="dd95e-126">All the following FHIR resources should be accessible by direct resource reference.</span></span>

## <a name="conformance-minimum-required-field-set"></a><span data-ttu-id="dd95e-127">"满足最低要求"字段集</span><span class="sxs-lookup"><span data-stu-id="dd95e-127">Conformance minimum required field set</span></span>

 <span data-ttu-id="dd95e-128">FHIR 服务器必须实现一致性声明，以便我们获得其功能的事实摘要。</span><span class="sxs-lookup"><span data-stu-id="dd95e-128">The FHIR Server must implement the conformance statement for us to have a factual summary of its capabilities.</span></span> <span data-ttu-id="dd95e-129">DSTU2 FHIR Server 中预期以下参数：</span><span class="sxs-lookup"><span data-stu-id="dd95e-129">We expect the below parameters in a DSTU2 FHIR Server:</span></span>

 - <span data-ttu-id="dd95e-130">REST</span><span class="sxs-lookup"><span data-stu-id="dd95e-130">REST</span></span>

    - <span data-ttu-id="dd95e-131">模式</span><span class="sxs-lookup"><span data-stu-id="dd95e-131">Mode</span></span>
    - <span data-ttu-id="dd95e-132">交互</span><span class="sxs-lookup"><span data-stu-id="dd95e-132">Interaction</span></span>
    - <span data-ttu-id="dd95e-133">资源：类型</span><span class="sxs-lookup"><span data-stu-id="dd95e-133">Resource: Type</span></span>
    - <span data-ttu-id="dd95e-134">安全性 [：OAuth URI 扩展](https://hl7.org/fhir/extension-oauth-uris.html)</span><span class="sxs-lookup"><span data-stu-id="dd95e-134">Security: [Extension for OAuth URIs](https://hl7.org/fhir/extension-oauth-uris.html)</span></span>
   
 - <span data-ttu-id="dd95e-135">FhirVersion (我们的代码需要此代码来了解应该透视到的版本，因为我们支持多个版本。) </span><span class="sxs-lookup"><span data-stu-id="dd95e-135">FhirVersion (Our code requires this to understand which version we should pivot to as we support multiple versions.)</span></span>

<span data-ttu-id="dd95e-136">有关 [https://www.hl7.org/fhir/dstu2/conformance.html](https://www.hl7.org/fhir/dstu2/conformance.html) 此字段集的其他详细信息，请参阅 。</span><span class="sxs-lookup"><span data-stu-id="dd95e-136">See [https://www.hl7.org/fhir/dstu2/conformance.html](https://www.hl7.org/fhir/dstu2/conformance.html) for other details on this field set.</span></span>

## <a name="patient"></a><span data-ttu-id="dd95e-137">Patient</span><span class="sxs-lookup"><span data-stu-id="dd95e-137">Patient</span></span>

<span data-ttu-id="dd95e-138">这些是最小必填字段，这些字段是 [Argonaut 患者配置文件字段的子集](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-patient.html) ：</span><span class="sxs-lookup"><span data-stu-id="dd95e-138">These are the minimum required fields, which are a subset of the [Argonaut patient profile](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-patient.html) fields:</span></span>

 - <span data-ttu-id="dd95e-139">Name.Family</span><span class="sxs-lookup"><span data-stu-id="dd95e-139">Name.Family</span></span>
 - <span data-ttu-id="dd95e-140">Name.Given</span><span class="sxs-lookup"><span data-stu-id="dd95e-140">Name.Given</span></span>
 - <span data-ttu-id="dd95e-141">性别</span><span class="sxs-lookup"><span data-stu-id="dd95e-141">Gender</span></span>
 - <span data-ttu-id="dd95e-142">BirthDate</span><span class="sxs-lookup"><span data-stu-id="dd95e-142">BirthDate</span></span>
 - <span data-ttu-id="dd95e-143">MRN (标识符) </span><span class="sxs-lookup"><span data-stu-id="dd95e-143">MRN (Identifier)</span></span>

<span data-ttu-id="dd95e-144">除了 Argonaut 字段之外，为了获得出色的用户体验，Patients 应用还会读取以下字段：</span><span class="sxs-lookup"><span data-stu-id="dd95e-144">In addition to the Argonaut fields, for a great user experience the Patients app also reads the following fields:</span></span>

 - <span data-ttu-id="dd95e-145">Name.Use</span><span class="sxs-lookup"><span data-stu-id="dd95e-145">Name.Use</span></span>
 - <span data-ttu-id="dd95e-146">Name.Prefix</span><span class="sxs-lookup"><span data-stu-id="dd95e-146">Name.Prefix</span></span>
 - <span data-ttu-id="dd95e-147">CareProvider (此对患者资源的引用应包括以下示例所示的显示字段。) </span><span class="sxs-lookup"><span data-stu-id="dd95e-147">CareProvider (This reference on the Patient resource should include the display fields shown in the following example.)</span></span>

    ```
    Request:
    GET <fhir-server>/Patient/<patient-id>
    
    Response:
    {
      "resourceType": "Patient",
      "id": "<patient-id>",
      .
      .
      .
      "name": [
        {
          "use": "official",
          "prefix": [ "Mr" ],
          "family": [ "Chau" ],
          "given": [ "Hugh" ]
        }
      ],
      "identifier": [
        {
          "use": "official",
          "type": {
            "coding": [
              {
                "system": "https://hl7.org/fhir/v2/0203",
                "code": "MR"
              }
            ]
          },
          "value": "1234567"
        }
      ],
      "gender": "male",
      "birthDate": "1957-06-05",
      "careProvider": [{ "display": "Jane Doe" }],
    }
    ```

<span data-ttu-id="dd95e-148">资源搜索使用 /Patient/_search 的 POST 方法以及以下参数：</span><span class="sxs-lookup"><span data-stu-id="dd95e-148">A resource search uses the POST method at /Patient/_search and the following parameters:</span></span>

 - <span data-ttu-id="dd95e-149">id</span><span class="sxs-lookup"><span data-stu-id="dd95e-149">id</span></span>
 - <span data-ttu-id="dd95e-150">family：contains= (搜索其家庭名称包含 value.) </span><span class="sxs-lookup"><span data-stu-id="dd95e-150">family:contains=(searches for all patients whose family name contains the value.)</span></span>
 - <span data-ttu-id="dd95e-151">given=\<substring></span><span class="sxs-lookup"><span data-stu-id="dd95e-151">given=\<substring></span></span>
 - <span data-ttu-id="dd95e-152">name=\<substring></span><span class="sxs-lookup"><span data-stu-id="dd95e-152">name=\<substring></span></span>
 - <span data-ttu-id="dd95e-153">birthdate= (完全匹配) </span><span class="sxs-lookup"><span data-stu-id="dd95e-153">birthdate=(exact match)</span></span>
 - <span data-ttu-id="dd95e-154">\_count (应返回的结果的最大) </span><span class="sxs-lookup"><span data-stu-id="dd95e-154">\_count (maximum number of results that should be returned)</span></span> <br> <span data-ttu-id="dd95e-155">响应应包含搜索结果返回的记录总数，并且 PatientsApp 将使用计数来限制返回 \_ 的记录数。</span><span class="sxs-lookup"><span data-stu-id="dd95e-155">The response should contain the total count of records returned as a result of the search, and \_count will be used by the PatientsApp to limit the number of records returned.</span></span>
 - <span data-ttu-id="dd95e-156">identifier=\<mrn></span><span class="sxs-lookup"><span data-stu-id="dd95e-156">identifier=\<mrn></span></span>

<span data-ttu-id="dd95e-157">目标是能够按以下条件搜索和筛选患者：</span><span class="sxs-lookup"><span data-stu-id="dd95e-157">The goal is to be able to search and filter for a patient by the following:</span></span>

- <span data-ttu-id="dd95e-158">ID：这是 FHIR 中每个资源具有的资源 ID。</span><span class="sxs-lookup"><span data-stu-id="dd95e-158">ID: This is the resource ID that every resource in FHIR has.</span></span>
- <span data-ttu-id="dd95e-159">MRN：这是患者的实际标识符，该患者是医疗人员会知道的信息。</span><span class="sxs-lookup"><span data-stu-id="dd95e-159">MRN: This is the actual identifier for the patient that clinical staff would know.</span></span> <span data-ttu-id="dd95e-160">我们知道，此 MRN 基于 FHIR 中标识符资源内的标识符类型</span><span class="sxs-lookup"><span data-stu-id="dd95e-160">We understand this MRN is based on the type of identifier inside the identifier resource in FHIR</span></span>
- <span data-ttu-id="dd95e-161">名称</span><span class="sxs-lookup"><span data-stu-id="dd95e-161">Name</span></span>
- <span data-ttu-id="dd95e-162">Birthdate</span><span class="sxs-lookup"><span data-stu-id="dd95e-162">Birthdate</span></span>

<span data-ttu-id="dd95e-163">请参阅以下此调用的示例。</span><span class="sxs-lookup"><span data-stu-id="dd95e-163">See the following example  of this call.</span></span>

```
Request:
POST <fhir-server>/Patient/_search
Request Body:
given=hugh&family=chau

Response:
{
  "resourceType": "Bundle",
  "id": "<bundle-id>",
  .
  .
  .
  "entry": [
    {
      "resource": {
        "resourceType": "Patient",
        "id": "<patient-id>",
        "name": [
          {
            "text": "Hugh Chau",
            "family": [ "Chau" ],
            "given": [ "Hugh" ]
          }
        ],
        "gender": "male",
        "birthDate": "1957-06-05"
      },
      "search": {
        "mode": "match"
      }
    }
  ]
}
```

<span data-ttu-id="dd95e-164">有关 [https://www.hl7.org/fhir/DSTU2/Patient.html](https://www.hl7.org/fhir/DSTU2/Patient.html) 此字段集的其他详细信息，请参阅 。</span><span class="sxs-lookup"><span data-stu-id="dd95e-164">See [https://www.hl7.org/fhir/DSTU2/Patient.html](https://www.hl7.org/fhir/DSTU2/Patient.html) for other details on this field set.</span></span>

## <a name="observation"></a><span data-ttu-id="dd95e-165">观察</span><span class="sxs-lookup"><span data-stu-id="dd95e-165">Observation</span></span>

<span data-ttu-id="dd95e-166">这些是最小必填字段，这些字段是 Argonaut 重要符号配置文件的子集：</span><span class="sxs-lookup"><span data-stu-id="dd95e-166">These are the minimum required fields, which are a subset of the Argonaut vital signs profile:</span></span>

 - <span data-ttu-id="dd95e-167">有效 (日期时间或) </span><span class="sxs-lookup"><span data-stu-id="dd95e-167">Effective (date time or period)</span></span>
 - <span data-ttu-id="dd95e-168">Code.Code.Code</span><span class="sxs-lookup"><span data-stu-id="dd95e-168">Code.Coding.Code</span></span>
 - <span data-ttu-id="dd95e-169">ValueQuantity.Value</span><span class="sxs-lookup"><span data-stu-id="dd95e-169">ValueQuantity.Value</span></span>

<span data-ttu-id="dd95e-170">除了 Argonaut 字段之外，为了获得出色的用户体验，Patients 应用还会读取以下字段：</span><span class="sxs-lookup"><span data-stu-id="dd95e-170">In addition to the Argonaut fields, for a great user experience the Patients app also reads the following fields:</span></span>

 - <span data-ttu-id="dd95e-171">Code.Code.Display</span><span class="sxs-lookup"><span data-stu-id="dd95e-171">Code.Coding.Display</span></span>
 - <span data-ttu-id="dd95e-172">ValueQuantity.Unit</span><span class="sxs-lookup"><span data-stu-id="dd95e-172">ValueQuantity.Unit</span></span>

<span data-ttu-id="dd95e-173">如果使用组件观察，则相同的逻辑适用于每个组件观察。</span><span class="sxs-lookup"><span data-stu-id="dd95e-173">If using component observations, the same logic applies for each component observation.</span></span>

<span data-ttu-id="dd95e-174">资源搜索使用 GET 方法和以下参数：</span><span class="sxs-lookup"><span data-stu-id="dd95e-174">A resource search uses the GET method and the following parameters:</span></span>

 - <span data-ttu-id="dd95e-175">patient=\<patient id\></span><span class="sxs-lookup"><span data-stu-id="dd95e-175">patient=\<patient id\></span></span>
 - <span data-ttu-id="dd95e-176">sort：desc=\<field ex. date\></span><span class="sxs-lookup"><span data-stu-id="dd95e-176">sort:desc=\<field ex. date\></span></span>

<span data-ttu-id="dd95e-177">目标是能够检索患者的最新生命符号 [VitalSigns.DSTU.saz] (？) 。</span><span class="sxs-lookup"><span data-stu-id="dd95e-177">The goal is to be able to retrieve the latest vital signs for a patient, [VitalSigns.DSTU.saz]  (observation?).</span></span>

```
Request:
GET <fhir-server>/Observation?patient=<patient-id>&_sort:desc=date&category=vital-signs

Response:
{
  "resourceType": "Bundle",
  "id": "<bundle-id>",
  "type": "searchset",
  "total": 20,
  "entry": [
    {
      "resource": {
        "resourceType": "Observation",
        "id": "<resource-id>",
        "category": {
          "coding": [ { code": "vital-signs" } ],
        },
        "code": {
          "coding": [
            {
              "system": "http://loinc.org",
              "code": "39156-5",
              "display": "bmi"
            }
          ],
        },
        "effectiveDateTime": "2009-12-01",
        "valueQuantity": {
          "value": 34.4,
          "unit": "kg/m2",
          "system": "http://unitsofmeasure.org",
          "code": "kg/m2"
        }
      },
    },
    .
    .
    .
  ]
}
```

<span data-ttu-id="dd95e-178">有关 [https://www.hl7.org/fhir/DSTU2/Observation.html](https://www.hl7.org/fhir/DSTU2/Observation.html) 此字段集的其他详细信息，请参阅 。</span><span class="sxs-lookup"><span data-stu-id="dd95e-178">See [https://www.hl7.org/fhir/DSTU2/Observation.html](https://www.hl7.org/fhir/DSTU2/Observation.html) for other details on this field set.</span></span>

## <a name="condition"></a><span data-ttu-id="dd95e-179">条件</span><span class="sxs-lookup"><span data-stu-id="dd95e-179">Condition</span></span>

<span data-ttu-id="dd95e-180">这些是最小必填字段，这些字段是 [Argonaut 条件配置文件的子集](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-condition.html)：</span><span class="sxs-lookup"><span data-stu-id="dd95e-180">These are the minimum required fields, which are a subset of the [Argonaut condition profile](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-condition.html):</span></span>

1. <span data-ttu-id="dd95e-181">Code.Code[0]。显示</span><span class="sxs-lookup"><span data-stu-id="dd95e-181">Code.Coding[0].Display</span></span>

<span data-ttu-id="dd95e-182">除了 Argonaut 字段之外，为了获得出色的用户体验，Patients 应用还可以读取以下字段：</span><span class="sxs-lookup"><span data-stu-id="dd95e-182">In addition to the Argonaut fields, for a great user experience the Patients app can also read the following fields:</span></span>

 - <span data-ttu-id="dd95e-183">记录的日期</span><span class="sxs-lookup"><span data-stu-id="dd95e-183">Date Recorded</span></span>
 - <span data-ttu-id="dd95e-184">严重性</span><span class="sxs-lookup"><span data-stu-id="dd95e-184">Severity</span></span>

<span data-ttu-id="dd95e-185">资源搜索使用 GET 方法和以下参数：</span><span class="sxs-lookup"><span data-stu-id="dd95e-185">A resource search uses the GET method and the following parameters:</span></span>

 - <span data-ttu-id="dd95e-186">patient=\<patient id></span><span class="sxs-lookup"><span data-stu-id="dd95e-186">patient=\<patient id></span></span>
 - <span data-ttu-id="dd95e-187">_count=\<max results></span><span class="sxs-lookup"><span data-stu-id="dd95e-187">_count=\<max results></span></span>

<span data-ttu-id="dd95e-188">请参阅以下此调用示例：</span><span class="sxs-lookup"><span data-stu-id="dd95e-188">See the following example of this call:</span></span>

```
Request:
GET <fhir-server>/Condition?patient=<patient-id>&_count=10

Response:
{
  "resourceType": "Bundle",
  "id": "<bundle-id>",
  "type": "searchset",
  "total": 1,
  "entry": [
    {
      "resource": {
        "resourceType": "Condition",
        "id": "<resource-id>",
        "code": {
          "coding": [
            {
              "system": "http://snomed.info/sct",
              "code": "386033004",
              "display": "Neuropathy (nerve damage)"
            }
          ]
        },
        "dateRecorded": "2018-09-17",
        "severity": {
          "coding": [
            {
              "system": "http://snomed.info/sct",
              "code": "24484000",
              "display": "Severe"
            }
          ]
        }
      },
    }
  ]
}
```

<span data-ttu-id="dd95e-189">有关 [https://www.hl7.org/fhir/DSTU2/Condition.html](https://www.hl7.org/fhir/DSTU2/Condition.html) 此字段集的其他详细信息，请参阅 。</span><span class="sxs-lookup"><span data-stu-id="dd95e-189">See [https://www.hl7.org/fhir/DSTU2/Condition.html](https://www.hl7.org/fhir/DSTU2/Condition.html) for other details on this field set.</span></span>

## <a name="encounter"></a><span data-ttu-id="dd95e-190">Encounter</span><span class="sxs-lookup"><span data-stu-id="dd95e-190">Encounter</span></span>

<span data-ttu-id="dd95e-191">这些是最小必填字段，这些字段是 US Core Encounter 配置文件"必须包含"字段的子集：</span><span class="sxs-lookup"><span data-stu-id="dd95e-191">These are the minimum required fields, which are a subset of the US Core Encounter profile "must have" fields:</span></span>

 - <span data-ttu-id="dd95e-192">状态</span><span class="sxs-lookup"><span data-stu-id="dd95e-192">Status</span></span>
 - <span data-ttu-id="dd95e-193">Type[0]。编码[0]。显示</span><span class="sxs-lookup"><span data-stu-id="dd95e-193">Type[0].Coding[0].Display</span></span>

<span data-ttu-id="dd95e-194">此外，US Core Encounter 配置文件的"必须支持"字段中的以下字段</span><span class="sxs-lookup"><span data-stu-id="dd95e-194">In addition, the following fields from US Core Encounter profile's "must support" fields</span></span>

 - <span data-ttu-id="dd95e-195">Period.Start</span><span class="sxs-lookup"><span data-stu-id="dd95e-195">Period.Start</span></span>
 - <span data-ttu-id="dd95e-196">Location[0]。Location.Display</span><span class="sxs-lookup"><span data-stu-id="dd95e-196">Location[0].Location.Display</span></span>

<span data-ttu-id="dd95e-197">资源搜索使用 GET 方法和以下参数：</span><span class="sxs-lookup"><span data-stu-id="dd95e-197">A resource search uses the GET method and the following parameters:</span></span>

 - <span data-ttu-id="dd95e-198">patient=\<patient id></span><span class="sxs-lookup"><span data-stu-id="dd95e-198">patient=\<patient id></span></span>
 - <span data-ttu-id="dd95e-199">_sort：desc=\<field ex. date></span><span class="sxs-lookup"><span data-stu-id="dd95e-199">_sort:desc=\<field ex. date></span></span>
 - <span data-ttu-id="dd95e-200">_count=\<max results></span><span class="sxs-lookup"><span data-stu-id="dd95e-200">_count=\<max results></span></span>

<span data-ttu-id="dd95e-201">目标是能够检索患者上次已知的位置。</span><span class="sxs-lookup"><span data-stu-id="dd95e-201">The goal is to be able to retrieve the patient's last known location.</span></span> <span data-ttu-id="dd95e-202">每次遇到都引用一个位置资源。</span><span class="sxs-lookup"><span data-stu-id="dd95e-202">Each encounter references a location resource.</span></span> <span data-ttu-id="dd95e-203">引用还应包括位置的显示字段。</span><span class="sxs-lookup"><span data-stu-id="dd95e-203">The reference shall also include the location's display field.</span></span> <span data-ttu-id="dd95e-204">请参阅以下此调用的示例。</span><span class="sxs-lookup"><span data-stu-id="dd95e-204">See the following example of this call.</span></span>

```
Request:
GET <fhir-server>/Encounter?patient=<patient-id>&_sort:desc=date&_count=1

Response:
{
  "resourceType": "Bundle",
  "type": "searchset",
  "total": 1,
  "entry": [
    {
      "resource": {
        "resourceType": "Encounter",
        "id": "<resource-id>",
        "identifier": [{ "use": "official", "value": "<id>" }],
        "status": "arrived",
        "type": [
          {
            "coding": [{ "display": "Appointment" }],
          }
        ],
        "patient": { "reference": "Patient/<patient-id>" },
        "period": { "start": "09/17/2018 1:00:00 PM" },
        "location": [
          {
            "location": { "display": "Clinic - ENT" },
          }
        ]
      }
    }
  ]
}
```

<span data-ttu-id="dd95e-205">有关 [https://www.hl7.org/fhir/DSTU2/Encounter.htm](https://www.hl7.org/fhir/DSTU2/Encounter.htm) 此字段集的其他详细信息，请参阅 。</span><span class="sxs-lookup"><span data-stu-id="dd95e-205">See [https://www.hl7.org/fhir/DSTU2/Encounter.htm](https://www.hl7.org/fhir/DSTU2/Encounter.htm) for other details on this field set.</span></span>

## <a name="allergyintolerance"></a><span data-ttu-id="dd95e-206">管理障碍</span><span class="sxs-lookup"><span data-stu-id="dd95e-206">AllergyIntolerance</span></span>

<span data-ttu-id="dd95e-207">这些是最小必填字段，这些字段是 ArgonautAutyIntolerance 配置文件的子集：</span><span class="sxs-lookup"><span data-stu-id="dd95e-207">These are the minimum required fields, which are a subset of the Argonaut AllergyIntolerance profile:</span></span>

 - <span data-ttu-id="dd95e-208">Code.Text</span><span class="sxs-lookup"><span data-stu-id="dd95e-208">Code.Text</span></span>
 - <span data-ttu-id="dd95e-209">Code.Code[0]。显示</span><span class="sxs-lookup"><span data-stu-id="dd95e-209">Code.Coding[0].Display</span></span>
 - <span data-ttu-id="dd95e-210">状态</span><span class="sxs-lookup"><span data-stu-id="dd95e-210">Status</span></span>

<span data-ttu-id="dd95e-211">除了 Argonaut 字段之外，为了获得出色的用户体验，Patients 应用还会读取以下字段：</span><span class="sxs-lookup"><span data-stu-id="dd95e-211">In addition to the Argonaut fields, for a great user experience the Patients app also reads the following fields:</span></span>

 - <span data-ttu-id="dd95e-212">RecordedDate</span><span class="sxs-lookup"><span data-stu-id="dd95e-212">RecordedDate</span></span>
 - <span data-ttu-id="dd95e-213">Note.Text</span><span class="sxs-lookup"><span data-stu-id="dd95e-213">Note.Text</span></span>
 - <span data-ttu-id="dd95e-214">Reaction[..]。内容.文本</span><span class="sxs-lookup"><span data-stu-id="dd95e-214">Reaction[..].Substance.Text</span></span>
 - <span data-ttu-id="dd95e-215">Reaction[..]。一切[..]。文本</span><span class="sxs-lookup"><span data-stu-id="dd95e-215">Reaction[..].Manifestation[..].Text</span></span>
 - <span data-ttu-id="dd95e-216">Text.Div</span><span class="sxs-lookup"><span data-stu-id="dd95e-216">Text.Div</span></span>

<span data-ttu-id="dd95e-217">资源搜索使用 GET 方法和以下参数：</span><span class="sxs-lookup"><span data-stu-id="dd95e-217">A resource search uses the GET method and the following parameters:</span></span>

 - <span data-ttu-id="dd95e-218">Patient =  \<patient id></span><span class="sxs-lookup"><span data-stu-id="dd95e-218">Patient =  \<patient id></span></span>

<span data-ttu-id="dd95e-219">请参阅以下此调用示例：</span><span class="sxs-lookup"><span data-stu-id="dd95e-219">See the following example of this call:</span></span>

```
Request:
GET <fhir-server>/AllergyIntolerance?patient=<patient-id>

Response:
{
  "resourceType": "Bundle",
  "id": "<bundle-id>",
  "type": "searchset",
  "total": 1,
  "entry": [
    {
      "resource": {
        "resourceType": "AllergyIntolerance",
        "id": "<resource-id>",
        "recordedDate": "2018-09-17T07:00:00.000Z",
        "substance": {
          "text": "Cashew nuts"
        },
        "status": "confirmed",
        "reaction": [
          {
            "substance": {
              "text": "cashew nut allergenic extract Injectable Product"
            },
            "manifestation": [
              {
                "text": "Anaphylactic reaction"
              }
            ]
          }
        ]
      }
    }
  ]
}
```

<span data-ttu-id="dd95e-220">有关 [https://www.hl7.org/fhir/DSTU2/AllergyIntolerance.html](https://www.hl7.org/fhir/DSTU2/AllergyIntolerance.html) 此字段集的其他详细信息，请参阅 。</span><span class="sxs-lookup"><span data-stu-id="dd95e-220">See [https://www.hl7.org/fhir/DSTU2/AllergyIntolerance.html](https://www.hl7.org/fhir/DSTU2/AllergyIntolerance.html) for other details on this field set.</span></span>

## <a name="medication-order"></a><span data-ttu-id="dd95e-221">药物订单</span><span class="sxs-lookup"><span data-stu-id="dd95e-221">Medication Order</span></span>

<span data-ttu-id="dd95e-222">这些是最小必填字段，这些字段是 Argonaut 的一部分"一文""Order"配置文件：</span><span class="sxs-lookup"><span data-stu-id="dd95e-222">These are the minimum required fields, which are a subset of the Argonaut MedicationOrder profile:</span></span>

 - <span data-ttu-id="dd95e-223">DateWritten</span><span class="sxs-lookup"><span data-stu-id="dd95e-223">DateWritten</span></span>
 - <span data-ttu-id="dd95e-224">管理程序.Display</span><span class="sxs-lookup"><span data-stu-id="dd95e-224">Prescriber.Display</span></span>
 - <span data-ttu-id="dd95e-225">如果参考， (显示) </span><span class="sxs-lookup"><span data-stu-id="dd95e-225">Medication.Display (if reference)</span></span>
 - <span data-ttu-id="dd95e-226">药物.文本 (概念) </span><span class="sxs-lookup"><span data-stu-id="dd95e-226">Medication.Text (if concept)</span></span>

<span data-ttu-id="dd95e-227">除了 Argonaut 字段之外，为了获得出色的用户体验，Patients 应用还可以读取以下字段：</span><span class="sxs-lookup"><span data-stu-id="dd95e-227">In addition to the Argonaut fields, for a great user experience the Patients app can also read the following fields:</span></span>

 - <span data-ttu-id="dd95e-228">DateEnded</span><span class="sxs-lookup"><span data-stu-id="dd95e-228">DateEnded</span></span>
 - <span data-ttu-id="dd95e-229">一文</span><span class="sxs-lookup"><span data-stu-id="dd95e-229">DosageInstruction.Text</span></span>
 - <span data-ttu-id="dd95e-230">Text.Div</span><span class="sxs-lookup"><span data-stu-id="dd95e-230">Text.Div</span></span>

<span data-ttu-id="dd95e-231">资源搜索使用 GET 方法和以下参数：</span><span class="sxs-lookup"><span data-stu-id="dd95e-231">A resource search uses the GET method and the following parameters:</span></span>

 - <span data-ttu-id="dd95e-232">patient=\<patient id></span><span class="sxs-lookup"><span data-stu-id="dd95e-232">patient=\<patient id></span></span>
 - <span data-ttu-id="dd95e-233">_count=\<max results></span><span class="sxs-lookup"><span data-stu-id="dd95e-233">_count=\<max results></span></span>

<span data-ttu-id="dd95e-234">请参阅以下此调用示例：</span><span class="sxs-lookup"><span data-stu-id="dd95e-234">See the following example of this call:</span></span>

```
Request:
GET <fhir-server>/MedicationOrder?patient=<patient-id>&_count=10

Response:
{
  "resourceType": "Bundle",
  "id": "<bundle-id>",
  "type": "searchset",
  "total": 1,
  "entry": [
    {
      "resource": {
        "resourceType": "MedicationOrder",
        "id": "<resource-id>",
        "dateWritten": "2018-09-17",
        "medicationCodeableConcept": {
          "text": "Lisinopril 20 MG Oral Tablet"
        },
        "prescriber": {
          "display": "Jane Doe"
        },
        "dosageInstruction": [
          {
            "text": "1 daily"
          }
        ]
      }
    }
  ]
}
```

<span data-ttu-id="dd95e-235">有关 [https://www.hl7.org/fhir/DSTU2/MedicationOrder.html](https://www.hl7.org/fhir/DSTU2/MedicationOrder.html) 此字段集的其他详细信息，请参阅 。</span><span class="sxs-lookup"><span data-stu-id="dd95e-235">See [https://www.hl7.org/fhir/DSTU2/MedicationOrder.html](https://www.hl7.org/fhir/DSTU2/MedicationOrder.html) for other details on this field set.</span></span>

## <a name="coverage"></a><span data-ttu-id="dd95e-236">覆盖范围</span><span class="sxs-lookup"><span data-stu-id="dd95e-236">Coverage</span></span>

<span data-ttu-id="dd95e-237">这些是最小必填字段，US Core 或 Argonaut 配置文件未涵盖这些字段：</span><span class="sxs-lookup"><span data-stu-id="dd95e-237">These are the minimum required fields, not covered by either US Core or Argonaut profiles:</span></span>

 - <span data-ttu-id="dd95e-238">支付方</span><span class="sxs-lookup"><span data-stu-id="dd95e-238">Payor</span></span>

<span data-ttu-id="dd95e-239">资源搜索使用 GET 方法和以下参数：</span><span class="sxs-lookup"><span data-stu-id="dd95e-239">A resource search uses the GET method and the following parameters:</span></span>

 - <span data-ttu-id="dd95e-240">patient=\<patient id></span><span class="sxs-lookup"><span data-stu-id="dd95e-240">patient=\<patient id></span></span>

<span data-ttu-id="dd95e-241">请参阅以下此调用示例：</span><span class="sxs-lookup"><span data-stu-id="dd95e-241">See the following example of this call:</span></span>

```
Request:
GET <fhir-server>/Coverage?patient=<patient-id>

Response:
{
  "resourceType": "Bundle",
  "type": "searchset",
  "total": 1,
  "entry": [
    {
      "resource": {
        "resourceType": "Coverage",
        "id": "<resource-id>",
        "plan": "No Primary Insurance",
        "subscriber": { "reference": "Patient/<patient-id>" }
      }
    }
  ]
}
```
    
<span data-ttu-id="dd95e-242">有关 [https://www.hl7.org/fhir/DSTU2/Coverage.html](https://www.hl7.org/fhir/DSTU2/Coverage.html) 此字段集的其他详细信息，请参阅 。</span><span class="sxs-lookup"><span data-stu-id="dd95e-242">See [https://www.hl7.org/fhir/DSTU2/Coverage.html](https://www.hl7.org/fhir/DSTU2/Coverage.html) for other details on this field set.</span></span>

## <a name="location"></a><span data-ttu-id="dd95e-243">位置</span><span class="sxs-lookup"><span data-stu-id="dd95e-243">Location</span></span>

<span data-ttu-id="dd95e-244">此资源仅用于对 Encounter 资源 [的引用](#encounter) 。</span><span class="sxs-lookup"><span data-stu-id="dd95e-244">This resource is only being used as a reference on the [Encounter](#encounter) resource.</span></span>

<span data-ttu-id="dd95e-245">有关 [https://www.hl7.org/fhir/DSTU2/Location.html](https://www.hl7.org/fhir/DSTU2/Location.html) 此字段集的其他详细信息，请参阅 。</span><span class="sxs-lookup"><span data-stu-id="dd95e-245">See [https://www.hl7.org/fhir/DSTU2/Location.html](https://www.hl7.org/fhir/DSTU2/Location.html) for other details on this field set.</span></span>
