---
title: 患者应用和 EHR 集成 STU3 接口
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
description: 了解如何将电子健康记录集成到Microsoft Teams应用和 STU3 接口规范中。
ms.custom: seo-marvel-apr2020
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: 4e20619badb2509d0a90f396563a98796e718e2f
ms.sourcegitcommit: beaaee10019f4eda746f348888a4a3c2aaa6f196
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2020
ms.locfileid: "48803490"
---
# <a name="stu3-interface-specification"></a><span data-ttu-id="8a084-103">STU3 接口规范</span><span class="sxs-lookup"><span data-stu-id="8a084-103">STU3 interface specification</span></span>

> [!NOTE]
> <span data-ttu-id="8a084-104">从 2020 年 10 月 30 日起，"患者"应用已停用，并替换为 Teams [列表](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) 应用。</span><span class="sxs-lookup"><span data-stu-id="8a084-104">Effective October 30, 2020, the Patients app has been retired and replaced by the [Lists app](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) in Teams.</span></span> <span data-ttu-id="8a084-105">患者应用数据存储在支持团队的 Office 365 组的组邮箱中。</span><span class="sxs-lookup"><span data-stu-id="8a084-105">Patients app data is stored in the group mailbox of the Office 365 group that backs the team.</span></span> <span data-ttu-id="8a084-106">与该患者应用关联的所有数据将保留在该组，但无法再通过用户界面访问。</span><span class="sxs-lookup"><span data-stu-id="8a084-106">All data associated with the Patients app is retained in this group but can no longer be accessed through the user interface.</span></span> <span data-ttu-id="8a084-107">用户可通过"列表"应用或 [重新创建](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db)。</span><span class="sxs-lookup"><span data-stu-id="8a084-107">Users can re-create their lists using the [Lists app](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db).</span></span>
>
><span data-ttu-id="8a084-108">借助列表，医疗保健组织中的护理团队可针对各种方案创建患者列表，提供圆形和内联团队会议、常规患者监视等。</span><span class="sxs-lookup"><span data-stu-id="8a084-108">With Lists, care teams in your healthcare organization can create patient lists for scenarios ranging from rounds and interdisciplinary team meetings to general patient monitoring.</span></span> <span data-ttu-id="8a084-109">查看列表的"患者"模板以开始使用。</span><span class="sxs-lookup"><span data-stu-id="8a084-109">Check out the Patients template in Lists to get started.</span></span> <span data-ttu-id="8a084-110">若要深入了解如何在组织中管理列表应用，请参阅" [列表应用管理](../../manage-lists-app.md)。</span><span class="sxs-lookup"><span data-stu-id="8a084-110">To learn more about how to manage the Lists app in your organization, see [Manage the Lists app](../../manage-lists-app.md).</span></span>

<span data-ttu-id="8a084-111">设置或重新配置 FHIR 服务器以使用Microsoft Teams患者应用需要了解应用需要访问哪些数据。</span><span class="sxs-lookup"><span data-stu-id="8a084-111">Setting up or reconfiguring an FHIR server to work with the Microsoft Teams Patients app requires understanding what data the app needs to access.</span></span> <span data-ttu-id="8a084-112">FHIR 服务器必须使用捆绑包支持以下资源的 POST 请求：</span><span class="sxs-lookup"><span data-stu-id="8a084-112">The FHIR server must support POST requests using bundles for the following resources:</span></span>

