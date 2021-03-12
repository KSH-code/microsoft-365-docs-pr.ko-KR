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
- m365solution-ediscovery
- m365initiative-compliance
- m365solution-overview
search.appverid:
- MOE150
- MET150
description: Microsoft 365의 Advanced eDiscovery 솔루션에 대해 자세히 알아보십시오. 이 문서에서는 내부 및 외부 조사를 관리하는 데 도움이 되는 도구인 Microsoft 365의 Advanced eDiscovery에 대한 개요를 제공합니다. 또한 Advanced eDiscovery를 사용하여 법적 조사를 관리하는 비즈니스 이유에 대한 프레임을 제공합니다.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 6623682dedd0342f1e88478127d23bbbd4ab9dbb
ms.sourcegitcommit: 3d48e198e706f22ac903b346cadda06b2368dd1e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/11/2021
ms.locfileid: "50727589"
---
# <a name="overview-of-microsoft-365-advanced-ediscovery"></a>Microsoft 365 Advanced eDiscovery 개요

Microsoft 365의 Advanced eDiscovery 솔루션은 기존 Microsoft eDiscovery 및 분석 기능을 빌드합니다. Advanced eDiscovery는 조직의 내부 및 외부 조사에 응답하는 콘텐츠를 보존, 수집, 분석, 검토, 분석 및 내보내기 위한 종단 간 워크플로를 제공합니다. 또한 법률 팀에서 전체 법적 보유 알림 워크플로를 관리하여 사례에 관련된 보유자와 통신할 수 있습니다.

Advanced eDiscovery는 조직이 거주하는 데이터를 검색하여 법적 문제 또는 내부 조사에 대응하는 데 도움을 줄 수 있습니다. 관심 있는 사용자와 해당 데이터 원본을 식별하여 eDiscovery 워크플로를 원활하게 관리하고, 보류를 원활하게 적용하여 데이터를 보존한 다음 법적 보존 통신 프로세스를 관리할 수 있습니다. 원본에서 데이터를 수집하면 라이브 Microsoft 365 플랫폼을 검색하여 필요한 것을 빠르게 찾을 수 있습니다. 심층 인덱싱, 전자 메일 스레딩 및 중복에 가까운 검색과 같은 지능적인 기계 학습 기능도 관련 데이터 집합으로 대량의 데이터를 줄이는 데 도움이 됩니다.

다음 섹션에서는 이러한 Advanced eDiscovery 기능이 조직에 어떻게 도움이 되는지 설명합니다.

## <a name="discover-and-collect-data-in-place"></a>데이터 검색 및 원본치 수집

일반적으로 여러 타사 eDiscovery 솔루션을 사용하는 조직에서는 처리를 위해 대량의 데이터를 Microsoft 365에서 복사하고 중복 데이터를 호스트해야 합니다. 이러한 요구는 관련 데이터를 찾는 데 필요한 시간 및 여러 솔루션 관리의 위험, 비용 및 복잡성을 증가합니다.

Microsoft 365의 Advanced eDiscovery를 사용하면 원본에서 데이터를 검색하고 Microsoft 365 보안 및 규정 준수 경계 내에서 데이터를 검색할 수 있습니다.  Advanced eDiscovery는 라이브 시스템에서 데이터를 원본으로 수집하여 원본으로 돌아가는 마찰을 줄이고 누락된 콘텐츠를 찾을 필요가 없는 불필요한 작업을 줄여주며, 기존 eDiscovery 솔루션에서 저널링이 진행될 때 자주 발생합니다.

Teams, Yammer, SharePoint Online, 비즈니스용 OneDrive 및 Exchange Online의 데이터에 대한 기본 검색 및 수집 기능은 데이터 검색을 더욱 향상합니다. 예를 들어 Advanced eDiscovery:

- Teams 대화를 재구성합니다(대화에서 개별 메시지를 반환하는 대신).

- 전자 메일 메시지 및 Teams 채팅에서 링크 또는 최신 첨부 파일을 사용하여 사용자와 공유되는 클라우드 기반 콘텐츠를 수집합니다.

- 수백 개의 비 Microsoft 365 파일 형식에 대한 기본 제공 지원이 있습니다.

