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
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: a36c6176b4873dd41d654493bd36e9a3dbbfd49a
ms.sourcegitcommit: 18b5e3487ba1350c5d2e6d676a4ab582b5b638d4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "48772263"
---
# <a name="stu3-interface-specification"></a><span data-ttu-id="3b302-103">STU3 接口规范</span><span class="sxs-lookup"><span data-stu-id="3b302-103">STU3 interface specification</span></span>

> [!NOTE]
> <span data-ttu-id="3b302-104">2020年10月30日，患者应用已停用，并已由团队中的 " [列表" 应用](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) 取代。</span><span class="sxs-lookup"><span data-stu-id="3b302-104">Effective October 30, 2020, the Patients app has been retired and replaced by the [Lists app](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) in Teams.</span></span> <span data-ttu-id="3b302-105">利用 "列表"，医疗保健组织中的 "护理团队" 可以创建各种方案的患者列表，包括从倒圆角和 interdisciplinary 团队会议到常规患者监控。</span><span class="sxs-lookup"><span data-stu-id="3b302-105">With Lists, care teams in your healthcare organization can create patient lists for scenarios ranging from rounds and interdisciplinary team meetings to general patient monitoring.</span></span> <span data-ttu-id="3b302-106">查看列表中的患者模板以开始使用。</span><span class="sxs-lookup"><span data-stu-id="3b302-106">Check out the Patients template in Lists to get started.</span></span> <span data-ttu-id="3b302-107">若要了解有关如何管理组织中的列表应用的详细信息，请参阅 [管理列表应用](../../manage-lists-app.md)。</span><span class="sxs-lookup"><span data-stu-id="3b302-107">To learn more about how to manage the Lists app in your organization, see [Manage the Lists app](../../manage-lists-app.md).</span></span>

<span data-ttu-id="3b302-108">设置或重新配置 FHIR 服务器以处理 Microsoft 团队患者应用需要了解应用需要访问的数据。</span><span class="sxs-lookup"><span data-stu-id="3b302-108">Setting up or reconfiguring an FHIR server to work with the Microsoft Teams Patients app requires understanding what data the app needs to access.</span></span> <span data-ttu-id="3b302-109">FHIR 服务器必须使用以下资源的捆绑包支持发布请求：</span><span class="sxs-lookup"><span data-stu-id="3b302-109">The FHIR server must support POST requests using bundles for the following resources:</span></span>

