---
title: Microsoft 365의 Advanced eDiscovery 솔루션 개요
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- m365-security-compliance
- m365solution-aed
- m365initiative-compliance
- m365solution-overview
search.appverid:
- MOE150
- MET150
description: Microsoft 365의 Advanced eDiscovery 솔루션에 대해 자세히 알아보십시오. 이 문서에서는 내부 및 외부 조사를 관리하는 데 도움이 되는 도구인 Microsoft 365의 Advanced eDiscovery에 대한 개요를 제공합니다. 또한 Advanced eDiscovery를 사용하여 법적 조사를 관리하는 비즈니스 이유에 대한 프레임을 제공합니다.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 0f6ae536f84190f81248bbf68ff66f438727e068
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50927660"
---
# <a name="overview-of-microsoft-365-advanced-ediscovery"></a>Microsoft 365 Advanced eDiscovery 개요

Microsoft 365의 Advanced eDiscovery 솔루션은 기존 Microsoft eDiscovery 및 분석 기능을 빌드합니다. Advanced eDiscovery는 조직의 내부 및 외부 조사에 응답하는 콘텐츠를 보존, 수집, 분석, 검토, 분석 및 내보내기 위한 종단 간 워크플로를 제공합니다. 또한 법률 팀에서 전체 법적 보유 알림 워크플로를 관리하여 사례에 관련된 보유자와 통신할 수 있습니다.

## <a name="advanced-ediscovery-capabilities"></a>고급 eDiscovery 기능

Advanced eDiscovery는 조직이 거주하는 데이터를 검색하여 법적 문제 또는 내부 조사에 대응하는 데 도움을 줄 수 있습니다. 관심 있는 사용자와 해당 데이터 원본을 식별하여 eDiscovery 워크플로를 원활하게 관리하고, 보류를 원활하게 적용하여 데이터를 보존한 다음 법적 보존 통신 프로세스를 관리할 수 있습니다. 원본에서 데이터를 수집하면 라이브 Microsoft 365 플랫폼을 검색하여 필요한 것을 빠르게 찾을 수 있습니다. 심층 인덱싱, 전자 메일 스레딩 및 중복에 가까운 검색과 같은 지능적인 기계 학습 기능도 관련 데이터 집합으로 대량의 데이터를 줄이는 데 도움이 됩니다.

다음 섹션에서는 이러한 Advanced eDiscovery 기능이 조직에 어떻게 도움이 되는지 설명합니다.

![고급 eDiscovery 기능](../media/advanced-ediscovery-capabilities.png)

### <a name="discover-and-collect-data-in-place"></a>데이터 검색 및 원본치 수집

일반적으로 여러 타사 eDiscovery 솔루션을 사용하는 조직에서는 처리를 위해 대량의 데이터를 Microsoft 365에서 복사하고 중복 데이터를 호스트해야 합니다. 이러한 요구는 관련 데이터를 찾는 데 필요한 시간 및 여러 솔루션 관리의 위험, 비용 및 복잡성을 증가합니다.

Microsoft 365의 Advanced eDiscovery를 사용하면 원본에서 데이터를 검색하고 Microsoft 365 보안 및 규정 준수 경계 내에서 데이터를 검색할 수 있습니다.  Advanced eDiscovery는 라이브 시스템에서 데이터를 원본으로 수집하여 원본으로 돌아가는 마찰을 줄이고 누락된 콘텐츠를 찾을 필요가 없는 불필요한 작업을 줄여주며, 기존 eDiscovery 솔루션에서 저널링이 진행될 때 자주 발생합니다.

Teams, Yammer, SharePoint Online, 비즈니스용 OneDrive 및 Exchange Online의 데이터에 대한 기본 검색 및 수집 기능은 데이터 검색을 더욱 향상합니다. 예를 들어 Advanced eDiscovery:

- Teams 대화를 재구성합니다(대화에서 개별 메시지를 반환하는 대신).

- 전자 메일 메시지 및 Teams 채팅에서 링크 또는 최신 첨부 파일을 사용하여 사용자와 공유되는 클라우드 기반 콘텐츠를 수집합니다.

- 수백 개의 비 Microsoft 365 파일 형식에 대한 기본 제공 지원이 있습니다.

- 데이터 커넥터에 의해 Microsoft 365에서 가져오고 보관하는 타사 원본(예: Bloomberg, Facebook, Slack 및 Zoom Meetings)에서 데이터를 [수집합니다.](archiving-third-party-data.md)

### <a name="manage-ediscovery-workflow-in-one-platform"></a>하나의 플랫폼에서 eDiscovery 워크플로 관리