- 데이터 커넥터에 의해 Microsoft 365에서 가져오고 보관하는 타사 원본(예: Bloomberg, Facebook, Slack 및 Zoom Meetings)에서 데이터를 [수집합니다.](archiving-third-party-data.md)

## <a name="manage-ediscovery-workflow-in-one-platform"></a>하나의 플랫폼에서 eDiscovery 워크플로 관리

Advanced eDiscovery를 사용하면 필요한 eDiscovery 솔루션의 수를 줄일 수 있습니다. Microsoft 365 내에서 발생하는 간소화된 종단-종단 워크플로를 제공합니다. Advanced eDiscovery를 사용하면 고유 및 공유 데이터 원본을 관심 있는 사용자(보좌관)에게 자동으로 매핑하고 분석 및 검토를 위해 수집하기 전에 잠재적으로 관련성 있는 데이터에 대한 보고 및 분석을 제공하여 관련 정보의 잠재적 원본을 식별하고 수집하는 마찰을 줄일 수 있습니다.

또한 Microsoft Graph API를 사용하면 eDiscovery 워크플로를 자동화하고 사용자 지정 솔루션에 대해 Advanced eDiscovery를 확장할 수 있습니다.

## <a name="cull-data-intelligently"></a>지능적으로 데이터 컬링

Advanced eDiscovery의 지능형 기계 학습 기능을 사용하면 검토할 데이터의 양을 줄일 수 있습니다. 이러한 지능형 기능을 사용하면 대량의 데이터를 줄이고 관련 집합으로 컬링할 수 있습니다. 예를 들어 기본 제공 검토 집합 쿼리를 사용하면 중복에 가까운 항목을 식별하여 고유한 콘텐츠만 필터링할 수 있습니다. 이 기능은 검토할 데이터 양을 크게 줄일 수 있습니다.

추가 기계 학습 기능은 관련성 모듈과 같은 스마트 태그 및 기술 지원 검토 도구를 사용하여 관련 데이터를 보다 구체화하고 식별할 수 있습니다.

## <a name="advanced-ediscovery-architecture"></a>고급 eDiscovery 아키텍처

다음은 단일 위치 환경 및 다중 위치 환경의 종단-종단식 워크플로와 EDRM(전자 검색 참조 모델)에 맞춰진 종단-종단 [](advanced-ediscovery-edrm.md) 데이터 흐름을 보여 줍니다.

[![모델 포스터: Microsoft 365의 Advanced eDiscovery 아키텍처](../media/solutions-architecture-center/ediscovery-poster-thumb.png)](../media/solutions-architecture-center/m365-advanced-ediscovery-architecture.png)

[이미지로 보기](../media/solutions-architecture-center/m365-advanced-ediscovery-architecture.png)