- [<span data-ttu-id="3b302-110">档案</span><span class="sxs-lookup"><span data-stu-id="3b302-110">Patient</span></span>](#patient)
- [<span data-ttu-id="3b302-111">知识产权</span><span class="sxs-lookup"><span data-stu-id="3b302-111">Observation</span></span>](#observation)
- [<span data-ttu-id="3b302-112">条件</span><span class="sxs-lookup"><span data-stu-id="3b302-112">Condition</span></span>](#condition)
- [<span data-ttu-id="3b302-113">产生</span><span class="sxs-lookup"><span data-stu-id="3b302-113">Encounter</span></span>](#encounter)
- [<span data-ttu-id="3b302-114">过敏症 Intolerance</span><span class="sxs-lookup"><span data-stu-id="3b302-114">Allergy Intolerance</span></span>](#allergyintolerance)
- [<span data-ttu-id="3b302-115">内</span><span class="sxs-lookup"><span data-stu-id="3b302-115">Coverage</span></span>](#coverage)
- <span data-ttu-id="3b302-116">[药物报表](#medication-request) (替换 PATIENTSAPP 的 DSTU2 版本中的 MedicationOrder) </span><span class="sxs-lookup"><span data-stu-id="3b302-116">[Medication Statement](#medication-request) (replaces the MedicationOrder in the DSTU2 version of the PatientsApp)</span></span>
- <span data-ttu-id="3b302-117">位置 (此资源所需的信息可以包含在 "遇到") </span><span class="sxs-lookup"><span data-stu-id="3b302-117">Location (the information needed from this resource can be included in Encounter)</span></span>

> [!NOTE]
> <span data-ttu-id="3b302-118">患者资源是唯一必需的资源 (不会在所有) 加载的应用;但是，建议合作伙伴针对 Microsoft 团队患者应用的最佳最终用户体验，针对以下提供的针对以上提及的所有资源提供支持。</span><span class="sxs-lookup"><span data-stu-id="3b302-118">The Patient resource is the only mandatory resource (without which the app will not load at all); However, it is recommended that the Partner implement support for all the above mentioned resources per specifications provided below for the best end-user experience with the Microsoft Teams Patients App.</span></span>

<span data-ttu-id="3b302-119">来自 Microsoft 团队患者应用的来自多个资源的查询将发布 (批处理) FHIR 服务器 URL 的捆绑包。</span><span class="sxs-lookup"><span data-stu-id="3b302-119">Queries from the Microsoft Teams Patients app for more than one resource shall post a bundle (BATCH) of requests to the FHIR server's URL.</span></span> <span data-ttu-id="3b302-120">服务器应对每个请求进行处理，并返回每个请求所匹配的资源的捆绑包。</span><span class="sxs-lookup"><span data-stu-id="3b302-120">The server shall process each request and return a bundle of the resources matched by each request.</span></span> <span data-ttu-id="3b302-121">有关详细信息和示例，请参阅 [https://www.hl7.org/fhir/STU3/http.html#transaction](https://www.hl7.org/fhir/STU3/http.html#transaction) 。</span><span class="sxs-lookup"><span data-stu-id="3b302-121">For more information and examples, see [https://www.hl7.org/fhir/STU3/http.html#transaction](https://www.hl7.org/fhir/STU3/http.html#transaction).</span></span>

## <a name="capability-statement"></a><span data-ttu-id="3b302-122">功能陈述</span><span class="sxs-lookup"><span data-stu-id="3b302-122">Capability Statement</span></span>

<span data-ttu-id="3b302-123">以下是最少的必填字段：</span><span class="sxs-lookup"><span data-stu-id="3b302-123">These are the minimum required fields:</span></span>

 - <span data-ttu-id="3b302-124">余下</span><span class="sxs-lookup"><span data-stu-id="3b302-124">REST</span></span>

    - <span data-ttu-id="3b302-125">众</span><span class="sxs-lookup"><span data-stu-id="3b302-125">Mode</span></span>
    - <span data-ttu-id="3b302-126">相交</span><span class="sxs-lookup"><span data-stu-id="3b302-126">Interaction</span></span>
    - <span data-ttu-id="3b302-127">资源：类型</span><span class="sxs-lookup"><span data-stu-id="3b302-127">Resource: Type</span></span>
    - <span data-ttu-id="3b302-128">安全性： [OAuth uri 的扩展](https://hl7.org/fhir/extension-oauth-uris.html)</span><span class="sxs-lookup"><span data-stu-id="3b302-128">Security: [Extension for OAuth URIs](https://hl7.org/fhir/extension-oauth-uris.html)</span></span>
    
 - <span data-ttu-id="3b302-129">FhirVersion (我们的代码需要此内容才能了解应将数据透视到哪个版本。 ) </span><span class="sxs-lookup"><span data-stu-id="3b302-129">FhirVersion (Our code requires this to understand which version we should pivot to.)</span></span>

<span data-ttu-id="3b302-130">[https://www.hl7.org/fhir/stu3/capabilitystatement.html](https://www.hl7.org/fhir/stu3/capabilitystatement.html)有关此字段集的其他详细信息，请参阅。</span><span class="sxs-lookup"><span data-stu-id="3b302-130">See [https://www.hl7.org/fhir/stu3/capabilitystatement.html](https://www.hl7.org/fhir/stu3/capabilitystatement.html) for other details on this field set.</span></span>

## <a name="patient"></a><span data-ttu-id="3b302-131">档案</span><span class="sxs-lookup"><span data-stu-id="3b302-131">Patient</span></span>

<span data-ttu-id="3b302-132">下面是 "Argonaut" 患者档案字段子集的最少必填字段：</span><span class="sxs-lookup"><span data-stu-id="3b302-132">Here are the minimum required fields, which are a subset of the Argonaut patient profile fields:</span></span>

 - <span data-ttu-id="3b302-133">名称。给定</span><span class="sxs-lookup"><span data-stu-id="3b302-133">Name.Given</span></span>
 - <span data-ttu-id="3b302-134">名称。家庭</span><span class="sxs-lookup"><span data-stu-id="3b302-134">Name.Family</span></span>
 - <span data-ttu-id="3b302-135">性别</span><span class="sxs-lookup"><span data-stu-id="3b302-135">Gender</span></span>
 - <span data-ttu-id="3b302-136">BirthDate</span><span class="sxs-lookup"><span data-stu-id="3b302-136">BirthDate</span></span>
 - <span data-ttu-id="3b302-137">MRN (标识符) </span><span class="sxs-lookup"><span data-stu-id="3b302-137">MRN (Identifier)</span></span>

<span data-ttu-id="3b302-138">除了 [Argonaut 字段](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-patient.html)外，还可以为患者应用提供出色的用户体验，还可以读取以下字段：</span><span class="sxs-lookup"><span data-stu-id="3b302-138">In addition to the [Argonaut fields](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-patient.html), for a great user experience the Patients app can also read the following fields:</span></span>

 - <span data-ttu-id="3b302-139">名称。使用</span><span class="sxs-lookup"><span data-stu-id="3b302-139">Name.Use</span></span>
 - <span data-ttu-id="3b302-140">名称。前缀</span><span class="sxs-lookup"><span data-stu-id="3b302-140">Name.Prefix</span></span>
 - <span data-ttu-id="3b302-141">[GeneralPractitioner]-GeneralPractitioner 参考应包含在患者资源 (仅限显示字段中) </span><span class="sxs-lookup"><span data-stu-id="3b302-141">[GeneralPractitioner] - The GeneralPractitioner reference should be included in the Patient resource (display field only)</span></span>

<span data-ttu-id="3b302-142">资源搜索在/Patient/_search 使用 POST 方法，并使用以下参数：</span><span class="sxs-lookup"><span data-stu-id="3b302-142">A resource search uses the POST method at /Patient/_search and the following parameters:</span></span>

 - <span data-ttu-id="3b302-143">标识号</span><span class="sxs-lookup"><span data-stu-id="3b302-143">id</span></span>
 - <span data-ttu-id="3b302-144">系列 = (搜索其系列名称包含该值的所有患者) </span><span class="sxs-lookup"><span data-stu-id="3b302-144">family=(searches for all patients whose family name contains the value)</span></span>
 - <span data-ttu-id="3b302-145">给定 =\<substring></span><span class="sxs-lookup"><span data-stu-id="3b302-145">given=\<substring></span></span>
 - <span data-ttu-id="3b302-146">出生日期 = (完全匹配) </span><span class="sxs-lookup"><span data-stu-id="3b302-146">birthdate=(exact match)</span></span>
 - <span data-ttu-id="3b302-147">性别 = (值是一个管理性别) </span><span class="sxs-lookup"><span data-stu-id="3b302-147">gender=(values being one of the administrative-gender)</span></span>
 - <span data-ttu-id="3b302-148">\_计数 (应返回的最大结果数) </span><span class="sxs-lookup"><span data-stu-id="3b302-148">\_count (maximum number of results that should be returned)</span></span> <br> <span data-ttu-id="3b302-149">该响应应包含作为搜索和计数的结果返回的记录总数， \_ PatientsApp 将使用该计数来限制返回的记录数。</span><span class="sxs-lookup"><span data-stu-id="3b302-149">The response should contain the total count of records returned as a result of the search and \_count will be used by the PatientsApp to limit the number of records returned.</span></span>
 - <span data-ttu-id="3b302-150">标识符 =\<mrn></span><span class="sxs-lookup"><span data-stu-id="3b302-150">identifier=\<mrn></span></span>

<span data-ttu-id="3b302-151">目标是能够搜索和筛选患者，如下所示：</span><span class="sxs-lookup"><span data-stu-id="3b302-151">The goal is to be able to search and filter for a patient by the following:</span></span>

- <span data-ttu-id="3b302-152">ID：这是 FHIR 中的每个资源具有的资源 ID。</span><span class="sxs-lookup"><span data-stu-id="3b302-152">ID: This is the resource ID that every resource in FHIR has.</span></span>
- <span data-ttu-id="3b302-153">MRN：这是临床人员将知道的患者的实际标识符。</span><span class="sxs-lookup"><span data-stu-id="3b302-153">MRN: This is the actual identifier for the patient that clinical staff would know.</span></span> <span data-ttu-id="3b302-154">我们理解此 MRN 基于 FHIR 中的标识符资源内的标识符类型。</span><span class="sxs-lookup"><span data-stu-id="3b302-154">We understand this MRN is based on the type of identifier inside the identifier resource in FHIR.</span></span>
- <span data-ttu-id="3b302-155">名称</span><span class="sxs-lookup"><span data-stu-id="3b302-155">Name</span></span>
- <span data-ttu-id="3b302-156">Birthdate</span><span class="sxs-lookup"><span data-stu-id="3b302-156">Birthdate</span></span>

<span data-ttu-id="3b302-157">请参阅下面的通话示例：</span><span class="sxs-lookup"><span data-stu-id="3b302-157">See the following example of the call:</span></span>

```
Request:
POST <fhir-server>/Patient/_search
Request Body:
given=ruth&family=black

Response:
{
  "resourceType": "Bundle",
  "id": "<bundle-id>",
  "meta": {
    "lastUpdated": "2019-01-14T23:44:45.052+00:00"
  },
  "type": "searchset",
  "total": 1,
  "link": [
    {
      "relation": "self",
      "url": <fhir-server>/Patient/_search"
    }
  ],
  "entry": [
    {
      "fullUrl": <fhir-server>/Patient/<patient-id>",
      "resource": {
        "resourceType": "Patient",
        "id": "<patient-id>",
        "meta": {
          "versionId": "1",
          "lastUpdated": "2017-10-18T18:32:37.000+00:00"
        },
        "text": {
          "status": "generated",
          "div": "<div>\n        <p>Ruth Black</p>\n      </div>"
        },
        "identifier": [
          {
            "use": "usual",
            "type": {
              "coding": [
                {
                  "system": "https://hl7.org/fhir/v2/0203",
                  "code": "MR",
                  "display": "Medical record number",
                  "userSelected": false
                }
              ],
              "text": "Medical record number"
            },
            "system": "http://hospital.smarthealthit.org",
            "value": "1234567"
          }
        ],
        "active": true,
        "name": [
          {
            "use": "official",
            "family": "Black",
            "given": [
              "Ruth",
              "C."
            ]
          }
        ],
        "telecom": [
          {
            "system": "phone",
            "value": "800-599-2739",
            "use": "home"
          },
          {
            "system": "phone",
            "value": "800-808-7785",
            "use": "mobile"
          },
          {
            "system": "email",
            "value": "ruth.black@example.com"
          }
        ],
        "gender": "female",
        "birthDate": "1951-08-23",
        "address": [
          {
            "use": "home",
            "line": [
              "26 South RdApt 22"
            ],
            "city": "Sapulpa",
            "state": "OK",
            "postalCode": "74066",
            "country": "USA"
          }
        ]
      },
      "search": {
        "mode": "match"
      }
    }
  ]
}
```

```
Request:
GET <fhir-server>/Patient/<patient-id>

Response:
{
  "resourceType": "Patient",
  "id": "<patient-id>",
  "identifier": [
    {
      "use": "usual",
      "type": {
        "coding": [
          {
            "system": "https://hl7.org/fhir/v2/0203",
            "code": "MR",
          }
        ],
        "text": "Medical record number"
      },
      "value": "1234567"
    }
  ],
  "name": [
    {
      "use": "official",
      "family": "Adams",
      "given": [ "Daniel", "X." ]
    }
  ],
  "gender": "male",
  "birthDate": "1925-12-23",
}
```

<span data-ttu-id="3b302-158">[https://hl7.org/fhir/stu3/patient.html](https://hl7.org/fhir/stu3/patient.html)有关此字段集的其他详细信息，请参阅。</span><span class="sxs-lookup"><span data-stu-id="3b302-158">See [https://hl7.org/fhir/stu3/patient.html](https://hl7.org/fhir/stu3/patient.html) for other details on this field set.</span></span>

## <a name="observation"></a><span data-ttu-id="3b302-159">知识产权</span><span class="sxs-lookup"><span data-stu-id="3b302-159">Observation</span></span>

<span data-ttu-id="3b302-160">以下是最少的必填字段，它们是 [Argonaut Vital-Signs 个人资料](https://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-vitalsigns.html)的子集。</span><span class="sxs-lookup"><span data-stu-id="3b302-160">These are the minimum required fields, which are a subset of the [Argonaut Vital-Signs profile](https://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-vitalsigns.html).</span></span>

 - <span data-ttu-id="3b302-161">有效 (日期时间或期间) </span><span class="sxs-lookup"><span data-stu-id="3b302-161">Effective (date time or period)</span></span>
 - <span data-ttu-id="3b302-162">编码代码</span><span class="sxs-lookup"><span data-stu-id="3b302-162">Code.Coding.Code</span></span>
 - <span data-ttu-id="3b302-163">ValueQuantity 值</span><span class="sxs-lookup"><span data-stu-id="3b302-163">ValueQuantity.Value</span></span>

<span data-ttu-id="3b302-164">除了 Argonaut 字段外，还可以为患者应用提供出色的用户体验，还可以读取以下字段：</span><span class="sxs-lookup"><span data-stu-id="3b302-164">In addition to the Argonaut fields, for a great user experience the Patients app can also read the following fields:</span></span>

 - <span data-ttu-id="3b302-165">代码编码。显示</span><span class="sxs-lookup"><span data-stu-id="3b302-165">Code.Coding.Display</span></span>
 - <span data-ttu-id="3b302-166">ValueQuantity 单位</span><span class="sxs-lookup"><span data-stu-id="3b302-166">ValueQuantity.Unit</span></span>

<span data-ttu-id="3b302-167">资源搜索使用 GET 方法和以下参数：</span><span class="sxs-lookup"><span data-stu-id="3b302-167">A resource search uses the GET method and the following parameters:</span></span>

 - <span data-ttu-id="3b302-168">患者 =\<patient id></span><span class="sxs-lookup"><span data-stu-id="3b302-168">patient=\<patient id></span></span>
 - <span data-ttu-id="3b302-169">_sort =-日期</span><span class="sxs-lookup"><span data-stu-id="3b302-169">_sort=-date</span></span>
 - <span data-ttu-id="3b302-170">类别 (我们将查询 "category = 重要标志" ) 以检索关键签名列表。</span><span class="sxs-lookup"><span data-stu-id="3b302-170">category (we will query for "category=vital-signs") to retrieve the list of vital signs.</span></span>

<span data-ttu-id="3b302-171">请参阅此通话示例：</span><span class="sxs-lookup"><span data-stu-id="3b302-171">Refer to this example of the call:</span></span>

```
Request:
GET <fhir-server>/Observation?patient=<patient-id>&category=vital-signs

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
        "category": [
          {
            "coding": [
              {
                "system": "https://hl7.org/fhir/observation-category",
                "code": "vital-signs"
              }
            ],
          }
        ],
        "code": {
          "coding": [
            {
              "system": "http://loinc.org",
              "code": "8867-4",
              "display": "heart_rate"
            }
          ]
        },
        "effectiveDateTime": "2009-04-08T00:00:00-06:00",
        "valueQuantity": {
          "value": 72.0,
          "unit": "{beats}/min",
          "system": "http://unitsofmeasure.org",
        }
      }
    },
    .
    .
    .
  ]
}
```

<span data-ttu-id="3b302-172">[https://www.hl7.org/fhir/stu3/observation.html](https://www.hl7.org/fhir/stu3/observation.html)有关此字段集的其他详细信息，请参阅。</span><span class="sxs-lookup"><span data-stu-id="3b302-172">See [https://www.hl7.org/fhir/stu3/observation.html](https://www.hl7.org/fhir/stu3/observation.html) for other details on this field set.</span></span>

## <a name="condition"></a><span data-ttu-id="3b302-173">条件</span><span class="sxs-lookup"><span data-stu-id="3b302-173">Condition</span></span>

<span data-ttu-id="3b302-174">下面是 [Argonaut 条件配置文件](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-condition.html)子集的最少必填字段。</span><span class="sxs-lookup"><span data-stu-id="3b302-174">Here's the minimum required fields, which are a subset of the [Argonaut condition profile](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-condition.html).</span></span>

 - <span data-ttu-id="3b302-175">代码。编码 [0]。画面</span><span class="sxs-lookup"><span data-stu-id="3b302-175">Code.Coding[0].Display</span></span>

<span data-ttu-id="3b302-176">除了 Argonaut 字段外，还可以为患者应用提供出色的用户体验，还可以读取以下字段：</span><span class="sxs-lookup"><span data-stu-id="3b302-176">In addition to the Argonaut fields, for a great user experience the Patients app can also read the following fields:</span></span>

 - <span data-ttu-id="3b302-177">AssertedDate</span><span class="sxs-lookup"><span data-stu-id="3b302-177">AssertedDate</span></span>
 - <span data-ttu-id="3b302-178">严重性</span><span class="sxs-lookup"><span data-stu-id="3b302-178">Severity</span></span>

<span data-ttu-id="3b302-179">资源搜索使用 GET 方法和以下参数：</span><span class="sxs-lookup"><span data-stu-id="3b302-179">A resource search uses the GET method and the following parameters:</span></span>

 - <span data-ttu-id="3b302-180">患者 =\<patient id></span><span class="sxs-lookup"><span data-stu-id="3b302-180">patient=\<patient id></span></span>
 - <span data-ttu-id="3b302-181">_count =\<max results></span><span class="sxs-lookup"><span data-stu-id="3b302-181">_count=\<max results></span></span>

<span data-ttu-id="3b302-182">请参阅下面的此呼叫示例：</span><span class="sxs-lookup"><span data-stu-id="3b302-182">See the following example of this call:</span></span>

```
Request:
GET <fhir-server>/Condition?patient=<patient-id>&_count=10

Response:
{
  "resourceType": "Bundle",
  "id": "<bundle-id>",
  "type": "searchset",
  "total": 2,
  "entry": [
    {
      "resource": {
        "resourceType": "Condition",
        "id": "<resource-id>",
        "code": {
          "coding": [
            {
              "system": "http://snomed.info/sct",
              "code": "185903001",
              "display": "Needs influenza immunization",
            }
          ]
        },
        "severity": {
          "coding": [
            {
              "system": "http://snomed.info/sct",
              "code": "24484000",
              "display": "Severe"
            }
          ]
        },
        "assertedDate": "2018-04-04"
      }
    },
    .
    .
    .
  ]
}
```

<span data-ttu-id="3b302-183">[https://hl7.org/fhir/stu3/condition.html](https://hl7.org/fhir/stu3/condition.html)有关此字段集的其他详细信息，请参阅。</span><span class="sxs-lookup"><span data-stu-id="3b302-183">See [https://hl7.org/fhir/stu3/condition.html](https://hl7.org/fhir/stu3/condition.html) for other details on this field set.</span></span>

## <a name="encounter"></a><span data-ttu-id="3b302-184">产生</span><span class="sxs-lookup"><span data-stu-id="3b302-184">Encounter</span></span>

<span data-ttu-id="3b302-185">以下是最少必填字段，这些字段是 [US Core](https://hl7.org/fhir/us/core/2018Jan/StructureDefinition-us-core-encounter.html) "必须有" 字段) 的一个子集。</span><span class="sxs-lookup"><span data-stu-id="3b302-185">These are the minimum required fields, which are a subset of the [US Core Encounter profile](https://hl7.org/fhir/us/core/2018Jan/StructureDefinition-us-core-encounter.html) "must have" fields).</span></span>

 - <span data-ttu-id="3b302-186">状态栏</span><span class="sxs-lookup"><span data-stu-id="3b302-186">Status</span></span>
 - <span data-ttu-id="3b302-187">键入 [0]。编码 [0]。画面</span><span class="sxs-lookup"><span data-stu-id="3b302-187">Type[0].Coding[0].Display</span></span>

<span data-ttu-id="3b302-188">此外，美国核心的以下字段会遇到配置文件的 "必须支持" 字段：</span><span class="sxs-lookup"><span data-stu-id="3b302-188">In addition, the following fields from US Core Encounter profile's "must support" fields:</span></span>

 - <span data-ttu-id="3b302-189">句号。开始</span><span class="sxs-lookup"><span data-stu-id="3b302-189">Period.Start</span></span>
 - <span data-ttu-id="3b302-190">位置 [0]。位置。显示</span><span class="sxs-lookup"><span data-stu-id="3b302-190">Location[0].Location.Display</span></span>

<span data-ttu-id="3b302-191">资源搜索使用 GET 方法和以下参数：</span><span class="sxs-lookup"><span data-stu-id="3b302-191">A resource search uses the GET method and the following parameters:</span></span>

 - <span data-ttu-id="3b302-192">患者 =\<patient id></span><span class="sxs-lookup"><span data-stu-id="3b302-192">patient=\<patient id></span></span>
 - <span data-ttu-id="3b302-193">_sort： desc =\<field ex. date></span><span class="sxs-lookup"><span data-stu-id="3b302-193">_sort:desc=\<field ex. date></span></span>
 - <span data-ttu-id="3b302-194">_count =\<max results></span><span class="sxs-lookup"><span data-stu-id="3b302-194">_count=\<max results></span></span>

<span data-ttu-id="3b302-195">目标是能够检索患者的最后一个已知位置。</span><span class="sxs-lookup"><span data-stu-id="3b302-195">The goal is to be able to retrieve the patient's last known location.</span></span> <span data-ttu-id="3b302-196">每个遇到的都引用一个位置资源。</span><span class="sxs-lookup"><span data-stu-id="3b302-196">Each encounter references a location resource.</span></span> <span data-ttu-id="3b302-197">该引用还应包含位置的显示字段。</span><span class="sxs-lookup"><span data-stu-id="3b302-197">The reference shall also include the location's display field.</span></span>

<span data-ttu-id="3b302-198">[https://hl7.org/fhir/stu3/encounter.html](https://hl7.org/fhir/stu3/encounter.html)有关此字段集的其他详细信息，请参阅。</span><span class="sxs-lookup"><span data-stu-id="3b302-198">See [https://hl7.org/fhir/stu3/encounter.html](https://hl7.org/fhir/stu3/encounter.html) for other details on this field set.</span></span>

## <a name="allergyintolerance"></a><span data-ttu-id="3b302-199">AllergyIntolerance</span><span class="sxs-lookup"><span data-stu-id="3b302-199">AllergyIntolerance</span></span>

<span data-ttu-id="3b302-200">以下是最少的必填字段，它们是 [Argonaut AllergyIntolerance](https://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-allergyintolerance.html) 配置文件的子集：</span><span class="sxs-lookup"><span data-stu-id="3b302-200">These are the minimum required fields, which are a subset of the [Argonaut AllergyIntolerance](https://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-allergyintolerance.html) profile:</span></span>

 - <span data-ttu-id="3b302-201">代码。文本</span><span class="sxs-lookup"><span data-stu-id="3b302-201">Code.Text</span></span>
 - <span data-ttu-id="3b302-202">代码。编码 [0]。画面</span><span class="sxs-lookup"><span data-stu-id="3b302-202">Code.Coding[0].Display</span></span>
 - <span data-ttu-id="3b302-203">ClinicalStatus/VerificationStatus (我们同时阅读) </span><span class="sxs-lookup"><span data-stu-id="3b302-203">ClinicalStatus/VerificationStatus (we read both)</span></span>

<span data-ttu-id="3b302-204">除了 Argonaut 字段外，还可为患者应用提供出色的用户体验，还可以读取以下字段：</span><span class="sxs-lookup"><span data-stu-id="3b302-204">In addition to the Argonaut fields, for a great user experience the Patients app can also read the following field:</span></span>

 - <span data-ttu-id="3b302-205">AssertedDate</span><span class="sxs-lookup"><span data-stu-id="3b302-205">AssertedDate</span></span>
 - <span data-ttu-id="3b302-206">备注。文本</span><span class="sxs-lookup"><span data-stu-id="3b302-206">Note.Text</span></span>
 - <span data-ttu-id="3b302-207">被动</span><span class="sxs-lookup"><span data-stu-id="3b302-207">Reaction</span></span>
    - <span data-ttu-id="3b302-208"> (一个编码元素) 的物质</span><span class="sxs-lookup"><span data-stu-id="3b302-208">Substance (one coding element)</span></span>
    - <span data-ttu-id="3b302-209"> (一个编码元素的表现形式) </span><span class="sxs-lookup"><span data-stu-id="3b302-209">Manifestation (one coding element)</span></span>

<span data-ttu-id="3b302-210">资源搜索使用 GET 方法和以下参数：</span><span class="sxs-lookup"><span data-stu-id="3b302-210">A resource search uses the GET method and the following parameters:</span></span>

 - <span data-ttu-id="3b302-211">患者 =  \<patient id></span><span class="sxs-lookup"><span data-stu-id="3b302-211">Patient =  \<patient id></span></span>

<span data-ttu-id="3b302-212">请参阅下面的通话示例：</span><span class="sxs-lookup"><span data-stu-id="3b302-212">See the following example of the call:</span></span> 

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
        "clinicalStatus": "active",
        "verificationStatus": "confirmed",
        "code": {
          "coding": [
            {
              "system": "http://rxnav.nlm.nih.gov/REST/Ndfrt",
              "code": "N0000175503",
              "display": "sulfonamide antibacterial",
            }
          ],
          "text": "sulfonamide antibacterial"
        },
        "assertedDate": "2018-01-01T00:00:00-07:00",
        "reaction": [
          {
            "manifestation": [
              {
                "coding": [
                  {
                    "system": "http://snomed.info/sct",
                    "code": "271807003",
                    "display": "skin rash",
                  }
                ],
                "text": "skin rash"
              }
            ],
          }
        ]
      }
    }
  ]
}
```

<span data-ttu-id="3b302-213">[https://hl7.org/fhir/stu3/allergyintolerance.html](https://hl7.org/fhir/stu3/allergyintolerance.html)有关此字段集的其他详细信息，请参阅。</span><span class="sxs-lookup"><span data-stu-id="3b302-213">See [https://hl7.org/fhir/stu3/allergyintolerance.html](https://hl7.org/fhir/stu3/allergyintolerance.html) for other details on this field set.</span></span>

## <a name="medication-request"></a><span data-ttu-id="3b302-214">药物请求</span><span class="sxs-lookup"><span data-stu-id="3b302-214">Medication Request</span></span>

<span data-ttu-id="3b302-215">以下是最少的必填字段，这些字段是 [美国核心药物请求档案](http://www.hl7.org/fhir/us/core/StructureDefinition-us-core-medicationrequest.html)的子集：</span><span class="sxs-lookup"><span data-stu-id="3b302-215">These are the minimum required fields, which are a subset of the [US Core Medication Request profile](http://www.hl7.org/fhir/us/core/StructureDefinition-us-core-medicationrequest.html):</span></span>

 - <span data-ttu-id="3b302-216">药物。如果引用) ，则显示 (</span><span class="sxs-lookup"><span data-stu-id="3b302-216">Medication.Display (if Reference)</span></span>
 - <span data-ttu-id="3b302-217">如果 CodableConcept) ，则为文本 (</span><span class="sxs-lookup"><span data-stu-id="3b302-217">Medication.Text (if CodableConcept)</span></span>
 - <span data-ttu-id="3b302-218">AuthoredOn</span><span class="sxs-lookup"><span data-stu-id="3b302-218">AuthoredOn</span></span>
 - <span data-ttu-id="3b302-219">请求者代理。显示</span><span class="sxs-lookup"><span data-stu-id="3b302-219">Requester.Agent.Display</span></span>

<span data-ttu-id="3b302-220">除了 US 核心字段外，还可为患者应用提供出色的用户体验，还可以读取以下字段：</span><span class="sxs-lookup"><span data-stu-id="3b302-220">In addition to the US Core fields, for a great user experience the Patients app can also read the following fields:</span></span>

 - <span data-ttu-id="3b302-221">DosageInstruction[..].文本</span><span class="sxs-lookup"><span data-stu-id="3b302-221">DosageInstruction[..].Text</span></span>
 - <span data-ttu-id="3b302-222">文本</span><span class="sxs-lookup"><span data-stu-id="3b302-222">Text</span></span>

<span data-ttu-id="3b302-223">资源搜索使用 GET 方法和以下参数：</span><span class="sxs-lookup"><span data-stu-id="3b302-223">A resource search uses the GET method and the following parameters:</span></span>

 - <span data-ttu-id="3b302-224">患者 =\<patient id></span><span class="sxs-lookup"><span data-stu-id="3b302-224">patient=\<patient id></span></span>
 - <span data-ttu-id="3b302-225">_count =\<max results></span><span class="sxs-lookup"><span data-stu-id="3b302-225">_count=\<max results></span></span>

<span data-ttu-id="3b302-226">[https://www.hl7.org/fhir/medicationrequest.html](https://www.hl7.org/fhir/medicationrequest.html)有关此字段集的其他详细信息，请参阅。</span><span class="sxs-lookup"><span data-stu-id="3b302-226">See [https://www.hl7.org/fhir/medicationrequest.html](https://www.hl7.org/fhir/medicationrequest.html) for other details on this field set.</span></span>

## <a name="coverage"></a><span data-ttu-id="3b302-227">内</span><span class="sxs-lookup"><span data-stu-id="3b302-227">Coverage</span></span>

<span data-ttu-id="3b302-228">以下是 "最少必填字段"，不包含在美国 Core 或 Argonaut 配置文件中：</span><span class="sxs-lookup"><span data-stu-id="3b302-228">These are the minimum required fields, not covered by either US Core or Argonaut profiles:</span></span>

 - <span data-ttu-id="3b302-229">组合，至少一个元素具有</span><span class="sxs-lookup"><span data-stu-id="3b302-229">Grouping, at least one element with</span></span>
    - <span data-ttu-id="3b302-230">GroupDisplay</span><span class="sxs-lookup"><span data-stu-id="3b302-230">GroupDisplay</span></span>
    - <span data-ttu-id="3b302-231">PlanDisplay</span><span class="sxs-lookup"><span data-stu-id="3b302-231">PlanDisplay</span></span>
 - <span data-ttu-id="3b302-232">试用期</span><span class="sxs-lookup"><span data-stu-id="3b302-232">Period</span></span>
 - <span data-ttu-id="3b302-233">SubscriberId</span><span class="sxs-lookup"><span data-stu-id="3b302-233">SubscriberId</span></span>

<span data-ttu-id="3b302-234">资源搜索使用 GET 方法和以下参数：</span><span class="sxs-lookup"><span data-stu-id="3b302-234">A resource search uses the GET method and the following parameters:</span></span>

 - <span data-ttu-id="3b302-235">患者 = \<patient id></span><span class="sxs-lookup"><span data-stu-id="3b302-235">Patient = \<patient id></span></span>

<span data-ttu-id="3b302-236">[https://hl7.org/fhir/stu3/coverage.html](https://www.hl7.org/fhir/medicationrequest.html)有关此字段集的其他详细信息，请参阅。</span><span class="sxs-lookup"><span data-stu-id="3b302-236">See [https://hl7.org/fhir/stu3/coverage.html](https://www.hl7.org/fhir/medicationrequest.html) for other details on this field set.</span></span>
