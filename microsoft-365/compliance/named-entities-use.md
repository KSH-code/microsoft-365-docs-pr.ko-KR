---
title: 데이터 손실 방지 정책에 명명된 엔터티 사용(미리 보기)
f1.keywords:
- CSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: Admin
search.appverid: MET150
ms.topic: article
f1_keywords:
- ms.o365.cc.UnifiedDLPRuleContainsSensitiveInformation
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
description: 다음 절차에 따라 데이터 손실 방지 정책에서 명명된 엔터티를 활용합니다.
ms.openlocfilehash: c1ee219594cc5406fc559ab9e9a489b1d6285af6
ms.sourcegitcommit: bf3965b46487f6f8cf900dd9a3af8b213a405989
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/02/2021
ms.locfileid: "60661899"
---
# <a name="use-named-entities-in-your-data-loss-prevention-policies-preview"></a>데이터 손실 방지 정책에 명명된 엔터티 사용(미리 보기)

> [!IMPORTANT]
> 명명된 엔터티 기능은 롤아웃 중으로, 사용 가능한 경우 테넌트에 표시됩니다. 콘텐츠 탐색기 및 DLP(데이터 손실 방지) 정책 작성 흐름에서 해당 정책을 검사합니다. 

사용을 시작하기 전에 [명명된 엔터티(미리 보기)에](named-entities-learn.md) 대한 자세한 내용을 읽어 읽습니다.

## <a name="before-you-begin"></a>시작하기 전에

### <a name="skusubscriptions-licensing"></a>SKU/구독 라이선싱

다음 구독 중 하나를 사용해야 합니다.

- 정보 보호 및 거버넌스
- Microsoft 365 E5 Compliance
- Office 365 E5
- Microsoft 365 E5

전체 라이선스에 대한 자세한 내용은 서비스 [설명을 참조하세요.](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#information-protection-data-classification-analytics-overview-content--activity-explorer)

### <a name="permissions"></a>사용 권한

DLP(데이터 손실 방지) 정책을 만들고 편집하는 데 사용하는 계정에 **DLP** 준수 관리 역할 권한이 있어야 합니다. 자세한 내용은 사용자에게 정책 준수 센터에 대한 액세스 [Office 365 부여를 참조하세요.](../security/office-365-security/grant-access-to-the-security-and-compliance-center.md)


## <a name="supported-locations"></a>지원되는 위치

명명된 엔터티 SITS 및 향상된 정책을 사용하여 이러한 위치에서 중요한 항목을 검색하고 보호할 수 있습니다.

- SharePoint 사이트
- OneDrive 계정
- Teams 채팅 및 채널 메시지

명명된 엔터티 SITS 및 향상된 정책은 지원되지 않습니다.

- 장치(Windows 10 끝점 장치)
- 사내 리포지토리

## <a name="create-and-edit-enhanced-policies"></a>향상된 정책 만들기 및 편집

DLP 정책을 만들거나 편집하려면 DLP 정책 만들기, 테스트 및 조정의 [절차를 사용 합니다.](create-test-tune-dlp-policy.md)

## <a name="workloads-and-services-that-support-named-entities"></a>명명된 엔터티를 지원하는 워크로드 및 서비스


- **Microsoft 3655 eDiscovery는** Substrate 서비스에서 명명된 엔터티의 사용을 지원합니다.
- **Microsoft Cloud App Security(MCAS)는** MCAS 정책에서 명명된 엔터티의 사용을 지원합니다.
- **내부자 위험 관리는** Substrate Services에서 명명된 엔터티의 사용을 지원합니다.
- **통신 규정 준수는** 전송 규칙 및 저장 데이터에서 명명된 Exchange 사용을 지원하지 않습니다.
- **MIG(Microsoft Information Governance)는** 전송 규칙 및 저장 데이터에서 명명된 Exchange 사용을 지원하지 않습니다.
 
### <a name="unified-dlp"></a>통합 DLP

|Workload/Services  |명명된 엔터티에 대한 공개 미리 보기 지원  |
|---------|---------|
|Office Win32 클라이언트 정책 팁    |지원되지 않음  |
|Office WAC 클라이언트 정책 팁    |지원         |
|OWA 정책 팁     |지원되지 않음         |
|Outlook 정책 팁     |지원되지 않음 |
|끝점(Windows 10)     |지원되지 않음  |
|Exchange 전송 규칙     |지원되지 않음 |
|비즈니스용 OneDrive 데이터 저장     |지원         |
|SharePoint 저장 시 온라인 데이터     |지원         |
|Teams 데이터 저장     |지원         |
|미사용 전자 메일 메시지 데이터     |지원되지 않음         |
|Microsoft Cloud App Security(MCAS)     |지원         |

### <a name="autolabeling"></a>자동레이블

|Workload/Services |명명된 엔터티에 대한 공개 미리 보기 지원  |
|---------|---------|
|Office 오프라인으로 Win32 클라이언트   |지원, 사용자가 레이블을 선택하고 수동으로 적용해야 합니다. |
|온라인 Office Win32 클라이언트|이전 신뢰 구성표로 지원 |
|Outlook 온라인   |이전 신뢰 구성표로 지원  |
|Office WAC 클라이언트     |지원 |
|OWA     |지원 |
|Exchange 전송     |지원되지 않음 |
|비즈니스용 OneDrive 데이터 저장     |지원 |
|SharePoint 저장 시 온라인 데이터|지원|
|AIP(Azure Information Protection) 스캐너|지원되지 않음|

## <a name="known-issues"></a>알려진 문제

|문제  |영향  |
|---------|---------|
|DLP 정책 팁(OWA, Outlook, Office Win32 클라이언트)     |   엔터티 조건이 있는 정책 팁은 "일치하지 않습니다."로 표시됩니다.      |
| 사용자 이름에 대한 아시아 언어 지원(중국어, 일본어, 한국어)    | 라틴어 기반 문자 집합에만 지원되는 명명된 엔터티(즉, 간지가 지원되지 않습니다.)        |
|장치 작업량(Endpoint)     | 워크로드로 지원되지 않습니다. 명명된 엔터티를 사용하여 작성 정책은 허용되지 않습니다.        |
|사내 리포지토리    | 워크로드로 지원되지 않습니다.|

## <a name="for-further-information"></a>자세한 내용은
<!-- - [Sensitive information type entity definitions](sensitive-information-type-entity-definitions.md)-->
- [명명된 엔터티(미리 보기)에 대해 자세히 알아보습니다.](named-entities-learn.md)
- [DLP 정책 생성, 테스트 및 조정](create-test-tune-dlp-policy.md)
- [서식 파일에서 DLP 정책 만들기](create-a-dlp-policy-from-a-template.md)
