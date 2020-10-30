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
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: 12833ea55977cf7e8d18ee5c10b1f17d898b27b3
ms.sourcegitcommit: beaaee10019f4eda746f348888a4a3c2aaa6f196
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2020
ms.locfileid: "48803480"
---
# <a name="dstu2-interface-specification"></a>DSTU2 接口规范

> [!NOTE]
> 2020年10月30日，患者应用已停用，并已由团队中的 " [列表" 应用](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) 取代。 患者应用数据存储在支持团队的 Office 365 组的组邮箱中。 与病人应用关联的所有数据都将保留在此组中，但不能再通过用户界面进行访问。 用户可以使用 " [列表" 应用](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db)重新创建其列表。
>
>利用 "列表"，医疗保健组织中的 "护理团队" 可以创建各种方案的患者列表，包括从倒圆角和 interdisciplinary 团队会议到常规患者监控。 查看列表中的患者模板以开始使用。 若要了解有关如何管理组织中的列表应用的详细信息，请参阅 [管理列表应用](../../manage-lists-app.md)。

设置或重新配置 FHIR 服务器以处理 Microsoft 团队患者应用需要了解应用需要访问的数据。 FHIR 服务器必须使用以下资源的捆绑包支持发布请求：

- [档案](#patient)
- [知识产权](#observation)
- [条件](#condition)
- [产生](#encounter)
- [过敏症 intolerance](#allergyintolerance)
- [内](#coverage)
- [药物订货](#medication-order)
- [位置](#location)

> [!NOTE]
> 患者资源是唯一必需的资源 (不会加载应用程序。 但是，建议合作伙伴针对 Microsoft 团队患者应用的最佳最终用户体验，针对以下提供的针对以上提及的所有资源提供支持。

来自 Microsoft 团队患者应用的来自多个资源的查询发布捆绑 (对 FHIR 服务器 URL 的请求的批处理) 。 服务器处理每个请求，并返回每个请求所匹配的资源的捆绑包。 有关详细信息和示例，请参阅 [https://www.hl7.org/fhir/DSTU2/http.html#transaction](https://www.hl7.org/fhir/DSTU2/http.html#transaction) 。

所有以下 FHIR 资源应可通过直接资源参考访问。

## <a name="conformance-minimum-required-field-set"></a>一致性最低要求字段集

 FHIR 服务器必须实现一致性声明，才能为我们提供其功能的实际摘要。 我们期望 DSTU2 FHIR 服务器中的以下参数：

 - 余下

    - 众
    - 相交
    - 资源：类型
    - 安全性： [OAuth uri 的扩展](https://hl7.org/fhir/extension-oauth-uris.html)
   
 - FhirVersion (我们的代码需要此内容，以了解我们支持多个版本时应透视到的版本。 ) 

[https://www.hl7.org/fhir/dstu2/conformance.html](https://www.hl7.org/fhir/dstu2/conformance.html)有关此字段集的其他详细信息，请参阅。

## <a name="patient"></a>档案

以下是 " [Argonaut" 患者档案](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-patient.html) 字段子集的最少必填字段：

 - 名称。家庭
 - 名称。给定
 - 性别
 - BirthDate
 - MRN (标识符) 

除了 Argonaut 字段，为患者应用提供出色的用户体验还会读取以下字段：

 - 名称。使用
 - 名称。前缀
 - CareProvider (对患者资源的此参考应包括以下示例中所示的显示字段。 ) 

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

资源搜索在/Patient/_search 使用 POST 方法，并使用以下参数：

 - 标识号
 - 系列：包含 = (搜索其系列名称包含值的所有患者。 ) 
 - 给定 =\<substring>
 - 名称 =\<substring>
 - 出生日期 = (完全匹配) 
 - \_计数 (应返回的最大结果数)  <br> 该响应应包含作为搜索结果返回的记录的总数， \_ PatientsApp 将使用该计数来限制返回的记录数。
 - 标识符 =\<mrn>

目标是能够搜索和筛选患者，如下所示：

- ID：这是 FHIR 中的每个资源具有的资源 ID。
- MRN：这是临床人员将知道的患者的实际标识符。 我们理解此 MRN 基于 FHIR 中的标识符资源内的标识符类型
- 名称
- Birthdate

请参阅下面的此通话示例。

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

[https://www.hl7.org/fhir/DSTU2/Patient.html](https://www.hl7.org/fhir/DSTU2/Patient.html)有关此字段集的其他详细信息，请参阅。

## <a name="observation"></a>知识产权

以下是最少的必填字段，这些字段是 Argonaut 的重要符号配置文件的子集：

 - 有效 (日期时间或期间) 
 - 编码代码
 - ValueQuantity 值

除了 Argonaut 字段，为患者应用提供出色的用户体验还会读取以下字段：

 - 代码编码。显示
 - ValueQuantity 单位

如果使用组件观测值，则相同的逻辑适用于每个组件观察。

资源搜索使用 GET 方法和以下参数：

 - 患者 =\<patient id\>
 - 排序： desc =\<field ex. date\>

目标是能够检索患者的最新重要标志 [VitalSigns] (观察？ ) 。

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

[https://www.hl7.org/fhir/DSTU2/Observation.html](https://www.hl7.org/fhir/DSTU2/Observation.html)有关此字段集的其他详细信息，请参阅。

## <a name="condition"></a>条件

下面是 [Argonaut 条件配置文件](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-condition.html)子集的最少必填字段：

1. 代码。编码 [0]。画面

除了 Argonaut 字段外，还可以为患者应用提供出色的用户体验，还可以读取以下字段：

 - 录制日期
 - 严重性

资源搜索使用 GET 方法和以下参数：

 - 患者 =\<patient id>
 - _count =\<max results>

请参阅下面的此呼叫示例：

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

[https://www.hl7.org/fhir/DSTU2/Condition.html](https://www.hl7.org/fhir/DSTU2/Condition.html)有关此字段集的其他详细信息，请参阅。

## <a name="encounter"></a>产生

以下是最少必填字段，这些字段是 "美国核心" 基本配置文件 "必须具有" 字段的子集：

 - 状态栏
 - 键入 [0]。编码 [0]。画面

此外，美国核心的以下字段会遇到配置文件的 "必须支持" 字段

 - 句号。开始
 - 位置 [0]。位置。显示

资源搜索使用 GET 方法和以下参数：

 - 患者 =\<patient id>
 - _sort： desc =\<field ex. date>
 - _count =\<max results>

目标是能够检索患者的最后一个已知位置。 每个遇到的都引用一个位置资源。 该引用还应包含位置的显示字段。 请参阅下面的此通话示例。

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

[https://www.hl7.org/fhir/DSTU2/Encounter.htm](https://www.hl7.org/fhir/DSTU2/Encounter.htm)有关此字段集的其他详细信息，请参阅。

## <a name="allergyintolerance"></a>AllergyIntolerance

以下是最少的必填字段，它们是 Argonaut AllergyIntolerance 配置文件的子集：

 - 代码。文本
 - 代码。编码 [0]。画面
 - 状态栏

除了 Argonaut 字段，为患者应用提供出色的用户体验还会读取以下字段：

 - RecordedDate
 - 备注。文本
 - 反应 [...]。物质。文本
 - 反应 [...]。表现形式 [...]。文本
 - 文本 Div

资源搜索使用 GET 方法和以下参数：

 - 患者 =  \<patient id>

请参阅下面的此呼叫示例：

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

[https://www.hl7.org/fhir/DSTU2/AllergyIntolerance.html](https://www.hl7.org/fhir/DSTU2/AllergyIntolerance.html)有关此字段集的其他详细信息，请参阅。

## <a name="medication-order"></a>药物订货

以下是最少的必填字段，它们是 Argonaut MedicationOrder 配置文件的子集：

 - DateWritten
 - Prescriber 显示
 - 药物。如果引用) ，则显示 (
 -  () 概念的 "药物" 文本

除了 Argonaut 字段外，还可以为患者应用提供出色的用户体验，还可以读取以下字段：

 - DateEnded
 - DosageInstruction
 - 文本 Div

资源搜索使用 GET 方法和以下参数：

 - 患者 =\<patient id>
 - _count =\<max results>

请参阅下面的此呼叫示例：

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

[https://www.hl7.org/fhir/DSTU2/MedicationOrder.html](https://www.hl7.org/fhir/DSTU2/MedicationOrder.html)有关此字段集的其他详细信息，请参阅。

## <a name="coverage"></a>内

以下是 "最少必填字段"，不包含在美国 Core 或 Argonaut 配置文件中：

 - Payor

资源搜索使用 GET 方法和以下参数：

 - 患者 =\<patient id>

请参阅下面的此呼叫示例：

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
    
[https://www.hl7.org/fhir/DSTU2/Coverage.html](https://www.hl7.org/fhir/DSTU2/Coverage.html)有关此字段集的其他详细信息，请参阅。

## <a name="location"></a>位置

此资源仅用作 " [遇到](#encounter) " 资源的参考。

[https://www.hl7.org/fhir/DSTU2/Location.html](https://www.hl7.org/fhir/DSTU2/Location.html)有关此字段集的其他详细信息，请参阅。