- [<span data-ttu-id="8a084-113">Patient</span><span class="sxs-lookup"><span data-stu-id="8a084-113">Patient</span></span>](#patient)
- [<span data-ttu-id="8a084-114">观察</span><span class="sxs-lookup"><span data-stu-id="8a084-114">Observation</span></span>](#observation)
- [<span data-ttu-id="8a084-115">条件</span><span class="sxs-lookup"><span data-stu-id="8a084-115">Condition</span></span>](#condition)
- [<span data-ttu-id="8a084-116">Encounter</span><span class="sxs-lookup"><span data-stu-id="8a084-116">Encounter</span></span>](#encounter)
- [<span data-ttu-id="8a084-117">仇恨者</span><span class="sxs-lookup"><span data-stu-id="8a084-117">Allergy Intolerance</span></span>](#allergyintolerance)
- [<span data-ttu-id="8a084-118">覆盖范围</span><span class="sxs-lookup"><span data-stu-id="8a084-118">Coverage</span></span>](#coverage)
- <span data-ttu-id="8a084-119">[药物 (](#medication-request) 替代 PatientsApp) 的 DSTU2 版本中的 PatientOrder</span><span class="sxs-lookup"><span data-stu-id="8a084-119">[Medication Statement](#medication-request) (replaces the MedicationOrder in the DSTU2 version of the PatientsApp)</span></span>
- <span data-ttu-id="8a084-120">位置 (此资源所需信息的位置可以包含在"遇到") </span><span class="sxs-lookup"><span data-stu-id="8a084-120">Location (the information needed from this resource can be included in Encounter)</span></span>

> [!NOTE]
> <span data-ttu-id="8a084-121">患者资源是唯一必需的资源 (，如果没有它，应用将完全不加载) ;但是，建议合作伙伴根据下面提供的规范实施对上述所有资源的支持，以获得最佳患者应用最终用户Microsoft Teams体验。</span><span class="sxs-lookup"><span data-stu-id="8a084-121">The Patient resource is the only mandatory resource (without which the app will not load at all); However, it is recommended that the Partner implement support for all the above mentioned resources per specifications provided below for the best end-user experience with the Microsoft Teams Patients App.</span></span>

<span data-ttu-id="8a084-122">来自 Microsoft Teams Patients 应用的查询针对多个资源应发布一个捆绑包 (BATCH) FHIR 服务器 URL 的请求。</span><span class="sxs-lookup"><span data-stu-id="8a084-122">Queries from the Microsoft Teams Patients app for more than one resource shall post a bundle (BATCH) of requests to the FHIR server's URL.</span></span> <span data-ttu-id="8a084-123">服务器应处理每个请求并返回每个请求匹配的资源捆绑包。</span><span class="sxs-lookup"><span data-stu-id="8a084-123">The server shall process each request and return a bundle of the resources matched by each request.</span></span> <span data-ttu-id="8a084-124">有关详细信息和示例，请参阅 [https://www.hl7.org/fhir/STU3/http.html#transaction](https://www.hl7.org/fhir/STU3/http.html#transaction) 。</span><span class="sxs-lookup"><span data-stu-id="8a084-124">For more information and examples, see [https://www.hl7.org/fhir/STU3/http.html#transaction](https://www.hl7.org/fhir/STU3/http.html#transaction).</span></span>

## <a name="capability-statement"></a><span data-ttu-id="8a084-125">功能语句</span><span class="sxs-lookup"><span data-stu-id="8a084-125">Capability Statement</span></span>

<span data-ttu-id="8a084-126">这些是最小必填字段：</span><span class="sxs-lookup"><span data-stu-id="8a084-126">These are the minimum required fields:</span></span>

 - <span data-ttu-id="8a084-127">REST</span><span class="sxs-lookup"><span data-stu-id="8a084-127">REST</span></span>

    - <span data-ttu-id="8a084-128">模式</span><span class="sxs-lookup"><span data-stu-id="8a084-128">Mode</span></span>
    - <span data-ttu-id="8a084-129">交互</span><span class="sxs-lookup"><span data-stu-id="8a084-129">Interaction</span></span>
    - <span data-ttu-id="8a084-130">资源：类型</span><span class="sxs-lookup"><span data-stu-id="8a084-130">Resource: Type</span></span>
    - <span data-ttu-id="8a084-131">安全性 [：OAuth URI 扩展](https://hl7.org/fhir/extension-oauth-uris.html)</span><span class="sxs-lookup"><span data-stu-id="8a084-131">Security: [Extension for OAuth URIs](https://hl7.org/fhir/extension-oauth-uris.html)</span></span>
    
 - <span data-ttu-id="8a084-132">FhirVersion (我们的代码需要此代码来了解应该透视到哪个版本) </span><span class="sxs-lookup"><span data-stu-id="8a084-132">FhirVersion (Our code requires this to understand which version we should pivot to.)</span></span>

<span data-ttu-id="8a084-133">有关 [https://www.hl7.org/fhir/stu3/capabilitystatement.html](https://www.hl7.org/fhir/stu3/capabilitystatement.html) 此字段集的其他详细信息，请参阅 。</span><span class="sxs-lookup"><span data-stu-id="8a084-133">See [https://www.hl7.org/fhir/stu3/capabilitystatement.html](https://www.hl7.org/fhir/stu3/capabilitystatement.html) for other details on this field set.</span></span>

## <a name="patient"></a><span data-ttu-id="8a084-134">Patient</span><span class="sxs-lookup"><span data-stu-id="8a084-134">Patient</span></span>

<span data-ttu-id="8a084-135">下面是最小必填字段，这些字段是 Argonaut 患者配置文件字段的子集：</span><span class="sxs-lookup"><span data-stu-id="8a084-135">Here are the minimum required fields, which are a subset of the Argonaut patient profile fields:</span></span>

 - <span data-ttu-id="8a084-136">Name.Given</span><span class="sxs-lookup"><span data-stu-id="8a084-136">Name.Given</span></span>
 - <span data-ttu-id="8a084-137">Name.Family</span><span class="sxs-lookup"><span data-stu-id="8a084-137">Name.Family</span></span>
 - <span data-ttu-id="8a084-138">性别</span><span class="sxs-lookup"><span data-stu-id="8a084-138">Gender</span></span>
 - <span data-ttu-id="8a084-139">BirthDate</span><span class="sxs-lookup"><span data-stu-id="8a084-139">BirthDate</span></span>
 - <span data-ttu-id="8a084-140">MRN (标识符) </span><span class="sxs-lookup"><span data-stu-id="8a084-140">MRN (Identifier)</span></span>

<span data-ttu-id="8a084-141">除了 [Argonaut](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-patient.html)字段之外，为了获得出色的用户体验，Patients 应用还可以读取以下字段：</span><span class="sxs-lookup"><span data-stu-id="8a084-141">In addition to the [Argonaut fields](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-patient.html), for a great user experience the Patients app can also read the following fields:</span></span>

 - <span data-ttu-id="8a084-142">Name.Use</span><span class="sxs-lookup"><span data-stu-id="8a084-142">Name.Use</span></span>
 - <span data-ttu-id="8a084-143">Name.Prefix</span><span class="sxs-lookup"><span data-stu-id="8a084-143">Name.Prefix</span></span>
 - <span data-ttu-id="8a084-144">[GeneralPractitioner] - GeneralPractitioner 引用应仅包含在"患者" (显示字段中) </span><span class="sxs-lookup"><span data-stu-id="8a084-144">[GeneralPractitioner] - The GeneralPractitioner reference should be included in the Patient resource (display field only)</span></span>

<span data-ttu-id="8a084-145">资源搜索使用 /Patient/_search 的 POST 方法以及以下参数：</span><span class="sxs-lookup"><span data-stu-id="8a084-145">A resource search uses the POST method at /Patient/_search and the following parameters:</span></span>

 - <span data-ttu-id="8a084-146">id</span><span class="sxs-lookup"><span data-stu-id="8a084-146">id</span></span>
 - <span data-ttu-id="8a084-147">family= (搜索其家庭名称包含其值的所有) </span><span class="sxs-lookup"><span data-stu-id="8a084-147">family=(searches for all patients whose family name contains the value)</span></span>
 - <span data-ttu-id="8a084-148">given=\<substring></span><span class="sxs-lookup"><span data-stu-id="8a084-148">given=\<substring></span></span>
 - <span data-ttu-id="8a084-149">birthdate= (完全匹配) </span><span class="sxs-lookup"><span data-stu-id="8a084-149">birthdate=(exact match)</span></span>
 - <span data-ttu-id="8a084-150">gender= (值是管理性别关系之一) </span><span class="sxs-lookup"><span data-stu-id="8a084-150">gender=(values being one of the administrative-gender)</span></span>
 - <span data-ttu-id="8a084-151">\_count (应返回的结果的最大) </span><span class="sxs-lookup"><span data-stu-id="8a084-151">\_count (maximum number of results that should be returned)</span></span> <br> <span data-ttu-id="8a084-152">响应应包含搜索结果返回的记录总数，并且 PatientsApp 将用来限制返回 \_ 的记录数。</span><span class="sxs-lookup"><span data-stu-id="8a084-152">The response should contain the total count of records returned as a result of the search and \_count will be used by the PatientsApp to limit the number of records returned.</span></span>
 - <span data-ttu-id="8a084-153">identifier=\<mrn></span><span class="sxs-lookup"><span data-stu-id="8a084-153">identifier=\<mrn></span></span>

<span data-ttu-id="8a084-154">目标是能够按以下条件搜索和筛选患者：</span><span class="sxs-lookup"><span data-stu-id="8a084-154">The goal is to be able to search and filter for a patient by the following:</span></span>

- <span data-ttu-id="8a084-155">ID：这是 FHIR 中每个资源具有的资源 ID。</span><span class="sxs-lookup"><span data-stu-id="8a084-155">ID: This is the resource ID that every resource in FHIR has.</span></span>
- <span data-ttu-id="8a084-156">MRN：这是患者的实际标识符，该患者是医疗人员会知道的信息。</span><span class="sxs-lookup"><span data-stu-id="8a084-156">MRN: This is the actual identifier for the patient that clinical staff would know.</span></span> <span data-ttu-id="8a084-157">我们知道，此 MRN 基于 FHIR 中标识符资源内的标识符类型。</span><span class="sxs-lookup"><span data-stu-id="8a084-157">We understand this MRN is based on the type of identifier inside the identifier resource in FHIR.</span></span>
- <span data-ttu-id="8a084-158">名称</span><span class="sxs-lookup"><span data-stu-id="8a084-158">Name</span></span>
- <span data-ttu-id="8a084-159">Birthdate</span><span class="sxs-lookup"><span data-stu-id="8a084-159">Birthdate</span></span>

<span data-ttu-id="8a084-160">请参阅以下调用示例：</span><span class="sxs-lookup"><span data-stu-id="8a084-160">See the following example of the call:</span></span>

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

<span data-ttu-id="8a084-161">有关 [https://hl7.org/fhir/stu3/patient.html](https://hl7.org/fhir/stu3/patient.html) 此字段集的其他详细信息，请参阅 。</span><span class="sxs-lookup"><span data-stu-id="8a084-161">See [https://hl7.org/fhir/stu3/patient.html](https://hl7.org/fhir/stu3/patient.html) for other details on this field set.</span></span>

## <a name="observation"></a><span data-ttu-id="8a084-162">观察</span><span class="sxs-lookup"><span data-stu-id="8a084-162">Observation</span></span>

<span data-ttu-id="8a084-163">这些是最小必填字段，这些字段是 [Argonaut Vital-Signs配置文件 的子集](https://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-vitalsigns.html)。</span><span class="sxs-lookup"><span data-stu-id="8a084-163">These are the minimum required fields, which are a subset of the [Argonaut Vital-Signs profile](https://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-vitalsigns.html).</span></span>

 - <span data-ttu-id="8a084-164">有效 (日期时间或) </span><span class="sxs-lookup"><span data-stu-id="8a084-164">Effective (date time or period)</span></span>
 - <span data-ttu-id="8a084-165">Code.Code.Code</span><span class="sxs-lookup"><span data-stu-id="8a084-165">Code.Coding.Code</span></span>
 - <span data-ttu-id="8a084-166">ValueQuantity.Value</span><span class="sxs-lookup"><span data-stu-id="8a084-166">ValueQuantity.Value</span></span>

<span data-ttu-id="8a084-167">除了 Argonaut 字段之外，为了获得出色的用户体验，Patients 应用还可以读取以下字段：</span><span class="sxs-lookup"><span data-stu-id="8a084-167">In addition to the Argonaut fields, for a great user experience the Patients app can also read the following fields:</span></span>

 - <span data-ttu-id="8a084-168">Code.Code.Display</span><span class="sxs-lookup"><span data-stu-id="8a084-168">Code.Coding.Display</span></span>
 - <span data-ttu-id="8a084-169">ValueQuantity.Unit</span><span class="sxs-lookup"><span data-stu-id="8a084-169">ValueQuantity.Unit</span></span>

<span data-ttu-id="8a084-170">资源搜索使用 GET 方法和以下参数：</span><span class="sxs-lookup"><span data-stu-id="8a084-170">A resource search uses the GET method and the following parameters:</span></span>

 - <span data-ttu-id="8a084-171">patient=\<patient id></span><span class="sxs-lookup"><span data-stu-id="8a084-171">patient=\<patient id></span></span>
 - <span data-ttu-id="8a084-172">_sort=-date</span><span class="sxs-lookup"><span data-stu-id="8a084-172">_sort=-date</span></span>
 - <span data-ttu-id="8a084-173">类别 (查询"category=vital-signs") 检索重要符号列表。</span><span class="sxs-lookup"><span data-stu-id="8a084-173">category (we will query for "category=vital-signs") to retrieve the list of vital signs.</span></span>

<span data-ttu-id="8a084-174">请参考以下调用示例：</span><span class="sxs-lookup"><span data-stu-id="8a084-174">Refer to this example of the call:</span></span>

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

<span data-ttu-id="8a084-175">有关 [https://www.hl7.org/fhir/stu3/observation.html](https://www.hl7.org/fhir/stu3/observation.html) 此字段集的其他详细信息，请参阅 。</span><span class="sxs-lookup"><span data-stu-id="8a084-175">See [https://www.hl7.org/fhir/stu3/observation.html](https://www.hl7.org/fhir/stu3/observation.html) for other details on this field set.</span></span>

## <a name="condition"></a><span data-ttu-id="8a084-176">条件</span><span class="sxs-lookup"><span data-stu-id="8a084-176">Condition</span></span>

<span data-ttu-id="8a084-177">下面是最小必填字段，这些字段是 [Argonaut 条件配置文件 的子集](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-condition.html)。</span><span class="sxs-lookup"><span data-stu-id="8a084-177">Here's the minimum required fields, which are a subset of the [Argonaut condition profile](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-condition.html).</span></span>

 - <span data-ttu-id="8a084-178">Code.Code[0]。显示</span><span class="sxs-lookup"><span data-stu-id="8a084-178">Code.Coding[0].Display</span></span>

<span data-ttu-id="8a084-179">除了 Argonaut 字段之外，为了获得出色的用户体验，Patients 应用还可以读取以下字段：</span><span class="sxs-lookup"><span data-stu-id="8a084-179">In addition to the Argonaut fields, for a great user experience the Patients app can also read the following fields:</span></span>

 - <span data-ttu-id="8a084-180">AssertedDate</span><span class="sxs-lookup"><span data-stu-id="8a084-180">AssertedDate</span></span>
 - <span data-ttu-id="8a084-181">严重性</span><span class="sxs-lookup"><span data-stu-id="8a084-181">Severity</span></span>

<span data-ttu-id="8a084-182">资源搜索使用 GET 方法和以下参数：</span><span class="sxs-lookup"><span data-stu-id="8a084-182">A resource search uses the GET method and the following parameters:</span></span>

 - <span data-ttu-id="8a084-183">patient=\<patient id></span><span class="sxs-lookup"><span data-stu-id="8a084-183">patient=\<patient id></span></span>
 - <span data-ttu-id="8a084-184">_count=\<max results></span><span class="sxs-lookup"><span data-stu-id="8a084-184">_count=\<max results></span></span>

<span data-ttu-id="8a084-185">请参阅以下此调用示例：</span><span class="sxs-lookup"><span data-stu-id="8a084-185">See the following example of this call:</span></span>

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

<span data-ttu-id="8a084-186">有关 [https://hl7.org/fhir/stu3/condition.html](https://hl7.org/fhir/stu3/condition.html) 此字段集的其他详细信息，请参阅 。</span><span class="sxs-lookup"><span data-stu-id="8a084-186">See [https://hl7.org/fhir/stu3/condition.html](https://hl7.org/fhir/stu3/condition.html) for other details on this field set.</span></span>

## <a name="encounter"></a><span data-ttu-id="8a084-187">Encounter</span><span class="sxs-lookup"><span data-stu-id="8a084-187">Encounter</span></span>

<span data-ttu-id="8a084-188">这些是最小必填字段，这些字段是" [美国核心](https://hl7.org/fhir/us/core/2018Jan/StructureDefinition-us-core-encounter.html) 遇到"配置文件"必须具有"字段的) 。</span><span class="sxs-lookup"><span data-stu-id="8a084-188">These are the minimum required fields, which are a subset of the [US Core Encounter profile](https://hl7.org/fhir/us/core/2018Jan/StructureDefinition-us-core-encounter.html) "must have" fields).</span></span>

 - <span data-ttu-id="8a084-189">状态</span><span class="sxs-lookup"><span data-stu-id="8a084-189">Status</span></span>
 - <span data-ttu-id="8a084-190">Type[0]。编码[0]。显示</span><span class="sxs-lookup"><span data-stu-id="8a084-190">Type[0].Coding[0].Display</span></span>

<span data-ttu-id="8a084-191">此外，US Core Encounter 配置文件的"必须支持"字段中的以下字段：</span><span class="sxs-lookup"><span data-stu-id="8a084-191">In addition, the following fields from US Core Encounter profile's "must support" fields:</span></span>

 - <span data-ttu-id="8a084-192">Period.Start</span><span class="sxs-lookup"><span data-stu-id="8a084-192">Period.Start</span></span>
 - <span data-ttu-id="8a084-193">Location[0]。Location.Display</span><span class="sxs-lookup"><span data-stu-id="8a084-193">Location[0].Location.Display</span></span>

<span data-ttu-id="8a084-194">资源搜索使用 GET 方法和以下参数：</span><span class="sxs-lookup"><span data-stu-id="8a084-194">A resource search uses the GET method and the following parameters:</span></span>

 - <span data-ttu-id="8a084-195">patient=\<patient id></span><span class="sxs-lookup"><span data-stu-id="8a084-195">patient=\<patient id></span></span>
 - <span data-ttu-id="8a084-196">_sort：desc=\<field ex. date></span><span class="sxs-lookup"><span data-stu-id="8a084-196">_sort:desc=\<field ex. date></span></span>
 - <span data-ttu-id="8a084-197">_count=\<max results></span><span class="sxs-lookup"><span data-stu-id="8a084-197">_count=\<max results></span></span>

<span data-ttu-id="8a084-198">目标是能够检索患者上次已知的位置。</span><span class="sxs-lookup"><span data-stu-id="8a084-198">The goal is to be able to retrieve the patient's last known location.</span></span> <span data-ttu-id="8a084-199">每次遇到都引用一个位置资源。</span><span class="sxs-lookup"><span data-stu-id="8a084-199">Each encounter references a location resource.</span></span> <span data-ttu-id="8a084-200">引用还应包括位置的显示字段。</span><span class="sxs-lookup"><span data-stu-id="8a084-200">The reference shall also include the location's display field.</span></span>

<span data-ttu-id="8a084-201">有关 [https://hl7.org/fhir/stu3/encounter.html](https://hl7.org/fhir/stu3/encounter.html) 此字段集的其他详细信息，请参阅 。</span><span class="sxs-lookup"><span data-stu-id="8a084-201">See [https://hl7.org/fhir/stu3/encounter.html](https://hl7.org/fhir/stu3/encounter.html) for other details on this field set.</span></span>

## <a name="allergyintolerance"></a><span data-ttu-id="8a084-202">管理障碍</span><span class="sxs-lookup"><span data-stu-id="8a084-202">AllergyIntolerance</span></span>

<span data-ttu-id="8a084-203">这些是最小必填字段，这些字段是 [ArgonautAutyIntolerance 配置文件的子集](https://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-allergyintolerance.html) ：</span><span class="sxs-lookup"><span data-stu-id="8a084-203">These are the minimum required fields, which are a subset of the [Argonaut AllergyIntolerance](https://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-allergyintolerance.html) profile:</span></span>

 - <span data-ttu-id="8a084-204">Code.Text</span><span class="sxs-lookup"><span data-stu-id="8a084-204">Code.Text</span></span>
 - <span data-ttu-id="8a084-205">Code.Code[0]。显示</span><span class="sxs-lookup"><span data-stu-id="8a084-205">Code.Coding[0].Display</span></span>
 - <span data-ttu-id="8a084-206">ClinicalStatus/VerificationStatus (读取这两) </span><span class="sxs-lookup"><span data-stu-id="8a084-206">ClinicalStatus/VerificationStatus (we read both)</span></span>

<span data-ttu-id="8a084-207">除了 Argonaut 字段之外，为了获得出色的用户体验，Patients 应用还可以读取以下字段：</span><span class="sxs-lookup"><span data-stu-id="8a084-207">In addition to the Argonaut fields, for a great user experience the Patients app can also read the following field:</span></span>

 - <span data-ttu-id="8a084-208">AssertedDate</span><span class="sxs-lookup"><span data-stu-id="8a084-208">AssertedDate</span></span>
 - <span data-ttu-id="8a084-209">Note.Text</span><span class="sxs-lookup"><span data-stu-id="8a084-209">Note.Text</span></span>
 - <span data-ttu-id="8a084-210">反应</span><span class="sxs-lookup"><span data-stu-id="8a084-210">Reaction</span></span>
    - <span data-ttu-id="8a084-211">实体 (一个编码元素) </span><span class="sxs-lookup"><span data-stu-id="8a084-211">Substance (one coding element)</span></span>
    - <span data-ttu-id="8a084-212">一 (一个编码元素的) </span><span class="sxs-lookup"><span data-stu-id="8a084-212">Manifestation (one coding element)</span></span>

<span data-ttu-id="8a084-213">资源搜索使用 GET 方法和以下参数：</span><span class="sxs-lookup"><span data-stu-id="8a084-213">A resource search uses the GET method and the following parameters:</span></span>

 - <span data-ttu-id="8a084-214">Patient =  \<patient id></span><span class="sxs-lookup"><span data-stu-id="8a084-214">Patient =  \<patient id></span></span>

<span data-ttu-id="8a084-215">请参阅以下调用示例：</span><span class="sxs-lookup"><span data-stu-id="8a084-215">See the following example of the call:</span></span> 

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

<span data-ttu-id="8a084-216">有关 [https://hl7.org/fhir/stu3/allergyintolerance.html](https://hl7.org/fhir/stu3/allergyintolerance.html) 此字段集的其他详细信息，请参阅 。</span><span class="sxs-lookup"><span data-stu-id="8a084-216">See [https://hl7.org/fhir/stu3/allergyintolerance.html](https://hl7.org/fhir/stu3/allergyintolerance.html) for other details on this field set.</span></span>

## <a name="medication-request"></a><span data-ttu-id="8a084-217">药物请求</span><span class="sxs-lookup"><span data-stu-id="8a084-217">Medication Request</span></span>

<span data-ttu-id="8a084-218">这些是最小必填字段，这些字段是 ["美国核心药物请求"配置文件的子集](http://www.hl7.org/fhir/us/core/StructureDefinition-us-core-medicationrequest.html)：</span><span class="sxs-lookup"><span data-stu-id="8a084-218">These are the minimum required fields, which are a subset of the [US Core Medication Request profile](http://www.hl7.org/fhir/us/core/StructureDefinition-us-core-medicationrequest.html):</span></span>

 - <span data-ttu-id="8a084-219">如果参考， (显示) </span><span class="sxs-lookup"><span data-stu-id="8a084-219">Medication.Display (if Reference)</span></span>
 - <span data-ttu-id="8a084-220">如果 CodableConcept (，将使用"药物.文本) </span><span class="sxs-lookup"><span data-stu-id="8a084-220">Medication.Text (if CodableConcept)</span></span>
 - <span data-ttu-id="8a084-221">AuthoredOn</span><span class="sxs-lookup"><span data-stu-id="8a084-221">AuthoredOn</span></span>
 - <span data-ttu-id="8a084-222">Requester.Agent.Display</span><span class="sxs-lookup"><span data-stu-id="8a084-222">Requester.Agent.Display</span></span>

<span data-ttu-id="8a084-223">除了"US Core"字段之外，为了获得出色的用户体验，Patients 应用还可以读取以下字段：</span><span class="sxs-lookup"><span data-stu-id="8a084-223">In addition to the US Core fields, for a great user experience the Patients app can also read the following fields:</span></span>

 - <span data-ttu-id="8a084-224">一文[..]。文本</span><span class="sxs-lookup"><span data-stu-id="8a084-224">DosageInstruction[..].Text</span></span>
 - <span data-ttu-id="8a084-225">文本</span><span class="sxs-lookup"><span data-stu-id="8a084-225">Text</span></span>

<span data-ttu-id="8a084-226">资源搜索使用 GET 方法和以下参数：</span><span class="sxs-lookup"><span data-stu-id="8a084-226">A resource search uses the GET method and the following parameters:</span></span>

 - <span data-ttu-id="8a084-227">patient=\<patient id></span><span class="sxs-lookup"><span data-stu-id="8a084-227">patient=\<patient id></span></span>
 - <span data-ttu-id="8a084-228">_count=\<max results></span><span class="sxs-lookup"><span data-stu-id="8a084-228">_count=\<max results></span></span>

<span data-ttu-id="8a084-229">有关 [https://www.hl7.org/fhir/medicationrequest.html](https://www.hl7.org/fhir/medicationrequest.html) 此字段集的其他详细信息，请参阅 。</span><span class="sxs-lookup"><span data-stu-id="8a084-229">See [https://www.hl7.org/fhir/medicationrequest.html](https://www.hl7.org/fhir/medicationrequest.html) for other details on this field set.</span></span>

## <a name="coverage"></a><span data-ttu-id="8a084-230">覆盖范围</span><span class="sxs-lookup"><span data-stu-id="8a084-230">Coverage</span></span>

<span data-ttu-id="8a084-231">这些是最小必填字段，US Core 或 Argonaut 配置文件未涵盖这些字段：</span><span class="sxs-lookup"><span data-stu-id="8a084-231">These are the minimum required fields, not covered by either US Core or Argonaut profiles:</span></span>

 - <span data-ttu-id="8a084-232">分组，至少包含一个元素</span><span class="sxs-lookup"><span data-stu-id="8a084-232">Grouping, at least one element with</span></span>
    - <span data-ttu-id="8a084-233">GroupDisplay</span><span class="sxs-lookup"><span data-stu-id="8a084-233">GroupDisplay</span></span>
    - <span data-ttu-id="8a084-234">PlanDisplay</span><span class="sxs-lookup"><span data-stu-id="8a084-234">PlanDisplay</span></span>
 - <span data-ttu-id="8a084-235">Period</span><span class="sxs-lookup"><span data-stu-id="8a084-235">Period</span></span>
 - <span data-ttu-id="8a084-236">SubscriberId</span><span class="sxs-lookup"><span data-stu-id="8a084-236">SubscriberId</span></span>

<span data-ttu-id="8a084-237">资源搜索使用 GET 方法和以下参数：</span><span class="sxs-lookup"><span data-stu-id="8a084-237">A resource search uses the GET method and the following parameters:</span></span>

 - <span data-ttu-id="8a084-238">Patient = \<patient id></span><span class="sxs-lookup"><span data-stu-id="8a084-238">Patient = \<patient id></span></span>

<span data-ttu-id="8a084-239">有关 [https://hl7.org/fhir/stu3/coverage.html](https://www.hl7.org/fhir/medicationrequest.html) 此字段集的其他详细信息，请参阅 。</span><span class="sxs-lookup"><span data-stu-id="8a084-239">See [https://hl7.org/fhir/stu3/coverage.html](https://www.hl7.org/fhir/medicationrequest.html) for other details on this field set.</span></span>