Advanced eDiscovery를 사용하면 필요한 eDiscovery 솔루션의 수를 줄일 수 있습니다. Microsoft 365 내에서 발생하는 간소화된 종단-종단 워크플로를 제공합니다. Advanced eDiscovery를 사용하면 고유 및 공유 데이터 원본을 관심 있는 사용자(보좌관)에게 자동으로 매핑하고 분석 및 검토를 위해 수집하기 전에 잠재적으로 관련성 있는 데이터에 대한 보고 및 분석을 제공하여 관련 정보의 잠재적 원본을 식별하고 수집하는 마찰을 줄일 수 있습니다.

또한 Microsoft Graph API를 사용하면 eDiscovery 워크플로를 자동화하고 사용자 지정 솔루션에 대해 Advanced eDiscovery를 확장할 수 있습니다.

### <a name="cull-data-intelligently"></a>지능적으로 데이터 컬링

Advanced eDiscovery의 지능형 기계 학습 기능을 사용하면 검토할 데이터의 양을 줄일 수 있습니다. 이러한 지능형 기능을 사용하면 대량의 데이터를 줄이고 관련 집합으로 컬링할 수 있습니다. 예를 들어 기본 제공 검토 집합 쿼리를 사용하면 중복에 가까운 항목을 식별하여 고유한 콘텐츠만 필터링할 수 있습니다. 이 기능은 검토할 데이터 양을 크게 줄일 수 있습니다.

추가 기계 학습 기능은 관련성 모듈과 같은 스마트 태그 및 기술 지원 검토 도구를 사용하여 관련 데이터를 보다 구체화하고 식별할 수 있습니다.

## <a name="advanced-ediscovery-alignment-with-the-electronic-discovery-reference-model"></a>전자 검색 참조 모델을 사용하여 고급 eDiscovery 맞춤

Microsoft 365의 Advanced eDiscovery의 기본 제공 워크플로는 EDRM(전자 검색 참조 모델)에 설명된 eDiscovery 프로세스와 일치합니다.

![EDRM(전자 검색 참조 모델)](../media/EDRMv1.png)

(이미지 원본에 대한 edrm.net. 원본 이미지는 Creative Commons Attribution 3.0 미지원 라이선스에서 사용할 수 있습니다.)

고급 eDiscovery에서 EDRM 워크플로를 지원하는 방식은 다음과 같습니다.

- **IDENTIFICATION.** 조사에 관심이 있는 잠재적인 사람을 식별한 후 고급 eDiscovery 사례에 보유자(데이터 보유자라고도 하는 데이터 보유자)로 추가할 수 있습니다. 사용자가 보호자로 추가된 후 쉽게 보존, 수집 및 검토할 수 있습니다.

- **보존.** 고급 eDiscovery를 사용하면 조사와 관련된 데이터를 보존하고 보호할 수 있습니다. 보유하지 않은 데이터를 보류할 수 있습니다. Advanced eDiscovery에는 보유자에 법적 보류 알림을 보내고 해당 확인을 추적할 수 있도록 기본 제공 통신 워크플로도 있습니다.

- **컬렉션입니다.** 조사와 관련된 데이터 원본을 식별하고 보존한 후 Advanced eDiscovery 검색의 기본 제공 검색 도구를 사용하여 해당 사례와 관련이 있을 수 있는 양도 데이터 원본(및 해당되는 경우 비구성 데이터 원본)에서 라이브 데이터를 검색하고 수집할 수 있습니다.

- **처리 중입니다.** 사례와 관련된 모든 데이터를 수집한 후 다음 단계에서는 추가 검토 및 분석을 위해 데이터를 처리합니다. Advanced eDiscovery에서 수집 단계에서 식별한 원본 위치 데이터가 Azure Storage 위치(검토 집합)에 복사되어 사례 데이터의 정적 보기를 제공합니다.  

- **검토.** 검토 집합에 데이터가 추가된 후 특정 문서를 보고 추가 쿼리를 실행하여 사례와 가장 관련성이 높은 데이터로 데이터를 줄일 수 있습니다. 또한 특정 문서에 주석을 추가하고 태그를 지정합니다.

- **분석.** Advanced eDiscovery는 조사와 관련이 없다고 판단되는 검토 집합에서 데이터를 추가로 선회하는 데 도움이 되는 통합 분석 도구를 제공합니다. Advance eDiscovery는 관련 데이터의 양을 줄이는 것 외에도 검토 프로세스를 더 쉽고 효율적으로 만들기 위해 콘텐츠를 구성할 수 있도록 하여 법적 검토 비용을 절약하는 데 도움이 됩니다.