[PDF 파일로 다운로드](https://download.microsoft.com/download/d/1/c/d1ce536d-9bcf-4d31-b75b-fcf0dc560665/m365-advanced-ediscovery-architecture.pdf)

[Visio 파일로 다운로드](https://download.microsoft.com/download/d/1/c/d1ce536d-9bcf-4d31-b75b-fcf0dc560665/m365-advanced-ediscovery-architecture.vsdx)

Advanced eDiscovery의 종단-종단 워크플로에 대한 자세한 내용은 [이 Microsoft Mechanics 비디오를 참조하세요.](https://go.microsoft.com/fwlink/?linkid=2066133)

## <a name="advanced-ediscovery-workflow"></a>고급 eDiscovery 워크플로

다음 섹션에서는 Microsoft 365 규정 준수 센터의 Advanced eDiscovery 도구에서 기본 제공 워크플로의 각 단계에 대해 설명합니다. 다음 스크린샷은  *2020.11.03 - Contoso v. Fabrikam* 이라는 사례의 개요 탭을 보여줍니다.

![기본 제공 Advanced eDiscovery 워크플로의 탭](../media/AeD-Case-Screenshot1.png)

자세한 내용은 [Manage the Advanced eDiscovery workflow를 참조하십시오.](create-and-manage-advanced-ediscoveryv2-case.md#manage-the-workflow)

### <a name="managing-custodians-and-non-custodial-data-sources"></a>보호자 및 비관리 데이터 원본 관리

데이터 **원본** 탭을 사용하여 사례에 관심 있는 사람으로 식별한 사용자 및 관리인과 연결되지 않을 수 있는 기타 데이터 원본을 추가하고 관리합니다. 보유자 또는 비관리 데이터 원본을 추가할 때 보유자 및 비관리 데이터 원본에 법적 보유를 두거나, 보유자와 통신하고, 보유자 및 비관리 데이터 원본을 검색하여 사례와 관련된 콘텐츠를 수집하는 작업을 신속하게 수행할 수 있습니다. 사례가 진행될 때 새 정보 근로자 또는 비구매인 날짜 원본을 추가하거나 사례에서 해제하기가 쉽습니다. 자세한 내용은 보호자 작업을 [참조하세요.](managing-custodians.md)

### <a name="managing-legal-hold-notifications"></a>법적 보유 알림 관리

통신 **탭을** 사용하여 이 경우 관리인과 통신하는 프로세스를 관리합니다. 법적 보존 고지는 보유자에게 사례와 관련된 모든 콘텐츠를 보존하도록 지시합니다. 법률 팀은 보호자에 의해 수신, 읽히고, 인정된 통지를 추적할 수 있어야 합니다. Advanced eDiscovery의 통신 워크플로를 사용하면 보유자에 대해 보류 알림을 확인하지 못할 경우 초기 알림, 미리 알림, 릴리스 알림 및 에스컬레이터를 만들고 보낼 수 있습니다. 자세한 내용은 [Work with communications을 참조하십시오.](managing-custodian-communications.md)

### <a name="managing-content-preservation"></a>콘텐츠 보존 관리

사례에 보유자 추가 시 보유 데이터를 보유할 수 있습니다. 보유 **탭을** 사용하여 보유자 추가 시 만들어진 보류를 관리하고 사례와 관련된 다른 법적 보유를 관리합니다. 예를 들어 보유하지 않은 데이터 원본을 식별하고 보류할 수 있습니다. 또한 이 경우 보류를 편집하고 쿼리 기반 보류로 만들어 쿼리와 일치하는 콘텐츠만 보존할 수 있습니다. 예를 들어 보류에 날짜 범위를 추가하여 특정 날짜 내에 만들어진 콘텐츠만 보존하도록 할 수 있습니다. 보류 상태인 콘텐츠에 대한 통계를 얻거나, 더 이상 사례와 관련이 없는 보류를 제거하거나, 삭제할 수도 있습니다. 자세한 내용은 [보류 관리를 참조하세요.](managing-holds.md)

### <a name="indexing-custodian-data"></a>보호자 데이터 인덱싱

사례에 보호자 및 해당 상주 데이터 원본을 추가하면 고급 인덱싱이라는 프로세스에 의해 보호자 데이터 원본의 부분적으로 인덱싱된 항목이 다시 *인덱싱됩니다.* 이를 통해 검색을 실행하여 사례에 대한 데이터를 수집할 때 이미지, 지원되지 않는 파일 형식 및 기타 잠재적으로 인덱서되지 않은 콘텐츠와 같은 콘텐츠를 완전히 검색할 수 있습니다. 처리 **탭을** 사용하여 고급 인덱싱 상태를 모니터링하고 오류 수정 이라는 프로세스를 사용하여 처리 오류를 *수정합니다.* 자세한 내용은 처리 오류 [수정을 참조하세요.](processing-data-for-case.md)

### <a name="collecting-case-data"></a>사례 데이터 수집하기

검색 **탭을 사용하여** 검색을 만들어 해당 사례와 관련된 콘텐츠에 대한 원본 및 비관용 데이터 원본을 검색합니다. 키워드 및 조건을 사용하여 쿼리 기반 검색을 만들고 실행하여 사례와 관련된 전자 메일 메시지 및 문서 집합을 식별하고 eDiscovery 워크플로의 후속 단계에서 추가로 검토하고 분석할 수 있습니다. 사례와 연결된 검색을 하나 이상 만들 수 있습니다. 검색 도구를 사용하여 예제 문서를 미리 보고 검색 통계를 확인하여 검색 결과를 구체화하고 개선할 수도 있습니다. 검색 결과에 사례와 관련된 모든 데이터가 포함된 경우 추가 검토, 분석 및 컬링을 위해 검색 결과를 검토 집합에 추가합니다. 자세한 내용은 [사례에 대한 데이터 수집을 참조하세요.](collecting-data-for-ediscovery.md)

### <a name="reviewing-and-analyzing-case-data"></a>사례 데이터 검토 및 분석

검토 집합 **탭을 사용하여** 라이브 시스템에서 수집하고 검토 집합에 추가한 콘텐츠를 검토하고 분석할 수 있습니다. 검토  집합은 eDiscovery 워크플로의 이전 단계에서 수집한 양도 데이터(해당하는 경우 비보조 데이터)의 해당 데이터의 정적 컬렉션입니다(즉, 데이터의 오프라인 복사본). 검색 결과를 검토 집합에 추가하면 컨테이너에서 파일을 추출하고 메타데이터를 추출하고 텍스트를 추출하는 프로세스가 트리거됩니다. 이 프로세스가 완료되면 시스템은 보호자로부터 수집된 모든 데이터의 새 인덱스를 작성하여 검토 집합에 추가합니다. 검토 집합에 데이터가 추가된 후 더 많은 쿼리를 실행하여 사례 데이터 범위를 좁히고, 데이터를 텍스트 또는 기본 파일 형식으로 보며, 검토 집합에서 문서에 주석을 추가하고, 편집하고, 태그를 지정할 수 있습니다. 문서 복제, 전자 메일 스레딩 및 테마 식별과 같은 고급 분석을 수행할 수도 있습니다. 데이터를 사례와 관련된 항목으로만 선회한 후 문서를 직접 다운로드하거나 파일 메타데이터, 주석 및 태그와 함께 내보낼 수 있습니다. 자세한 내용은 다음을 참조하세요.

- [검토 집합에서 문서 보기](view-documents-in-review-set.md)

- [검토 집합에서 데이터 쿼리](review-set-search.md)

- [검토 집합에서 문서 태그 지정](tagging-documents.md)

- [검토 집합의 데이터 분석](analyzing-data-in-review-set.md)

### <a name="exporting-data-for-review-and-presentation"></a>검토 및 프레젠테이션을 위해 데이터 내보내기

검토 집합에서 데이터를 내보내고 나면  내보내기 탭을 사용하여 내보내기 작업을 관리하고 검토 집합에서 데이터를 다운로드합니다. 검토 집합을 내보낼 때 데이터는 Microsoft에서 제공하는 Azure Storage 위치(또는 조직에서 관리하는 Azure Storage 위치)에 업로드됩니다. Azure에 업로드한 후 로컬 컴퓨터에 다운로드할 수 있습니다. 내보내기 탭에서 내보낼 데이터를 다운로드하는 데 필요한 저장소 평가 키를 얻을 **수** 있습니다. 자세한 내용은 사례 데이터 [내보내기 를 참조하세요.](exporting-data-ediscover20.md)

### <a name="managing-jobs"></a>작업 관리

작업 **탭을** 사용하여 시작한 사례 관련 작업에 대해 장기 실행 프로세스를 모니터링합니다. 작업의 예로는 사례 데이터 다시 인덱스, 검색 및 내보내기와 관련된 작업이 있습니다. 예를 들어 여러 데이터 원본이  포함된 검색 탭에서 검색을 만드는 경우 이 검색 프로세스의 상태가 작업 탭에 **표시됩니다.** 자세한 내용은 작업 [관리를 참조하세요.](managing-jobs-ediscovery20.md)

### <a name="configuring-case-settings"></a>사례 설정 구성

설정 **탭을** 사용하여 대소문자 전체 설정을 구성합니다. 여기에는 사례에 구성원 추가, 사례 닫기 또는 삭제, 검색 및 분석 설정 구성이 포함됩니다. 자세한 내용은 다음을 참조하세요.

- [사례에 구성원 추가](add-or-remove-members-from-a-case-in-advanced-ediscovery.md)

- [사례 닫기 또는 삭제](close-or-delete-case.md)

- [검색 및 분석 설정 구성](configure-search-and-analytics-settings-in-advanced-ediscovery.md)
