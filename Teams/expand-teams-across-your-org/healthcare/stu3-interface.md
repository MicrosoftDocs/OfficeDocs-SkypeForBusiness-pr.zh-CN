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
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Healthcare
appliesto:
- Microsoft Teams
ms.reviewer: anach
description: 了解如何将电子健康记录集成到 Microsoft Teams 应用和 STU3 接口规范中。
ms.custom: seo-marvel-apr2020
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: 64fc61072510942b67d51542095a927e7e67c697
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/26/2021
ms.locfileid: "58582326"
---
# <a name="stu3-interface-specification"></a>STU3 接口规范

> [!NOTE]
> 从 2020 年 10 月 30 日起，"患者"应用已停用，并替换为 Teams [列表](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) 应用。 患者应用数据存储在支持团队的 Office 365 组的组邮箱中。 与该患者应用关联的所有数据将保留在该组，但无法再通过用户界面访问。 用户可通过"列表"应用或 [重新创建](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db)。
>
>借助列表，医疗保健组织中的护理团队可针对各种方案创建患者列表，提供圆形和内联团队会议、常规患者监视等。 查看列表的"患者"模板以开始使用。 若要深入了解如何在组织中管理列表应用，请参阅" [列表应用管理](../../manage-lists-app.md)。

设置或重新配置 FHIR 服务器以使用 Microsoft Teams患者应用需要了解应用需要访问哪些数据。 FHIR 服务器必须使用捆绑包支持以下资源的 POST 请求：

