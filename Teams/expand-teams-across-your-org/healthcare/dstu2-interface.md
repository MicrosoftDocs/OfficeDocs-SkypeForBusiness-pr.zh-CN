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
ms.openlocfilehash: d29dab88f6ee53eb4c758f6c95f71278e20ecdbe
ms.sourcegitcommit: 0a51738879b13991986a3a872445daa8bd20533d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "48766975"
---
# <a name="dstu2-interface-specification"></a><span data-ttu-id="07b98-103">DSTU2 接口规范</span><span class="sxs-lookup"><span data-stu-id="07b98-103">DSTU2 interface specification</span></span>

> [!IMPORTANT]
> <span data-ttu-id="07b98-104">**2020年10月30日生效，患者应用将被否决，用户将无法再从团队应用商店安装。我们鼓励你立即开始使用团队中的 " [列表" 应用](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) 。**</span><span class="sxs-lookup"><span data-stu-id="07b98-104">**Effective October 30, 2020, the Patients app will be deprecated and users will no longer be able to install it from the Teams app store. We encourage you to start using the [Lists app](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) in Teams today.**</span></span>
>
><span data-ttu-id="07b98-105">患者应用数据存储在支持团队的 Office 365 组的组邮箱中。</span><span class="sxs-lookup"><span data-stu-id="07b98-105">Patients app data is stored in the group mailbox of the Office 365 group that backs the team.</span></span> <span data-ttu-id="07b98-106">当患者应用停用时，与之关联的所有数据将保留在此组中，但不能再通过用户界面进行访问。</span><span class="sxs-lookup"><span data-stu-id="07b98-106">When the Patients app is retired, all data associated with it will be retained in this group but can no longer be accessed through the user interface.</span></span> <span data-ttu-id="07b98-107">当前用户可以使用 " [列表" 应用](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db)重新创建其列表。</span><span class="sxs-lookup"><span data-stu-id="07b98-107">Current users can re-create their lists using the [Lists app](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db).</span></span>
>
><span data-ttu-id="07b98-108">" [列表" 应用](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) 为所有团队用户预安装，可在每个团队和频道中用作选项卡。</span><span class="sxs-lookup"><span data-stu-id="07b98-108">The [Lists app](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) is pre-installed for all Teams users and is available as a tab in every team and channel.</span></span> <span data-ttu-id="07b98-109">使用列表，运行状况团队可以使用内置患者模板、从头开始或通过将数据导入 Excel 来创建患者列表。</span><span class="sxs-lookup"><span data-stu-id="07b98-109">With Lists, health teams can create patient lists using the built-in Patients template, from scratch, or by importing data to Excel.</span></span> <span data-ttu-id="07b98-110">若要了解有关如何管理组织中的列表应用的详细信息，请参阅 [管理列表应用](../../manage-lists-app.md)。</span><span class="sxs-lookup"><span data-stu-id="07b98-110">To learn more about how to manage the Lists app in your organization, see [Manage the Lists app](../../manage-lists-app.md).</span></span>

[!INCLUDE [preview-feature](../../includes/preview-feature.md)]

<span data-ttu-id="07b98-111">设置或重新配置 FHIR 服务器以处理 Microsoft 团队患者应用需要了解应用需要访问的数据。</span><span class="sxs-lookup"><span data-stu-id="07b98-111">Setting up or reconfiguring an FHIR server to work with the Microsoft Teams Patients app requires understanding what data the app needs to access.</span></span> <span data-ttu-id="07b98-112">FHIR 服务器必须使用以下资源的捆绑包支持发布请求：</span><span class="sxs-lookup"><span data-stu-id="07b98-112">The FHIR server must support POST requests using bundles for the following resources:</span></span>