- **프로덕션** 및 **프레젠테이션.** 준비가 되면 법적 검토를 위해 검토 집합에서 문서를 내보낼 수 있습니다. 문서를 타사 검토 응용 프로그램으로 가져올 수 있도록 문서를 기본 형식 또는 EDRM 지정 형식으로 내보낼 수 있습니다.

## <a name="subscriptions-and-licensing"></a>구독 및 라이선스

Advanced eDiscovery 라이선스를 사용하려면 적절한 조직 구독 및 사용자당 라이선스가 필요합니다.

- **조직 구독:** Microsoft 365 규정 준수 센터에서 Advanced eDiscovery에 액세스하려면 조직에 다음 중 한 가지가 있어야 합니다.

  - Microsoft 365 E5 또는 Office 365 E5 구독
  
  - E5 Compliance 추가 기능이 포함된 Microsoft 365 E3 구독

  - E5 eDiscovery 및 감사 추가 기능을 통해 Microsoft 365 E3 구독

  기존 Microsoft 365 E5 요금제가 없는 경우 Advanced eDiscovery를 사용하려는 경우 기존 구독에 Microsoft [](https://www.microsoft.com/microsoft-365/enterprise) [365를](https://docs.microsoft.com/office365/admin/try-or-buy-microsoft-365) 추가하거나 Microsoft 365 E5 평가판을 등록할 수 있습니다.

- **사용자당 라이선스:** Advance eDiscovery 사례에서 사용자를 관리인으로 추가하려면 조직 구독에 따라 사용자에게 다음 라이선스 중 하나를 할당해야 합니다.

  - Microsoft 365: 사용자에게 Microsoft 365 E5 라이선스, E5 준수 추가 기능 라이선스 또는 E5 eDiscovery 및 감사 추가 기능 라이선스가 할당되어야 합니다.

  - Office 365: 사용자에게 Office 365 E5 라이선스가 할당되어야 합니다.

   라이선스를 할당하는 방법에 대한 자세한 내용은 사용자에게 라이선스 할당을 [참조하세요.](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users)

> [!NOTE]
> 고급 eDiscovery 사례에 E5 라이선스(또는 적절한 추가 기능 라이선스)만 추가하면 됩니다. Advanced eDiscovery를 사용하여 사례를 관리하고 사례 데이터를 검토하는 IT 관리자, eDiscovery 관리자, 변호사, paralegals 또는 조사자는 E5 또는 추가 기능 라이선스가 필요하지 않습니다.

## <a name="get-started-with-advanced-ediscovery"></a>Advanced eDiscovery 시작

Advanced eDiscovery를 시작하는 두 가지 빠르고 쉬운 단계가 있습니다.

![Advanced eDiscovery 시작 워크플로](../media/get-started-AeD.png)

|단계  |설명  |
|:---------|:---------|
|[Advanced eDiscovery 설정](get-started-with-advanced-ediscovery.md)| 구독 및 라이선스 요구 사항을 확인한 후 사용 권한을 할당하고 Advanced eDiscovery를 사용하도록 조직 전체 설정을 구성할 수 있습니다.|
|[사례 만들기 및 관리](create-and-manage-advanced-ediscoveryv2-case.md) | 조직의 모든 법적 및 기타 유형의 조사에 대한 Advanced eDiscovery 워크플로를 관리하는 사례를 만들 수 있습니다.|
|||

## <a name="advanced-ediscovery-architecture"></a>고급 eDiscovery 아키텍처

다음은 단일 위치 환경 및 다중 위치 환경의 종단-종단식 워크플로와 [EDRM에](#advanced-ediscovery-alignment-with-the-electronic-discovery-reference-model)맞게 조정된 종단-종단 데이터 흐름을 보여 줍니다.

[![모델 포스터: Microsoft 365의 Advanced eDiscovery 아키텍처](../media/solutions-architecture-center/ediscovery-poster-thumb.png)](../media/solutions-architecture-center/m365-advanced-ediscovery-architecture.png)

[이미지로 보기](../media/solutions-architecture-center/m365-advanced-ediscovery-architecture.png)

[PDF 파일로 다운로드](https://download.microsoft.com/download/d/1/c/d1ce536d-9bcf-4d31-b75b-fcf0dc560665/m365-advanced-ediscovery-architecture.pdf)

[Visio 파일로 다운로드](https://download.microsoft.com/download/d/1/c/d1ce536d-9bcf-4d31-b75b-fcf0dc560665/m365-advanced-ediscovery-architecture.vsdx)