- [Patient](#patient)
- [观察](#observation)
- [条件](#condition)
- [Encounter](#encounter)
- [仇恨者](#allergyintolerance)
- [覆盖范围](#coverage)
- [药物 (](#medication-request) 替代 PatientsApp) DSTU2 版本中的一种药物) 
- 位置 (此资源所需信息的位置信息可包含在"遇到") 

> [!NOTE]
> 患者资源是唯一必需的资源 (，如果没有它，应用将完全不加载) ;但是，建议合作伙伴根据下面提供的规范实现对上述所有资源的支持，以获得最佳患者应用最终用户Microsoft Teams体验。

来自 Microsoft Teams Patients 应用的查询针对多个资源应发布一个捆绑包 (BATCH) FHIR 服务器 URL 的请求。 服务器应处理每个请求并返回每个请求匹配的资源捆绑包。 有关详细信息和示例，请参阅 [https://www.hl7.org/fhir/STU3/http.html#transaction](https://www.hl7.org/fhir/STU3/http.html#transaction) 。

## <a name="capability-statement"></a>功能语句

这些是最小必填字段：

 - REST

    - 模式
    - 交互
    - 资源：类型
    - 安全性 [：OAuth URI 扩展](https://hl7.org/fhir/extension-oauth-uris.html)
    
 - FhirVersion (我们的代码要求它了解应该透视到哪个版本) 

有关 [https://www.hl7.org/fhir/stu3/capabilitystatement.html](https://www.hl7.org/fhir/stu3/capabilitystatement.html) 此字段集的其他详细信息，请参阅 。

## <a name="patient"></a>Patient

下面是最小必填字段，这些字段是 Argonaut 患者配置文件字段的子集：

 - Name.Given
 - Name.Family
 - 性别
 - BirthDate
 - MRN (标识符) 

除了 [Argonaut](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-patient.html)字段之外，为了获得出色的用户体验，Patients 应用还可以读取以下字段：

 - Name.Use
 - Name.Prefix
 - [GeneralPractitioner] - GeneralPractitioner 引用应仅包含在"患者" (显示字段中) 

资源搜索使用 /Patient/_search 的 POST 方法以及以下参数：

 - id
 - family= (搜索其家庭名称包含其值) 
 - given=\<substring>
 - birthdate= (完全匹配) 
 - gender= (值是管理性别差异之一) 
 - \_count (应返回的结果的最大)  <br> 响应应包含搜索结果返回的记录总数，并且 PatientsApp 将用来限制返回 \_ 的记录数。
 - identifier=\<mrn>

目标是能够按以下条件搜索和筛选患者：

- ID：这是 FHIR 中每个资源具有的资源 ID。
- MRN：这是患者的实际标识符，该患者是医疗人员会知道的信息。 我们知道，此 MRN 基于 FHIR 中标识符资源内的标识符类型。
- 名称
- Birthdate

请参阅以下调用示例：

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

有关 [https://hl7.org/fhir/stu3/patient.html](https://hl7.org/fhir/stu3/patient.html) 此字段集的其他详细信息，请参阅 。

## <a name="observation"></a>观察

这些是最小必填字段，这些字段是 [Argonaut Vital-Signs配置文件 的子集](https://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-vitalsigns.html)。

 - 有效 (日期时间或时间段) 
 - Code.Code.Code
 - ValueQuantity.Value

除了 Argonaut 字段之外，为了获得出色的用户体验，Patients 应用还可以读取以下字段：

 - Code.Code.Display
 - ValueQuantity.Unit

资源搜索使用 GET 方法和以下参数：

 - patient=\<patient id>
 - _sort=-date
 - 类别 (查询"category=vital-signs") 检索重要符号列表。

请参考以下调用示例：

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

有关 [https://www.hl7.org/fhir/stu3/observation.html](https://www.hl7.org/fhir/stu3/observation.html) 此字段集的其他详细信息，请参阅 。

## <a name="condition"></a>条件

下面是最小必填字段，这些字段是 [Argonaut 条件配置文件 的子集](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-condition.html)。

 - Code.Code[0]。显示

除了 Argonaut 字段之外，为了获得出色的用户体验，Patients 应用还可以读取以下字段：

 - AssertedDate
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

有关 [https://hl7.org/fhir/stu3/condition.html](https://hl7.org/fhir/stu3/condition.html) 此字段集的其他详细信息，请参阅 。

## <a name="encounter"></a>Encounter

这些是最小必填字段，这些字段是" [美国核心](https://hl7.org/fhir/us/core/2018Jan/StructureDefinition-us-core-encounter.html) 遇到"配置文件"必须具有"字段的) 。

 - 状态
 - Type[0]。编码[0]。显示

此外，US Core Encounter 配置文件的"必须支持"字段中的以下字段：

 - Period.Start
 - Location[0]。Location.Display

资源搜索使用 GET 方法和以下参数：

 - patient=\<patient id>
 - _sort：desc=\<field ex. date>
 - _count=\<max results>

目标是能够检索患者上次已知的位置。 每次遇到都引用一个位置资源。 引用还应包括位置的显示字段。

有关 [https://hl7.org/fhir/stu3/encounter.html](https://hl7.org/fhir/stu3/encounter.html) 此字段集的其他详细信息，请参阅 。

## <a name="allergyintolerance"></a>管理障碍

这些是最小必填字段，这些字段是 [ArgonautAutyIntolerance 配置文件的子集](https://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-allergyintolerance.html) ：

 - Code.Text
 - Code.Code[0]。显示
 - ClinicalStatus/VerificationStatus (读取这两) 

除了 Argonaut 字段之外，为了获得出色的用户体验，Patients 应用还可以读取以下字段：

 - AssertedDate
 - Note.Text
 - 反应
    - 实体 (一个编码元素) 
    - 一 (一个编码元素的) 

资源搜索使用 GET 方法和以下参数：

 - Patient =  \<patient id>

请参阅以下调用示例： 

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

有关 [https://hl7.org/fhir/stu3/allergyintolerance.html](https://hl7.org/fhir/stu3/allergyintolerance.html) 此字段集的其他详细信息，请参阅 。

## <a name="medication-request"></a>药物请求

这些是最小必填字段，这些字段是 ["美国核心药物请求"配置文件的子集](http://www.hl7.org/fhir/us/core/StructureDefinition-us-core-medicationrequest.html)：

 - 如果参考， (显示) 
 - 如果 CodableConcept (，将发送一) 
 - AuthoredOn
 - Requester.Agent.Display

除了"US Core"字段之外，为了获得出色的用户体验，Patients 应用还可以读取以下字段：

 - 一文[..]。文本
 - 文本

资源搜索使用 GET 方法和以下参数：

 - patient=\<patient id>
 - _count=\<max results>

有关 [https://www.hl7.org/fhir/medicationrequest.html](https://www.hl7.org/fhir/medicationrequest.html) 此字段集的其他详细信息，请参阅 。

## <a name="coverage"></a>覆盖范围

这些是最小必填字段，US Core 或 Argonaut 配置文件未涵盖这些字段：

 - 分组，至少包含一个元素
    - GroupDisplay
    - PlanDisplay
 - Period
 - SubscriberId

资源搜索使用 GET 方法和以下参数：

 - Patient = \<patient id>

有关 [https://hl7.org/fhir/stu3/coverage.html](https://www.hl7.org/fhir/medicationrequest.html) 此字段集的其他详细信息，请参阅 。