- [<span data-ttu-id="07b98-113">档案</span><span class="sxs-lookup"><span data-stu-id="07b98-113">Patient</span></span>](#patient)
- [<span data-ttu-id="07b98-114">知识产权</span><span class="sxs-lookup"><span data-stu-id="07b98-114">Observation</span></span>](#observation)
- [<span data-ttu-id="07b98-115">条件</span><span class="sxs-lookup"><span data-stu-id="07b98-115">Condition</span></span>](#condition)
- [<span data-ttu-id="07b98-116">产生</span><span class="sxs-lookup"><span data-stu-id="07b98-116">Encounter</span></span>](#encounter)
- [<span data-ttu-id="07b98-117">过敏症 intolerance</span><span class="sxs-lookup"><span data-stu-id="07b98-117">Allergy intolerance</span></span>](#allergyintolerance)
- [<span data-ttu-id="07b98-118">内</span><span class="sxs-lookup"><span data-stu-id="07b98-118">Coverage</span></span>](#coverage)
- [<span data-ttu-id="07b98-119">药物订货</span><span class="sxs-lookup"><span data-stu-id="07b98-119">Medication Order</span></span>](#medication-order)
- [<span data-ttu-id="07b98-120">位置</span><span class="sxs-lookup"><span data-stu-id="07b98-120">Location</span></span>](#location)

> [!NOTE]
> <span data-ttu-id="07b98-121">患者资源是唯一必需的资源 (不会加载应用程序。</span><span class="sxs-lookup"><span data-stu-id="07b98-121">The Patient resource is the only mandatory resource (without which the app will not load at all.</span></span> <span data-ttu-id="07b98-122">但是，建议合作伙伴针对 Microsoft 团队患者应用的最佳最终用户体验，针对以下提供的针对以上提及的所有资源提供支持。</span><span class="sxs-lookup"><span data-stu-id="07b98-122">However, it is recommended that the Partner implement support for all the above mentioned resources per specifications provided below for the best end-user experience with the Microsoft Teams Patients App.</span></span>

<span data-ttu-id="07b98-123">来自 Microsoft 团队患者应用的来自多个资源的查询发布捆绑 (对 FHIR 服务器 URL 的请求的批处理) 。</span><span class="sxs-lookup"><span data-stu-id="07b98-123">Queries from the Microsoft Teams Patients app for more than one resource post a bundle (BATCH) of requests to the FHIR server's URL.</span></span> <span data-ttu-id="07b98-124">服务器处理每个请求，并返回每个请求所匹配的资源的捆绑包。</span><span class="sxs-lookup"><span data-stu-id="07b98-124">The server processes each request and returns a bundle of the resources matched by each request.</span></span> <span data-ttu-id="07b98-125">有关详细信息和示例，请参阅 [https://www.hl7.org/fhir/DSTU2/http.html#transaction](https://www.hl7.org/fhir/DSTU2/http.html#transaction) 。</span><span class="sxs-lookup"><span data-stu-id="07b98-125">For more information and examples, see [https://www.hl7.org/fhir/DSTU2/http.html#transaction](https://www.hl7.org/fhir/DSTU2/http.html#transaction).</span></span>

<span data-ttu-id="07b98-126">所有以下 FHIR 资源应可通过直接资源参考访问。</span><span class="sxs-lookup"><span data-stu-id="07b98-126">All the following FHIR resources should be accessible by direct resource reference.</span></span>

## <a name="conformance-minimum-required-field-set"></a><span data-ttu-id="07b98-127">一致性最低要求字段集</span><span class="sxs-lookup"><span data-stu-id="07b98-127">Conformance minimum required field set</span></span>

 <span data-ttu-id="07b98-128">FHIR 服务器必须实现一致性声明，才能为我们提供其功能的实际摘要。</span><span class="sxs-lookup"><span data-stu-id="07b98-128">The FHIR Server must implement the conformance statement for us to have a factual summary of its capabilities.</span></span> <span data-ttu-id="07b98-129">我们期望 DSTU2 FHIR 服务器中的以下参数：</span><span class="sxs-lookup"><span data-stu-id="07b98-129">We expect the below parameters in a DSTU2 FHIR Server:</span></span>

 - <span data-ttu-id="07b98-130">余下</span><span class="sxs-lookup"><span data-stu-id="07b98-130">REST</span></span>

    - <span data-ttu-id="07b98-131">众</span><span class="sxs-lookup"><span data-stu-id="07b98-131">Mode</span></span>
    - <span data-ttu-id="07b98-132">相交</span><span class="sxs-lookup"><span data-stu-id="07b98-132">Interaction</span></span>
    - <span data-ttu-id="07b98-133">资源：类型</span><span class="sxs-lookup"><span data-stu-id="07b98-133">Resource: Type</span></span>
    - <span data-ttu-id="07b98-134">安全性： [OAuth uri 的扩展](https://hl7.org/fhir/extension-oauth-uris.html)</span><span class="sxs-lookup"><span data-stu-id="07b98-134">Security: [Extension for OAuth URIs](https://hl7.org/fhir/extension-oauth-uris.html)</span></span>
   
 - <span data-ttu-id="07b98-135">FhirVersion (我们的代码需要此内容，以了解我们支持多个版本时应透视到的版本。 ) </span><span class="sxs-lookup"><span data-stu-id="07b98-135">FhirVersion (Our code requires this to understand which version we should pivot to as we support multiple versions.)</span></span>

<span data-ttu-id="07b98-136">[https://www.hl7.org/fhir/dstu2/conformance.html](https://www.hl7.org/fhir/dstu2/conformance.html)有关此字段集的其他详细信息，请参阅。</span><span class="sxs-lookup"><span data-stu-id="07b98-136">See [https://www.hl7.org/fhir/dstu2/conformance.html](https://www.hl7.org/fhir/dstu2/conformance.html) for other details on this field set.</span></span>

## <a name="patient"></a><span data-ttu-id="07b98-137">档案</span><span class="sxs-lookup"><span data-stu-id="07b98-137">Patient</span></span>

<span data-ttu-id="07b98-138">以下是 " [Argonaut" 患者档案](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-patient.html) 字段子集的最少必填字段：</span><span class="sxs-lookup"><span data-stu-id="07b98-138">These are the minimum required fields, which are a subset of the [Argonaut patient profile](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-patient.html) fields:</span></span>

 - <span data-ttu-id="07b98-139">名称。家庭</span><span class="sxs-lookup"><span data-stu-id="07b98-139">Name.Family</span></span>
 - <span data-ttu-id="07b98-140">名称。给定</span><span class="sxs-lookup"><span data-stu-id="07b98-140">Name.Given</span></span>
 - <span data-ttu-id="07b98-141">性别</span><span class="sxs-lookup"><span data-stu-id="07b98-141">Gender</span></span>
 - <span data-ttu-id="07b98-142">BirthDate</span><span class="sxs-lookup"><span data-stu-id="07b98-142">BirthDate</span></span>
 - <span data-ttu-id="07b98-143">MRN (标识符) </span><span class="sxs-lookup"><span data-stu-id="07b98-143">MRN (Identifier)</span></span>

<span data-ttu-id="07b98-144">除了 Argonaut 字段，为患者应用提供出色的用户体验还会读取以下字段：</span><span class="sxs-lookup"><span data-stu-id="07b98-144">In addition to the Argonaut fields, for a great user experience the Patients app also reads the following fields:</span></span>

 - <span data-ttu-id="07b98-145">名称。使用</span><span class="sxs-lookup"><span data-stu-id="07b98-145">Name.Use</span></span>
 - <span data-ttu-id="07b98-146">名称。前缀</span><span class="sxs-lookup"><span data-stu-id="07b98-146">Name.Prefix</span></span>
 - <span data-ttu-id="07b98-147">CareProvider (对患者资源的此参考应包括以下示例中所示的显示字段。 ) </span><span class="sxs-lookup"><span data-stu-id="07b98-147">CareProvider (This reference on the Patient resource should include the display fields shown in the following example.)</span></span>

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

<span data-ttu-id="07b98-148">资源搜索在/Patient/_search 使用 POST 方法，并使用以下参数：</span><span class="sxs-lookup"><span data-stu-id="07b98-148">A resource search uses the POST method at /Patient/_search and the following parameters:</span></span>

 - <span data-ttu-id="07b98-149">标识号</span><span class="sxs-lookup"><span data-stu-id="07b98-149">id</span></span>
 - <span data-ttu-id="07b98-150">系列：包含 = (搜索其系列名称包含值的所有患者。 ) </span><span class="sxs-lookup"><span data-stu-id="07b98-150">family:contains=(searches for all patients whose family name contains the value.)</span></span>
 - <span data-ttu-id="07b98-151">给定 =\<substring></span><span class="sxs-lookup"><span data-stu-id="07b98-151">given=\<substring></span></span>
 - <span data-ttu-id="07b98-152">名称 =\<substring></span><span class="sxs-lookup"><span data-stu-id="07b98-152">name=\<substring></span></span>
 - <span data-ttu-id="07b98-153">出生日期 = (完全匹配) </span><span class="sxs-lookup"><span data-stu-id="07b98-153">birthdate=(exact match)</span></span>
 - <span data-ttu-id="07b98-154">\_计数 (应返回的最大结果数) </span><span class="sxs-lookup"><span data-stu-id="07b98-154">\_count (maximum number of results that should be returned)</span></span> <br> <span data-ttu-id="07b98-155">该响应应包含作为搜索结果返回的记录的总数， \_ PatientsApp 将使用该计数来限制返回的记录数。</span><span class="sxs-lookup"><span data-stu-id="07b98-155">The response should contain the total count of records returned as a result of the search, and \_count will be used by the PatientsApp to limit the number of records returned.</span></span>
 - <span data-ttu-id="07b98-156">标识符 =\<mrn></span><span class="sxs-lookup"><span data-stu-id="07b98-156">identifier=\<mrn></span></span>

<span data-ttu-id="07b98-157">目标是能够搜索和筛选患者，如下所示：</span><span class="sxs-lookup"><span data-stu-id="07b98-157">The goal is to be able to search and filter for a patient by the following:</span></span>

- <span data-ttu-id="07b98-158">ID：这是 FHIR 中的每个资源具有的资源 ID。</span><span class="sxs-lookup"><span data-stu-id="07b98-158">ID: This is the resource ID that every resource in FHIR has.</span></span>
- <span data-ttu-id="07b98-159">MRN：这是临床人员将知道的患者的实际标识符。</span><span class="sxs-lookup"><span data-stu-id="07b98-159">MRN: This is the actual identifier for the patient that clinical staff would know.</span></span> <span data-ttu-id="07b98-160">我们理解此 MRN 基于 FHIR 中的标识符资源内的标识符类型</span><span class="sxs-lookup"><span data-stu-id="07b98-160">We understand this MRN is based on the type of identifier inside the identifier resource in FHIR</span></span>
- <span data-ttu-id="07b98-161">名称</span><span class="sxs-lookup"><span data-stu-id="07b98-161">Name</span></span>
- <span data-ttu-id="07b98-162">Birthdate</span><span class="sxs-lookup"><span data-stu-id="07b98-162">Birthdate</span></span>

<span data-ttu-id="07b98-163">请参阅下面的此通话示例。</span><span class="sxs-lookup"><span data-stu-id="07b98-163">See the following example  of this call.</span></span>

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

<span data-ttu-id="07b98-164">[https://www.hl7.org/fhir/DSTU2/Patient.html](https://www.hl7.org/fhir/DSTU2/Patient.html)有关此字段集的其他详细信息，请参阅。</span><span class="sxs-lookup"><span data-stu-id="07b98-164">See [https://www.hl7.org/fhir/DSTU2/Patient.html](https://www.hl7.org/fhir/DSTU2/Patient.html) for other details on this field set.</span></span>

## <a name="observation"></a><span data-ttu-id="07b98-165">知识产权</span><span class="sxs-lookup"><span data-stu-id="07b98-165">Observation</span></span>

<span data-ttu-id="07b98-166">以下是最少的必填字段，这些字段是 Argonaut 的重要符号配置文件的子集：</span><span class="sxs-lookup"><span data-stu-id="07b98-166">These are the minimum required fields, which are a subset of the Argonaut vital signs profile:</span></span>

 - <span data-ttu-id="07b98-167">有效 (日期时间或期间) </span><span class="sxs-lookup"><span data-stu-id="07b98-167">Effective (date time or period)</span></span>
 - <span data-ttu-id="07b98-168">编码代码</span><span class="sxs-lookup"><span data-stu-id="07b98-168">Code.Coding.Code</span></span>
 - <span data-ttu-id="07b98-169">ValueQuantity 值</span><span class="sxs-lookup"><span data-stu-id="07b98-169">ValueQuantity.Value</span></span>

<span data-ttu-id="07b98-170">除了 Argonaut 字段，为患者应用提供出色的用户体验还会读取以下字段：</span><span class="sxs-lookup"><span data-stu-id="07b98-170">In addition to the Argonaut fields, for a great user experience the Patients app also reads the following fields:</span></span>

 - <span data-ttu-id="07b98-171">代码编码。显示</span><span class="sxs-lookup"><span data-stu-id="07b98-171">Code.Coding.Display</span></span>
 - <span data-ttu-id="07b98-172">ValueQuantity 单位</span><span class="sxs-lookup"><span data-stu-id="07b98-172">ValueQuantity.Unit</span></span>

<span data-ttu-id="07b98-173">如果使用组件观测值，则相同的逻辑适用于每个组件观察。</span><span class="sxs-lookup"><span data-stu-id="07b98-173">If using component observations, the same logic applies for each component observation.</span></span>

<span data-ttu-id="07b98-174">资源搜索使用 GET 方法和以下参数：</span><span class="sxs-lookup"><span data-stu-id="07b98-174">A resource search uses the GET method and the following parameters:</span></span>

 - <span data-ttu-id="07b98-175">患者 =\<patient id\></span><span class="sxs-lookup"><span data-stu-id="07b98-175">patient=\<patient id\></span></span>
 - <span data-ttu-id="07b98-176">排序： desc =\<field ex. date\></span><span class="sxs-lookup"><span data-stu-id="07b98-176">sort:desc=\<field ex. date\></span></span>

<span data-ttu-id="07b98-177">目标是能够检索患者的最新重要标志 [VitalSigns] (观察？ ) 。</span><span class="sxs-lookup"><span data-stu-id="07b98-177">The goal is to be able to retrieve the latest vital signs for a patient, [VitalSigns.DSTU.saz]  (observation?).</span></span>

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

<span data-ttu-id="07b98-178">[https://www.hl7.org/fhir/DSTU2/Observation.html](https://www.hl7.org/fhir/DSTU2/Observation.html)有关此字段集的其他详细信息，请参阅。</span><span class="sxs-lookup"><span data-stu-id="07b98-178">See [https://www.hl7.org/fhir/DSTU2/Observation.html](https://www.hl7.org/fhir/DSTU2/Observation.html) for other details on this field set.</span></span>

## <a name="condition"></a><span data-ttu-id="07b98-179">条件</span><span class="sxs-lookup"><span data-stu-id="07b98-179">Condition</span></span>

<span data-ttu-id="07b98-180">下面是 [Argonaut 条件配置文件](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-condition.html)子集的最少必填字段：</span><span class="sxs-lookup"><span data-stu-id="07b98-180">These are the minimum required fields, which are a subset of the [Argonaut condition profile](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-condition.html):</span></span>

1. <span data-ttu-id="07b98-181">代码。编码 [0]。画面</span><span class="sxs-lookup"><span data-stu-id="07b98-181">Code.Coding[0].Display</span></span>

<span data-ttu-id="07b98-182">除了 Argonaut 字段外，还可以为患者应用提供出色的用户体验，还可以读取以下字段：</span><span class="sxs-lookup"><span data-stu-id="07b98-182">In addition to the Argonaut fields, for a great user experience the Patients app can also read the following fields:</span></span>

 - <span data-ttu-id="07b98-183">录制日期</span><span class="sxs-lookup"><span data-stu-id="07b98-183">Date Recorded</span></span>
 - <span data-ttu-id="07b98-184">严重性</span><span class="sxs-lookup"><span data-stu-id="07b98-184">Severity</span></span>

<span data-ttu-id="07b98-185">资源搜索使用 GET 方法和以下参数：</span><span class="sxs-lookup"><span data-stu-id="07b98-185">A resource search uses the GET method and the following parameters:</span></span>

 - <span data-ttu-id="07b98-186">患者 =\<patient id></span><span class="sxs-lookup"><span data-stu-id="07b98-186">patient=\<patient id></span></span>
 - <span data-ttu-id="07b98-187">_count =\<max results></span><span class="sxs-lookup"><span data-stu-id="07b98-187">_count=\<max results></span></span>

<span data-ttu-id="07b98-188">请参阅下面的此呼叫示例：</span><span class="sxs-lookup"><span data-stu-id="07b98-188">See the following example of this call:</span></span>

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

<span data-ttu-id="07b98-189">[https://www.hl7.org/fhir/DSTU2/Condition.html](https://www.hl7.org/fhir/DSTU2/Condition.html)有关此字段集的其他详细信息，请参阅。</span><span class="sxs-lookup"><span data-stu-id="07b98-189">See [https://www.hl7.org/fhir/DSTU2/Condition.html](https://www.hl7.org/fhir/DSTU2/Condition.html) for other details on this field set.</span></span>

## <a name="encounter"></a><span data-ttu-id="07b98-190">产生</span><span class="sxs-lookup"><span data-stu-id="07b98-190">Encounter</span></span>

<span data-ttu-id="07b98-191">以下是最少必填字段，这些字段是 "美国核心" 基本配置文件 "必须具有" 字段的子集：</span><span class="sxs-lookup"><span data-stu-id="07b98-191">These are the minimum required fields, which are a subset of the US Core Encounter profile "must have" fields:</span></span>

 - <span data-ttu-id="07b98-192">状态栏</span><span class="sxs-lookup"><span data-stu-id="07b98-192">Status</span></span>
 - <span data-ttu-id="07b98-193">键入 [0]。编码 [0]。画面</span><span class="sxs-lookup"><span data-stu-id="07b98-193">Type[0].Coding[0].Display</span></span>

<span data-ttu-id="07b98-194">此外，美国核心的以下字段会遇到配置文件的 "必须支持" 字段</span><span class="sxs-lookup"><span data-stu-id="07b98-194">In addition, the following fields from US Core Encounter profile's "must support" fields</span></span>

 - <span data-ttu-id="07b98-195">句号。开始</span><span class="sxs-lookup"><span data-stu-id="07b98-195">Period.Start</span></span>
 - <span data-ttu-id="07b98-196">位置 [0]。位置。显示</span><span class="sxs-lookup"><span data-stu-id="07b98-196">Location[0].Location.Display</span></span>

<span data-ttu-id="07b98-197">资源搜索使用 GET 方法和以下参数：</span><span class="sxs-lookup"><span data-stu-id="07b98-197">A resource search uses the GET method and the following parameters:</span></span>

 - <span data-ttu-id="07b98-198">患者 =\<patient id></span><span class="sxs-lookup"><span data-stu-id="07b98-198">patient=\<patient id></span></span>
 - <span data-ttu-id="07b98-199">_sort： desc =\<field ex. date></span><span class="sxs-lookup"><span data-stu-id="07b98-199">_sort:desc=\<field ex. date></span></span>
 - <span data-ttu-id="07b98-200">_count =\<max results></span><span class="sxs-lookup"><span data-stu-id="07b98-200">_count=\<max results></span></span>

<span data-ttu-id="07b98-201">目标是能够检索患者的最后一个已知位置。</span><span class="sxs-lookup"><span data-stu-id="07b98-201">The goal is to be able to retrieve the patient's last known location.</span></span> <span data-ttu-id="07b98-202">每个遇到的都引用一个位置资源。</span><span class="sxs-lookup"><span data-stu-id="07b98-202">Each encounter references a location resource.</span></span> <span data-ttu-id="07b98-203">该引用还应包含位置的显示字段。</span><span class="sxs-lookup"><span data-stu-id="07b98-203">The reference shall also include the location's display field.</span></span> <span data-ttu-id="07b98-204">请参阅下面的此通话示例。</span><span class="sxs-lookup"><span data-stu-id="07b98-204">See the following example of this call.</span></span>

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

<span data-ttu-id="07b98-205">[https://www.hl7.org/fhir/DSTU2/Encounter.htm](https://www.hl7.org/fhir/DSTU2/Encounter.htm)有关此字段集的其他详细信息，请参阅。</span><span class="sxs-lookup"><span data-stu-id="07b98-205">See [https://www.hl7.org/fhir/DSTU2/Encounter.htm](https://www.hl7.org/fhir/DSTU2/Encounter.htm) for other details on this field set.</span></span>

## <a name="allergyintolerance"></a><span data-ttu-id="07b98-206">AllergyIntolerance</span><span class="sxs-lookup"><span data-stu-id="07b98-206">AllergyIntolerance</span></span>

<span data-ttu-id="07b98-207">以下是最少的必填字段，它们是 Argonaut AllergyIntolerance 配置文件的子集：</span><span class="sxs-lookup"><span data-stu-id="07b98-207">These are the minimum required fields, which are a subset of the Argonaut AllergyIntolerance profile:</span></span>

 - <span data-ttu-id="07b98-208">代码。文本</span><span class="sxs-lookup"><span data-stu-id="07b98-208">Code.Text</span></span>
 - <span data-ttu-id="07b98-209">代码。编码 [0]。画面</span><span class="sxs-lookup"><span data-stu-id="07b98-209">Code.Coding[0].Display</span></span>
 - <span data-ttu-id="07b98-210">状态栏</span><span class="sxs-lookup"><span data-stu-id="07b98-210">Status</span></span>

<span data-ttu-id="07b98-211">除了 Argonaut 字段，为患者应用提供出色的用户体验还会读取以下字段：</span><span class="sxs-lookup"><span data-stu-id="07b98-211">In addition to the Argonaut fields, for a great user experience the Patients app also reads the following fields:</span></span>

 - <span data-ttu-id="07b98-212">RecordedDate</span><span class="sxs-lookup"><span data-stu-id="07b98-212">RecordedDate</span></span>
 - <span data-ttu-id="07b98-213">备注。文本</span><span class="sxs-lookup"><span data-stu-id="07b98-213">Note.Text</span></span>
 - <span data-ttu-id="07b98-214">反应 [...]。物质。文本</span><span class="sxs-lookup"><span data-stu-id="07b98-214">Reaction[..].Substance.Text</span></span>
 - <span data-ttu-id="07b98-215">反应 [...]。表现形式 [...]。文本</span><span class="sxs-lookup"><span data-stu-id="07b98-215">Reaction[..].Manifestation[..].Text</span></span>
 - <span data-ttu-id="07b98-216">文本 Div</span><span class="sxs-lookup"><span data-stu-id="07b98-216">Text.Div</span></span>

<span data-ttu-id="07b98-217">资源搜索使用 GET 方法和以下参数：</span><span class="sxs-lookup"><span data-stu-id="07b98-217">A resource search uses the GET method and the following parameters:</span></span>

 - <span data-ttu-id="07b98-218">患者 =  \<patient id></span><span class="sxs-lookup"><span data-stu-id="07b98-218">Patient =  \<patient id></span></span>

<span data-ttu-id="07b98-219">请参阅下面的此呼叫示例：</span><span class="sxs-lookup"><span data-stu-id="07b98-219">See the following example of this call:</span></span>

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

<span data-ttu-id="07b98-220">[https://www.hl7.org/fhir/DSTU2/AllergyIntolerance.html](https://www.hl7.org/fhir/DSTU2/AllergyIntolerance.html)有关此字段集的其他详细信息，请参阅。</span><span class="sxs-lookup"><span data-stu-id="07b98-220">See [https://www.hl7.org/fhir/DSTU2/AllergyIntolerance.html](https://www.hl7.org/fhir/DSTU2/AllergyIntolerance.html) for other details on this field set.</span></span>

## <a name="medication-order"></a><span data-ttu-id="07b98-221">药物订货</span><span class="sxs-lookup"><span data-stu-id="07b98-221">Medication Order</span></span>

<span data-ttu-id="07b98-222">以下是最少的必填字段，它们是 Argonaut MedicationOrder 配置文件的子集：</span><span class="sxs-lookup"><span data-stu-id="07b98-222">These are the minimum required fields, which are a subset of the Argonaut MedicationOrder profile:</span></span>

 - <span data-ttu-id="07b98-223">DateWritten</span><span class="sxs-lookup"><span data-stu-id="07b98-223">DateWritten</span></span>
 - <span data-ttu-id="07b98-224">Prescriber 显示</span><span class="sxs-lookup"><span data-stu-id="07b98-224">Prescriber.Display</span></span>
 - <span data-ttu-id="07b98-225">药物。如果引用) ，则显示 (</span><span class="sxs-lookup"><span data-stu-id="07b98-225">Medication.Display (if reference)</span></span>
 - <span data-ttu-id="07b98-226"> () 概念的 "药物" 文本</span><span class="sxs-lookup"><span data-stu-id="07b98-226">Medication.Text (if concept)</span></span>

<span data-ttu-id="07b98-227">除了 Argonaut 字段外，还可以为患者应用提供出色的用户体验，还可以读取以下字段：</span><span class="sxs-lookup"><span data-stu-id="07b98-227">In addition to the Argonaut fields, for a great user experience the Patients app can also read the following fields:</span></span>

 - <span data-ttu-id="07b98-228">DateEnded</span><span class="sxs-lookup"><span data-stu-id="07b98-228">DateEnded</span></span>
 - <span data-ttu-id="07b98-229">DosageInstruction</span><span class="sxs-lookup"><span data-stu-id="07b98-229">DosageInstruction.Text</span></span>
 - <span data-ttu-id="07b98-230">文本 Div</span><span class="sxs-lookup"><span data-stu-id="07b98-230">Text.Div</span></span>

<span data-ttu-id="07b98-231">资源搜索使用 GET 方法和以下参数：</span><span class="sxs-lookup"><span data-stu-id="07b98-231">A resource search uses the GET method and the following parameters:</span></span>

 - <span data-ttu-id="07b98-232">患者 =\<patient id></span><span class="sxs-lookup"><span data-stu-id="07b98-232">patient=\<patient id></span></span>
 - <span data-ttu-id="07b98-233">_count =\<max results></span><span class="sxs-lookup"><span data-stu-id="07b98-233">_count=\<max results></span></span>

<span data-ttu-id="07b98-234">请参阅下面的此呼叫示例：</span><span class="sxs-lookup"><span data-stu-id="07b98-234">See the following example of this call:</span></span>

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

<span data-ttu-id="07b98-235">[https://www.hl7.org/fhir/DSTU2/MedicationOrder.html](https://www.hl7.org/fhir/DSTU2/MedicationOrder.html)有关此字段集的其他详细信息，请参阅。</span><span class="sxs-lookup"><span data-stu-id="07b98-235">See [https://www.hl7.org/fhir/DSTU2/MedicationOrder.html](https://www.hl7.org/fhir/DSTU2/MedicationOrder.html) for other details on this field set.</span></span>

## <a name="coverage"></a><span data-ttu-id="07b98-236">内</span><span class="sxs-lookup"><span data-stu-id="07b98-236">Coverage</span></span>

<span data-ttu-id="07b98-237">以下是 "最少必填字段"，不包含在美国 Core 或 Argonaut 配置文件中：</span><span class="sxs-lookup"><span data-stu-id="07b98-237">These are the minimum required fields, not covered by either US Core or Argonaut profiles:</span></span>

 - <span data-ttu-id="07b98-238">Payor</span><span class="sxs-lookup"><span data-stu-id="07b98-238">Payor</span></span>

<span data-ttu-id="07b98-239">资源搜索使用 GET 方法和以下参数：</span><span class="sxs-lookup"><span data-stu-id="07b98-239">A resource search uses the GET method and the following parameters:</span></span>

 - <span data-ttu-id="07b98-240">患者 =\<patient id></span><span class="sxs-lookup"><span data-stu-id="07b98-240">patient=\<patient id></span></span>

<span data-ttu-id="07b98-241">请参阅下面的此呼叫示例：</span><span class="sxs-lookup"><span data-stu-id="07b98-241">See the following example of this call:</span></span>

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
    
<span data-ttu-id="07b98-242">[https://www.hl7.org/fhir/DSTU2/Coverage.html](https://www.hl7.org/fhir/DSTU2/Coverage.html)有关此字段集的其他详细信息，请参阅。</span><span class="sxs-lookup"><span data-stu-id="07b98-242">See [https://www.hl7.org/fhir/DSTU2/Coverage.html](https://www.hl7.org/fhir/DSTU2/Coverage.html) for other details on this field set.</span></span>

## <a name="location"></a><span data-ttu-id="07b98-243">位置</span><span class="sxs-lookup"><span data-stu-id="07b98-243">Location</span></span>

<span data-ttu-id="07b98-244">此资源仅用作 " [遇到](#encounter) " 资源的参考。</span><span class="sxs-lookup"><span data-stu-id="07b98-244">This resource is only being used as a reference on the [Encounter](#encounter) resource.</span></span>

<span data-ttu-id="07b98-245">[https://www.hl7.org/fhir/DSTU2/Location.html](https://www.hl7.org/fhir/DSTU2/Location.html)有关此字段集的其他详细信息，请参阅。</span><span class="sxs-lookup"><span data-stu-id="07b98-245">See [https://www.hl7.org/fhir/DSTU2/Location.html](https://www.hl7.org/fhir/DSTU2/Location.html) for other details on this field set.</span></span>
