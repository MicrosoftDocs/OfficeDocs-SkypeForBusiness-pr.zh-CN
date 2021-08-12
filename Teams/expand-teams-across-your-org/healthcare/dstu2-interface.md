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
ms.openlocfilehash: 8ec2b1a88d99937e83bc8553f7dbcdd8d92f78b5a8e5708301147a26f0cffe4a
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2021
ms.locfileid: "54308761"
---
# <a name="dstu2-interface-specification"></a>DSTU2 接口规范

> [!NOTE]
> 从 2020 年 10 月 30 日起，"患者"应用已停用，并替换为 Teams [列表](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) 应用。 患者应用数据存储在支持团队的 Office 365 组的组邮箱中。 与该患者应用关联的所有数据将保留在该组，但无法再通过用户界面访问。 用户可通过"列表"应用或 [重新创建](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db)。
>
>借助列表，医疗保健组织中的护理团队可针对各种方案创建患者列表，提供圆形和内联团队会议、常规患者监视等。 查看列表的"患者"模板以开始使用。 若要深入了解如何在组织中管理列表应用，请参阅" [列表应用管理](../../manage-lists-app.md)。

设置或重新配置 FHIR 服务器以使用Microsoft Teams患者应用需要了解应用需要访问哪些数据。 FHIR 服务器必须使用捆绑包支持以下资源的 POST 请求：

