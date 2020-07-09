---
title: 이벤트 구동 보존
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: 이 항목에서는 Microsoft 365 REST API를 사용하여 이벤트를 통한 보존을 자동화하는 비즈니스 프로세스 흐름을 설정하는 방법에 대해 설명합니다.
ms.openlocfilehash: c97106597733460caeab8d1d398ff81e23dd2727
ms.sourcegitcommit: dc5de2064706137256307f100b8dc61e9797bd1c
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/07/2020
ms.locfileid: "45068117"
---
# <a name="automate-event-based-retention"></a>이벤트 기반 보존 자동화

>*[보안 및 규정 준수를 위한 Microsoft 365 라이선싱 지침](https://aka.ms/ComplianceSD)*

The explosion of content in organizations and how it can become ROT (redundant, obsolete, trivial) is serious business. To continue to meet legal, business, and regulatory compliance challenges, organizations must be able to keep and protect important information and quickly find what’s relevant. Retaining only important, pertinent information is key to an organization's success.

To help meet this need, organizations can take advantage of retention solutions in the Office 365 Security & Compliance Center. Retention can be triggered by using [retention labels](labels.md). A retention label has the option to [base the retention period on a specific event](event-driven-retention.md). Typically, the retention period is based on a known date, such as the creation date or last modified date for the content. However, organizations also have requirements to dispose of content based on the occurrence of an event, such as seven years after an employee leaves an organization.

To ensure compliant disposal of content, it's imperative to know when an event takes place. With the volume of content increasing rapidly, it's becoming challenging to retain and dispose content in a timely and compliant manner.

Event-based retention solves this problem. This topic explains how to set up your business process flows to automate retention through events by using the Microsoft 365 REST API.

## <a name="about-event-based-retention"></a>이벤트 기반 보존에 대한 설명

An organization can be small, medium, or large. The number of business documents, legal documents, employee files, contracts, and product documents that get created and managed on a day-to-day basis is increasing dramatically.

For example, each day, tens and hundreds of employees are joining and leaving organizations. The HR department continues to create, update, or delete employee-related documents as per business requirements. This process is subject to the different retention policies outlined for the business:

- **The period of retention for content can be a known date** such as the date the content was created, last modified, or labeled. For example, you might retain documents for seven years after they're created and then delete them.

- **The period of retention of content can also be an unknown date**. For example, with retention labels, you can also base a retention period on when a specific type of event occurs, such as an employee leaving the organization.

The event triggers the start of the retention period, and all content with a label applied for that type of event get the label's retention actions enforced on them. This is called event-based retention. To learn more, see [Overview of event-driven retention](event-driven-retention.md).

## <a name="set-up-event-based-retention"></a>이벤트 기반 보존 설정

이 절에서는 콘텐츠를 보존하기 전에 수행해야 할 작업에 대해 설명합니다.

### <a name="identify-roles"></a>역할 확인

레코드 관리 작업을 수행하고 효과적이고 효율적인 비즈니스 문서 보존을 담당하는 조직 안의 다양한 역할을 식별합니다.

  | 가상 사용자 | 역할 |
  | - | - |
  | 관리 | SharePoint에 보존 이벤트 유형, 보존 레이블 및 레코드 리포지토리를 만듭니다. |
  | 레코드 관리자                                  | 보존 정책과 보존 일정 지침 및 준수 세부사항을 제공합니다.   |
  | 시스템 관리자(회사)                          | Microsoft 365에서 작동하도록 외부 시스템을 설정하고 관리합니다.                       |
  | 정보 근로자                               | 비즈니스 프로세스(HR, 재무, IT 등)의 수명 주기를 관리합니다.                 |

### <a name="set-up-the-security--compliance-center"></a>보안 및 준수 센터 설정
  
1. 규정 준수 관리자가 이벤트 유형(예 &ndash; 직원 퇴사, 계약 만료 또는 제품 제조 종료)을 만듭니다. ([이벤트 기반 보존](event-driven-retention.md)의 단계별 프로세스 참조.)
    
2. 규정 준수 관리자가 이벤트를 기반으로 보존 레이블을 만들고 레이블을 이벤트 유형과 연결합니다.
    
    보존 레이블에 대해 다음과 같이 4종류의 트리거가 있습니다.
            
    1. 만든 날짜
                
    2. 마지막으로 수정한 날짜
                
    3. 레이블 날짜(콘텐츠 레이블이 지정 된 때)
                
    4. 이벤트 기반
    
3. 규정 준수 관리자가 보존 레이블을 게시합니다.

### <a name="set-up-sharepoint"></a>SharePoint 설정
   
레코드 저장소를 만들기 위해 규정 준수 관리자는 다음 작업을 수행합니다.

1. SharePoint 사이트를 생성합니다.

2. 다음 중 하나를 수행합니다.
        
   - Creates a SharePoint library: Set event-based label at the library level. For more information, see [Applying a default retention label to all content in a SharePoint library, folder, or document set](labels.md#applying-a-default-retention-label-to-all-content-in-a-sharepoint-library-folder-or-document-set).
          
   - SharePoint에서 문서 집합을 설정합니다. 자세한 내용은 [문서 집합 소개](https://support.microsoft.com/ko-KR/office/introduction-to-document-sets-3dbcd93e-0bed-46b7-b1ba-b31de2bcd234)를 참조합니다.
      
3. 각 직원 문서 집합에 자산 ID를 할당합니다. 자산 ID는 조직에서 사용하는 제품 이름 또는 코드입니다. 예를 들어 직원 번호는 자산 ID가 될 수 있습니다. 자산 ID를 폴더에 할당하면 해당 폴더에 있는 모든 항목이 자동으로 동일한 자산 ID를 상속합니다. 즉, 동일한 이벤트로 모든 항목의 보존 기간을 트리거할 수 있습니다.

## <a name="ways-to-trigger-event-based-retention"></a>이벤트 기반 보존을 트리거하는 방법

두 가지 방법으로 이벤트 기반 보존을 트리거할 수 있습니다.

- **관리자 센터 UI 사용** 한 번에 적은 콘텐츠를 유지하는 데 사용할 수 있거나 매월 또는 매년과 같이 보존을 트리거하는 빈도가 자주 없는 프로세스입니다. 이 방법에 자세한 내용은 [이벤트 기반 보존의 개요](event-driven-retention.md)를 참조하세요. 그러나 보존을 트리거하는 이 방법은 시간이 오래 걸리고 오류가 발생하기 쉬워 확장성을 저해합니다. 따라서 보존을 트리거하는 자동화된 원활한 솔루션을 통해 데이터 보안 및 규정 준수를 개선할 수 있습니다.

- **Using a M365 REST API** This process can be used when large amounts of content are to be retained at a time and/or the frequency to trigger retention is often such as daily or weekly. The flow detects when an event occurs in your line-of-business system, and then automatically creates a related event in the Security & Compliance Center. You don't need to manually create an event in the UI each time one occurs.

REST API를 사용할 수 있는 옵션은 다음과 같이 두 가지가 있습니다.

- **Microsoft Flow 또는 유사한 응용 프로그램**을 이벤트 발생을 자동으로 트리거하는 데 사용할 수 있습니다. Microsoft Flow는 다른 시스템에 연결하기 위한 조정자입니다. Microsoft Flow를 사용하는 경우 사용자 지정 솔루션이 필요하지 않습니다.

- **REST API를 호출하는 PowerShell 또는 HTTP 클라이언트** PowerShell (버전 6 이상)을 사용하여 Microsoft 365 REST API를 호출하여 이벤트를 만듭니다. 

Rest API는 서비스 자원에 대한 작성/검색/갱신/삭제 액세스를 제공하는 HTTP 조작(메소드) 세트를 지원하는 서비스 엔드 포인트입니다. 자세한 정보는 [REST API 요청/응답 구성 요소](https://docs.microsoft.com/rest/api/gettingstarted/#components-of-a-rest-api-requestresponse)를 참조하세요. 이 경우 Microsoft 365 REST API를 사용하여 POST 및 GET 메서드를 사용하여 이벤트를 만들고 검색할 수 있습니다.

## <a name="example-scenarios"></a>예제 시나리오

다음과 같은 시나리오를 고려해 봅시다.

### <a name="scenario-1-employees-leaving-the-organization"></a>시나리오 1: 조직을 떠나는 직원 

조직은 직원 한 명당 수많은 직원 관련 문서를 작성하고 저장합니다. 이 서류들은 각 직원의 고용 기간 동안 관리되고 유지됩니다. 그러나 직원이 조직을 떠나거나 고용이 해지되는 경우 조직은 법률 및 비즈니스 요구사항에 따라 해당 직원의 문서를 규정된 기간 동안 보유해야 합니다.

이제 여러 명의 직원이 매일 조직을 떠나는 경우 조직에서는 매일 수천 개의 문서가 아니라도 수백 가지의 보존 시계를 트리거해야 합니다.

이 외에도 직원 보유 기간은 직원 기록의 유형에 따라 직원의 근무 종료일자 + 일수, 개월수 또는 연수로 계산해야 합니다. 예를 들어, 동일한 직원에 대한 근로자 보상과 수당 서류의 보존 기간이 서로 다를 수 있습니다.

아래 다이어그램은 단일 이벤트와 연관된 레이블이 어떻게 여러 개가 존재할 수 있는지 보여줍니다. 여기서 근로자 보상 레이블 아래의 모든 파일과 직원 혜택 레이블 아래의 모든 파일은 조직을 떠나는 직원이라는 단일 이벤트와 연관됩니다. 이러한 서로 다른 파일에는 서로 다른 보존 시계가 있습니다.  따라서 직원이 조직을 떠날 때 각 레이블 내의 파일에는 다른 보존 기간이 적용됩니다. 각 직원의 개별 파일 유형 또는 레이블에 대해 이러한 다양한 보존 시계를 트리거하는 것은 매우 어려운 작업입니다. 여러 직원에 대해 이 작업을 수행한다고 가정해 보십시오.

![이벤트 유형, 이벤트 및 레이블 다이어그램](../media/automate-event-driven-retention-event-diagram-employee-leaving.png)

따라서 여러 직원에 대해 서로 다른 보존 시계를 트리거하는 자동화된 프로세스는 시간을 절약해주고 오류가 없으며 매우 효율적입니다.

**이 시나리오에 대한 이벤트 기반 자동 보존 구성하기:**

![조직을 떠나는 직원 시나리오에 대한 역할 및 작업 다이어그램](../media/automate-event-driven-retention-employee-termination-diagram.png)

  - 관리자는 문서 집합에 Jane Doe, John Smith와 같은 직원 폴더를 생성합니다.

  - 관리자는 수당, 급여, 근로 보상 등과 같은 직원 파일을 각 직원 폴더에 추가합니다.

  - 관리자는 각 직원 폴더에 자산 ID를 할당합니다. 

  - SCC 관리자는 보안 및 준수 센터로 로그인합니다.

  - SCC 관리자가 “직원 퇴사”, “직원 채용” 이벤트와 같은 직원 관련 이벤트 유형을 만듭니다.

  - SCC 관리자가 “직원 보존” 레이블을 만듭니다.

  - 이 "직원 보존"레이블은 SharePoint의 직원 파일에 수동 또는 자동으로게시되고 적용됩니다.

  - Workday와 같은 HR 관리 시스템은 Microsoft Flow와 함께 정기적으로 실행되어 직원 파일을 관리할 수 있습니다.

  - 직원이 조직을 떠난 경우 Flow는 특정 직원의 파일에 대한 보존 시계를 시작할 M365 이벤트 기반 보존 REST API를 트리거합니다.

#### <a name="using-microsoft-flow"></a>Microsoft Flow 사용

1단계- Flow를 생성하여 Microsoft 365 REST API를 사용하는 이벤트를 만듭니다.

![Flow를 사용해 이벤트 만들기](../media/automate-event-driven-retention-flow-1.png)

![Flow를 사용해 REST API 호출하기](../media/automate-event-driven-retention-flow-2.png)

##### <a name="create-an-event"></a>이벤트 만들기

REST API를 호출하는 샘플 코드:

- **메서드**: POST
- **URL**: `https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent`
- **헤더**: Key = Content-Type, Value = application/atom+xml
- **Body**:
    
    ```xml
    <?xml version='1.0' encoding='utf-8' standalone='yes'?>
    
    <entry xmlns:d='http://schemas.microsoft.com/ado/2007/08/dataservices'
    
    xmlns:m='http://schemas.microsoft.com/ado/2007/08/dataservices/metadata'
    
    xmlns='http://www.w3.org/2005/Atom'>
    
    <category scheme='http://schemas.microsoft.com/ado/2007/08/dataservices/scheme' term='Exchange.ComplianceRetentionEvent' />
    
    <updated>9/9/2017 10:50:00 PM</updated>
    
    <content type='application/xml'>
    
    <m:properties>
    
    <d:Name>Employee Termination </d:Name>
    
    <d:EventType>99e0ae64-a4b8-40bb-82ed-645895610f56</d:EventType>
    
    <d:SharePointAssetIdQuery>1234</d:SharePointAssetIdQuery>
    
    <d:EventDateTime>2018-12-01T00:00:00Z </d:EventDateTime>
    
    </m:properties>
    
    </content>
    
    </entry>
    ```
- **인증**: 기본
- **사용자 이름**: "Complianceuser"
- **암호**: "Compliancepassword"


##### <a name="available-parameters"></a>사용 가능한 매개 변수


|매개 변수|설명|참고|
|--- |--- |--- |
|<d:Name></d:Name>|이벤트에 대해 고유한 이름을 제공하고,|후행 공백 및 다음 문자를 사용할 수 없습니다. % * \ & < \> \| # ? , : ;|
|<d:EventType></d:EventType>|이벤트 유형 이름(또는 Guid)을 입력합니다.|Example: “Employee termination”. Event type has to be associated with a retention label.|
|<d:SharePointAssetIdQuery></d:SharePointAssetIdQuery>|“ComplianceAssetId:”와 직원 ID 입력|예제: "ComplianceAssetId:12345"|
|<d:EventDateTime></d:EventDateTime>|이벤트 날짜 및 시간|형식: yyyy-MM-ddTHH:mm:ssZ, 예제: 2018-12-01T00:00:00Z
|

##### <a name="response-codes"></a>응답코드

| 응답코드 | 설명       |
| ----------------- | --------------------- |
| 302               | 리디렉션              |
| 201               | 만든 날짜               |
| 403               | 인증 실패  |
| 401               | 인증 실패 |

##### <a name="get-events-based-on-time-range"></a>이벤트를 시간 범위를 기준으로 설정

- **메서드**: GET

- **URL**: `https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent?BeginDateTime=2019-01-11&EndDateTime=2019-01-16`

- **헤더**: Key = Content-Type, Value = application/atom+xml

- **인증**: 기본

- **사용자 이름**: "Complianceuser"

- **암호**: "Compliancepassword"


##### <a name="response-codes"></a>응답코드

| 응답코드 | 설명                   |
| ----------------- | --------------------------------- |
| 200               | 확인, atom + xml의 이벤트 목록 |
| 404               | 찾을 수 없음                         |
| 302               | 리디렉션                          |
| 401               | 인증 실패              |
| 403               | 인증 실패             |

##### <a name="get-an-event-by-id"></a>이벤트 ID로 가져오기

- **메서드**: GET

- **URL**: `https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent('174e9a86-74ff-4450-8666-7c11f7730f66')`

- **헤더**: Key = Content-Type, Value = application/atom+xml

- **인증**: 기본

- **사용자 이름**: "Complianceuser"

- **암호**: "Compliancepassword"



##### <a name="response-codes"></a>응답코드

| 응답코드 | 설명                                      |
| ----------------- | ---------------------------------------------------- |
| 200               | 확인, 응답 본문에 atom + xml 이벤트가 포함되어 있습니다. |
| 404               | 찾을 수 없음                                            |
| 302               | 리디렉션                                             |
| 401               | 인증 실패                                 |
| 403               | 인증 실패                                |

##### <a name="get-an-event-by-name"></a>이벤트 이름으로 받기

- **메서드**: GET

- **URL**: `https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent`

- **헤더**: Key = Content-Type, Value = application/atom+xml

- **인증**: 기본

- **사용자 이름**: "Complianceuser"

- **암호**: "Compliancepassword"


##### <a name="response-codes"></a>응답코드

| 응답코드 | 설명                                      |
| ----------------- | ---------------------------------------------------- |
| 200               | 확인, 응답 본문에 atom + xml 이벤트가 포함되어 있습니다. |
| 404               | 찾을 수 없음                                            |
| 302               | 리디렉션                                             |
| 401               | 인증 실패                                 |
| 403               | 인증 실패                                |

#### <a name="using-powershell-version-6-or-later-or-any-http-client"></a>PowerShell(버전 6 이상) 또는 모든 HTTP 클라이언트를 사용

1단계: PowerShell에 연결합니다.

2단계: 다음 스크립트를 실행합니다.

```powershell
param([string]$baseUri)

$userName = "UserName"

$password = "Password"

$securePassword = ConvertTo-SecureString $password -AsPlainText -Force

$credentials = New-Object System.Management.Automation.PSCredential($userName, $securePassword)

$EventName="EventByRESTPost-$(([Guid]::NewGuid()).ToString('N'))"

Write-Host "Start to create an event with name: $EventName"

$body = "<?xml version='1.0' encoding='utf-8' standalone='yes'?>

<entry xmlns:d='http://schemas.microsoft.com/ado/2007/08/dataservices'

xmlns:m='http://schemas.microsoft.com/ado/2007/08/dataservices/metadata'

xmlns='http://www.w3.org/2005/Atom'>

<category scheme='http://schemas.microsoft.com/ado/2007/08/dataservices/scheme' term='Exchange.ComplianceRetentionEvent' />

<updated>7/14/2017 2:03:36 PM</updated>

<content type='application/xml'>

<m:properties>

<d:Name>$EventName</d:Name>

<d:EventType>e823b782-9a07-4e30-8091-034fc01f9347</d:EventType>

<d:SharePointAssetIdQuery>'ComplianceAssetId:123'</d:SharePointAssetIdQuery>

</m:properties>

</content>

</entry>"

$event = $null

try

{

$event = Invoke-RestMethod -Body $body -Method 'POST' -Uri "$baseUri/ComplianceRetentionEvent" -ContentType "application/atom+xml" -Authentication Basic -Credential $credentials -MaximumRedirection 0

}

catch

{

$response = $_.Exception.Response

if($response.StatusCode -eq "Redirect")

{

$url = $response.Headers.Location

Write-Host "redirected to $url"

$event = Invoke-RestMethod -Body $body -Method 'POST' -Uri $url -ContentType "application/atom+xml" -Authentication Basic -Credential $credentials -MaximumRedirection 0

}

}

$event | fl *

```


#### <a name="verify-the-outcome-in-both-options"></a>두 옵션 모두에서 결과 확인하기

1단계: 보안 및 준수 센터로 이동

2단계: **정보 거버넌스**에서 **이벤트**를 선택합니다.

3단계: 이벤트가 생성되었는지 확인합니다.

마찬가지로 이벤트 기반 보존을 자동화하는 위의 옵션을 다음 시나리오에도 사용할 수 있습니다.

### <a name="scenario-2-contracts-expiring"></a>시나리오 2: 계약 만료

조직은 고객, 공급 업체, 파트너와의 단일 계약에 대한 레코드를 여러 개 가질 수 있습니다. 이러한 문서는 SharePoint와 같은 문서 라이브러리에 있을 수 있습니다. 계약이 끝나면 계약과 관련된 문서의 보존 기간에 대한 시작이 결정됩니다. 예를 들어 계약과 관련된 모든 레코드를 계약이 만료되는 시간으로부터 5년 동안 유지해야 합니다. 5년 보존 기간을 트리거하는 이벤트는 계약 만료입니다.

CRM(고객 관계 관리) 시스템은 Microsoft 365와 함께 작동하고 계약 문서의 보존을 트리거 할 수 있습니다.

**이 시나리오에 대한 이벤트 기반 자동 보존 구성하기:**

![계약 만료 시나리오에 대한 역할 및 작업 다이어그램](../media/automate-event-driven-retention-contract-expiration.png)

  - 관리자는 각 계약 유형별로 다양한 폴더가 있는 SharePoint 라이브러리를 만듭니다.

  - 관리자는 라이센스 계약, 개발 계약과 같은 계약 파일을 각 계약 폴더에 추가합니다.

  - 관리자는 각 계약 폴더에 자산 ID를 할당합니다.

  - SCC 관리자는 보안 및 준수 센터로 로그인합니다.

  - SCC 관리자가 “계약 생성”, “계약 만료” 등과 같은 계약 관련 이벤트 유형을 만듭니다.

  - SCC 관리자가 “계약 만료” 레이블을 만듭니다.

  - 이 "계약 만료 " 레이블은 SharePoint의 계약 파일에 수동 또는 자동으로 게시되고 적용됩니다.

  - 계약 관리 시스템은 Microsoft Flow 또는 이와 유사한 응용 프로그램과 함께 정기적으로 실행되어 계약 파일을 관리할 수 있습니다.

  - 계약이 만료되면 Microsoft Flow는 M365 이벤트 기반 보존 REST API를 트리거하여 특정 계약의 파일에 대한 보존 시계를 시작합니다.

### <a name="scenario-3-end-of-product-manufacturing"></a>시나리오 3: 제품 제조 종료

A manufacturing company that produces different lines of products creates many manufacturing specifications and pricing documents. When the product is no longer manufactured, all specifications and documents linked to this product need to be retained for a specific period after the end of the lifetime of the product.

ERP(Enterprise Resource Planning) 시스템은 Microsoft 365 및 Microsoft Flow와 함께 사용해 보존을 트리거할 수 있습니다.

**이 시나리오에 대한 이벤트 기반 자동 보존 구성하기:**

![제품 수명 주기 시나리오에 대한 역할 및 작업 다이어그램](../media/automate-event-driven-retention-product-lifecycle-expiration.png)

  - 관리자는 제품 1, 제품 2 등과 같이 문서 집합에 제품 폴더를 만듭니다.

  - 관리자는 제조 사양, 제품 가격, 제품 라이센스와 같은 제품 파일을 각 제품 폴더에 추가합니다.

  - 관리자는 각 제품폴더에 자산 ID를 할당합니다.

  - SCC 관리자는 보안 및 준수 센터로 로그인합니다.

  - SCC 관리자가 “제품 제조 시작”, “제품 제조 종료”와 같은 직원 관련 이벤트 유형을 만듭니다.

  - SCC 관리자가 “제품 제조 종료” 레이블을 만듭니다.

  - 이 "제품 제조 종료" 레이블은 SharePoint의 제품 파일에 수동 또는 자동으로 게시되고 적용됩니다.

  - ERP 시스템은 Microsoft Flow 또는 이와 유사한 응용 프로그램과 함께 정기적으로 실행되어 제품 파일을 관리할 수 있습니다.

  - 제품 제조가 끝나면 Microsoft Flow는 M365 이벤트 기반 보존 REST API를 트리거하여 특정 제품의 파일에 대한 보존 시계를 시작합니다.

## <a name="appendix"></a>부록

### <a name="using-redirect-302-response-results-to-call-the-rest-api"></a>Redirect 302 응답 결과를 이용하여 REST API 호출

1. REST API URL `https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent`을(를) 사용하여 POST 보존 이벤트 호출을 실행합니다.
    
    전역 관리자 권한이 필요합니다.

2. 응답코드를 확인하십시오. URL이 302인 경우 응답 헤더의 위치 속성에서 리디렉션된 URL을 가져옵니다.

3. 리디렉션된 URL을 사용하여 POST 보존 이벤트 호출을 다시 호출하십시오.

## <a name="credits"></a>크레딧

이 주제의 검토자:

Antonio Maio<br/>Microsoft Office 앱 및 서비스 MVP<br/> Antonio.Maio@Protiviti.com