- [Patient](#patient)
- [观察](#observation)
- [条件](#condition)
- [Encounter](#encounter)
- [仇恨者](#allergyintolerance)
- [覆盖范围](#coverage)
- [药物订单](#medication-order)
- [位置](#location)

> [!NOTE]
> 患者资源是唯一必需的 (资源，如果没有该资源，应用将完全无法加载。 但是，建议合作伙伴根据下面提供的规范实施对上述所有资源的支持，以获得最佳患者应用最终用户Microsoft Teams体验。

从 Microsoft Teams Patients 应用中针对多个资源的查询将捆绑包 (BATCH) FHIR 服务器 URL 的请求发布。 服务器处理每个请求，并返回每个请求匹配的资源捆绑包。 有关详细信息和示例，请参阅 [https://www.hl7.org/fhir/DSTU2/http.html#transaction](https://www.hl7.org/fhir/DSTU2/http.html#transaction) 。

以下所有 FHIR 资源都应可通过直接资源引用访问。

## <a name="conformance-minimum-required-field-set"></a>"满足最低要求"字段集

 FHIR 服务器必须实现一致性声明，以便我们获得其功能的事实摘要。 DSTU2 FHIR Server 中预期以下参数：

 - REST

    - 模式
    - 交互
    - 资源：类型
    - 安全性 [：OAuth URI 扩展](https://hl7.org/fhir/extension-oauth-uris.html)
   
 - FhirVersion (我们的代码需要此代码来了解应该透视到的版本，因为我们支持多个版本。) 

有关 [https://www.hl7.org/fhir/dstu2/conformance.html](https://www.hl7.org/fhir/dstu2/conformance.html) 此字段集的其他详细信息，请参阅 。

## <a name="patient"></a>Patient

这些是最小必填字段，这些字段是 [Argonaut 患者配置文件字段的子集](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-patient.html) ：

 - Name.Family
 - Name.Given
 - 性别
 - BirthDate
 - MRN (标识符) 

除了 Argonaut 字段之外，为了获得出色的用户体验，Patients 应用还会读取以下字段：

 - Name.Use
 - Name.Prefix
 - CareProvider (此对患者资源的引用应包括以下示例所示的显示字段。) 

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

资源搜索使用 /Patient/_search 的 POST 方法以及以下参数：

 - id
 - family：contains= (搜索其家庭名称包含 value.) 
 - given=\<substring>
 - name=\<substring>
 - birthdate= (完全匹配) 
 - \_count (应返回的结果的最大)  <br> 响应应包含搜索结果返回的记录总数，并且 PatientsApp 将使用计数来限制返回 \_ 的记录数。
 - identifier=\<mrn>

目标是能够按以下条件搜索和筛选患者：

- ID：这是 FHIR 中每个资源具有的资源 ID。
- MRN：这是患者的实际标识符，该患者是医疗人员会知道的信息。 我们知道，此 MRN 基于 FHIR 中标识符资源内的标识符类型
- 名称
- Birthdate

请参阅以下此调用的示例。

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

有关 [https://www.hl7.org/fhir/DSTU2/Patient.html](https://www.hl7.org/fhir/DSTU2/Patient.html) 此字段集的其他详细信息，请参阅 。

## <a name="observation"></a>观察

这些是最小必填字段，这些字段是 Argonaut 重要符号配置文件的子集：

 - 有效 (日期时间或) 
 - Code.Code.Code
 - ValueQuantity.Value

除了 Argonaut 字段之外，为了获得出色的用户体验，Patients 应用还会读取以下字段：

 - Code.Code.Display
 - ValueQuantity.Unit

如果使用组件观察，则相同的逻辑适用于每个组件观察。

资源搜索使用 GET 方法和以下参数：

 - patient=\<patient id\>
 - sort：desc=\<field ex. date\>

目标是能够检索患者的最新生命符号 [VitalSigns.DSTU.saz] (？) 。

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

有关 [https://www.hl7.org/fhir/DSTU2/Observation.html](https://www.hl7.org/fhir/DSTU2/Observation.html) 此字段集的其他详细信息，请参阅 。

## <a name="condition"></a>条件

这些是最小必填字段，这些字段是 [Argonaut 条件配置文件的子集](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-condition.html)：

1. Code.Code[0]。显示

除了 Argonaut 字段之外，为了获得出色的用户体验，Patients 应用还可以读取以下字段：

 - 记录的日期
 - 严重性

资源搜索使用 GET 方法和以下参数：

 - patient=\<patient id>
 - _count=\<max results>

请参阅以下此调用示例：

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

有关 [https://www.hl7.org/fhir/DSTU2/Condition.html](https://www.hl7.org/fhir/DSTU2/Condition.html) 此字段集的其他详细信息，请参阅 。

## <a name="encounter"></a>Encounter

这些是最小必填字段，这些字段是 US Core Encounter 配置文件"必须包含"字段的子集：

 - 状态
 - Type[0]。编码[0]。显示

此外，US Core Encounter 配置文件的"必须支持"字段中的以下字段

 - Period.Start
 - Location[0]。Location.Display

资源搜索使用 GET 方法和以下参数：

 - patient=\<patient id>
 - _sort：desc=\<field ex. date>
 - _count=\<max results>

目标是能够检索患者上次已知的位置。 每次遇到都引用一个位置资源。 引用还应包括位置的显示字段。 请参阅以下此调用的示例。

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

有关 [https://www.hl7.org/fhir/DSTU2/Encounter.htm](https://www.hl7.org/fhir/DSTU2/Encounter.htm) 此字段集的其他详细信息，请参阅 。

## <a name="allergyintolerance"></a>管理障碍

这些是最小必填字段，这些字段是 ArgonautAutyIntolerance 配置文件的子集：

 - Code.Text
 - Code.Code[0]。显示
 - 状态

除了 Argonaut 字段之外，为了获得出色的用户体验，Patients 应用还会读取以下字段：

 - RecordedDate
 - Note.Text
 - Reaction[..]。内容.文本
 - Reaction[..]。一切[..]。文本
 - Text.Div

资源搜索使用 GET 方法和以下参数：

 - Patient =  \<patient id>

请参阅以下此调用示例：

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

有关 [https://www.hl7.org/fhir/DSTU2/AllergyIntolerance.html](https://www.hl7.org/fhir/DSTU2/AllergyIntolerance.html) 此字段集的其他详细信息，请参阅 。

## <a name="medication-order"></a>药物订单

这些是最小必填字段，这些字段是 Argonaut 的一部分"一文""Order"配置文件：

 - DateWritten
 - 管理程序.Display
 - 如果参考， (显示) 
 - 药物.文本 (概念) 

除了 Argonaut 字段之外，为了获得出色的用户体验，Patients 应用还可以读取以下字段：

 - DateEnded
 - 一文
 - Text.Div

资源搜索使用 GET 方法和以下参数：

 - patient=\<patient id>
 - _count=\<max results>

请参阅以下此调用示例：

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

有关 [https://www.hl7.org/fhir/DSTU2/MedicationOrder.html](https://www.hl7.org/fhir/DSTU2/MedicationOrder.html) 此字段集的其他详细信息，请参阅 。

## <a name="coverage"></a>覆盖范围

这些是最小必填字段，US Core 或 Argonaut 配置文件未涵盖这些字段：

 - 支付方

资源搜索使用 GET 方法和以下参数：

 - patient=\<patient id>

请参阅以下此调用示例：

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
    
有关 [https://www.hl7.org/fhir/DSTU2/Coverage.html](https://www.hl7.org/fhir/DSTU2/Coverage.html) 此字段集的其他详细信息，请参阅 。

## <a name="location"></a>位置

此资源仅用于对 Encounter 资源 [的引用](#encounter) 。

有关 [https://www.hl7.org/fhir/DSTU2/Location.html](https://www.hl7.org/fhir/DSTU2/Location.html) 此字段集的其他详细信息，请参阅 。
