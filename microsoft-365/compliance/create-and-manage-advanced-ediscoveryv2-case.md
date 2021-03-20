---
title: Microsoft 365에서 Advanced eDiscovery 사례 만들기 및 관리
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
- m365solution-aed
- m365initiative-compliance
- m365solution-scenario
search.appverid:
- MOE150
- MET150
description: 이 문서에서는 Advanced eDiscovery 사례를 만들고 관리하는 방법을 설명합니다. 첫 번째 단계는 사례를 만들고 Advanced eDiscovery 기능 사용을 시작하는입니다.
ms.openlocfilehash: d0f63bca90945c3dfe13b08fa0f1d139da8a9189
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50908368"
---
# <a name="create-and-manage-an-advanced-ediscovery-case"></a>Advanced eDiscovery 사례 만들기 및 관리

Advanced eDiscovery를 설정하고 사례를 관리할 조직의 [eDiscovery](get-started-with-advanced-ediscovery.md#step-2-assign-ediscovery-permissions) 관리자에게 사용 권한을 할당한 후 다음 단계는 사례를 만들고 관리하는 것입니다.

또한 이 문서에서는 사례를 사용하여 법률 사례 또는 기타 유형의 조사를 위한 Advanced eDiscovery 워크플로를 관리하는 방법을 간략하게 소개합니다.

## <a name="create-a-case"></a>사례 만들기

다음 단계를 완료하여 사례를 만들고 구성원을 추가합니다. 사례를 만드는 사용자는 자동으로 구성원으로 추가됩니다. 사례의 구성원은 Microsoft 365 규정 준수 센터에서 사례에 액세스하고 고급 eDiscovery 작업을 수행할 수 있습니다.

1. 으로 이동한 후 eDiscovery 권한이 할당된 사용자 계정의 자격 증명을 <https://compliance.microsoft.com> 사용하여 로그인합니다. 조직 관리 역할 그룹의 구성원은 Advanced eDiscovery 사례를 만들 수 있습니다.

2. Microsoft 365 규정 준수 센터의 왼쪽 탐색 창에서 모두 표시를 클릭한 다음 **고급 에서 eDiscovery > 클릭합니다.**

3. Advanced **eDiscovery** 페이지에서 사례  탭을 클릭한 다음 사례 만들기 **를 클릭합니다.**

4. 새 **eDiscovery** 사례 플라이아웃 페이지에서 사례에 이름(필수)을 지정한 다음 선택적 사례 번호와 설명을 입력합니다. 사례 이름은 조직에서 고유해야 합니다.

5. **저장을** 클릭하여 사례를 만들 수 있습니다.

   새 사례가 만들어지며 새 사례의 **설정** 탭이 표시됩니다.

6. 설정 **탭의 Access &** 권한 **타일에서** 선택을 **클릭한** 다음 업데이트를 **클릭합니다.**

7. **업데이트** 를 클릭합니다.

8. 이 **사례 관리 플라이아웃** 페이지의 구성원  관리에서 **추가를** 클릭하여 사례에 구성원을 추가합니다.

9. 사용자 목록에서 사례에 추가할 사용자 이름 옆의 확인란을 선택합니다. 앞서 설명한 것 처럼 사례에 추가 하는 사용자에게 적절한 eDiscovery 권한이 할당되어 있는지 확인 합니다.

10. 사례의 구성원으로 추가할 구성원을 선택한 후 추가 를 **클릭합니다.**

11. 이 **사례 관리 플라이아웃**  페이지에서 저장을 클릭하여 새 사례 구성원 목록을 저장합니다.

12. 홈 **탭을** 클릭하여 사례 홈 페이지로 이동합니다.

## <a name="manage-the-workflow"></a>워크플로 관리

Advanced eDiscovery 사용을 시작하기 위해 일반적인 [eDiscovery](advanced-ediscovery-edrm.md)사례에 부합하는 기본 워크플로는 다음과 있습니다. 이러한 각 단계에서는 탐색할 수 있는 몇 가지 확장된 Advanced eDiscovery 기능도 강조합니다.

![고급 eDiscovery 워크플로](../media/AeDWorkflow.png)

1. **[사례에](add-custodians-to-case.md) [](non-custodial-data-sources.md)** 보호자 및 비보조 데이터 원본을 추가합니다. 사례를 작성한 후 첫 번째 단계는 보금자리를 추가하는 것입니다. *관리자는* 사례와 관련이 있을 수 있는 문서 또는 전자 파일의 관리 제어권이 있는 사람입니다. 또한 특정 사용자와 연결되지는 않지만 사례와 관련이 있을 수 있는 데이터 원본을 추가할 수 있습니다.

   다음은 사례에 보금을 추가할 때(또는 할 수 있는) 몇 가지 사항입니다.

   - 거래소의 Exchange 사서함, OneDrive 계정 및 Yammer 구성원인 Microsoft Teams 또는 Yammer 그룹의 데이터는 이 경우 양도 데이터로 "표시"될 수 있습니다.
  
   - 보호자 데이터는 고급 인덱싱이라는 프로세스에 의해 다시 *인덱싱됩니다.* 이렇게 하면 다음 단계에서 검색을 최적화하는 데 도움이 됩니다.
  
   - 보유자 데이터를 보류할 수 있습니다. 이렇게 하면 조사 중에 사례와 관련이 있을 수 있는 데이터가 보존됩니다.
  
   - 다른 데이터 원본을 보유자(예: SharePoint 사이트 또는 Microsoft 365 그룹을 보유자에 연결하여 보유자)와 연결하여 보유자 사서함 또는 OneDrive 계정의 데이터와 마찬가지로 이 데이터를 다시 인덱서하고 보류하고 검색할 수 있습니다.

   - Advanced eDiscovery의 통신 워크플로를 사용하여 보유자에 법적 보류 알림을 보낼 수 있습니다. [](managing-custodian-communications.md)

2. **[데이터 원본에서 관련 콘텐츠를 수집합니다.](create-draft-collection.md)** 사례에 보호자 및 비보조 데이터 원본을 추가한 후 기본 제공 컬렉션 도구를 사용하여 이러한 데이터 원본에서 사례와 관련이 있을 수 있는 콘텐츠를 검색합니다. 키워드, 속성 및 조건을 사용하여 [](building-search-queries.md) 사례와 관련성이 가장 높은 데이터로 검색 결과를 반환하는 검색 쿼리를 작성합니다. 또한 다음을 수행할 수 있습니다.

   - 결과 [범위를 좁히기](collection-statistics-reports.md) 위해 컬렉션을 구체화하는 데 도움이 될 수 있는 컬렉션 통계를 볼 수 있습니다.

   - 컬렉션 샘플을 미리 보고 관련 데이터가 있는지 빠르게 확인할 수 있습니다.

   - 쿼리를 변경하고 컬렉션을 다시 실행합니다.

3. **[컬렉션을 검토 집합에 커밋합니다.](commit-draft-collection.md)** 검색에서 원하는 데이터를 반환하는지 구성하고 확인한 다음에는 검색 결과를 검토 집합에 추가합니다. 검토 집합에 데이터를 추가하면 항목이 원래 위치에서 안전한 Azure Storage 위치로 복사됩니다. 검토 집합의 항목을 검토하고 분석할 때 철저하고 빠른 검색을 위해 데이터를 다시 인덱서합니다. 또한 검토 집합 [에 비 Office 365 데이터를 추가할 수도 있습니다.](load-non-office-365-data-into-a-review-set.md)

   대화 검토 집합이라고 하는 데이터를 추가할 수 있는 특별한 종류의 검토 *집합도 있습니다.* 이러한 유형의 리뷰 집합은 Microsoft Teams에서와 같이 스레드된 대화를 재구성, 검토 및 내보내기 위한 대화 재구성 기능을 제공합니다. 자세한 내용은 [고급 eDiscovery에서 대화 검토를 참조하세요.](conversation-review-sets.md)

4. **검토 집합의 데이터를 검토하고 분석합니다.** 이제 데이터가 검토 집합에 추가된 후 다양한 도구 및 기능을 사용하여 조사하는 사례와 가장 관련성이 높은 데이터 집합을 줄이는 것을 목표와 함께 사례 데이터를 보고 분석할 수 있습니다. 다음은 이 프로세스 중에 사용할 수 있는 몇 가지 도구 및 기능 목록입니다.

   - [문서 보기.](view-documents-in-review-set.md) 여기에는 검토 집합의 각 문서에 대한 메타데이터 보기, 문서의 기본 버전 또는 텍스트 버전 보기가 포함됩니다.

   - [쿼리 및 필터를 만듭니다.](review-set-search.md) 다양한 검색 조건(모든 파일 메타데이터 속성 검색 포함)을 사용하여 검색 쿼리를 만들어 사례 데이터를 사례와 가장 관련성이 높은 항목으로 보다 구체화하고 선형화할 수 있습니다. [](document-metadata-fields-in-advanced-ediscovery.md) 또한 검토 집합 필터를 사용하여 검색 쿼리 결과에 다른 조건을 신속하게 적용하여 이러한 결과를 보다 구체화할 수도 있습니다. 

   - [태그를 만들고 사용 합니다.](tagging-documents.md) 검토 집합의 문서에 태그를 적용하여 응답하는(또는 사례에 응답하지 않는) 태그를 식별한 다음 검색 쿼리를 만들 때 해당 태그를 사용하여 태그가 지정된 문서를 포함하거나 제외할 수 있습니다. 또한 태그를 지정하여 내보낼 문서를 결정할 수 있습니다.

   - [문서에 주석을 추가하고 문서를 다시 고치면 됩니다.](view-documents-in-review-set.md#annotate-view) 검토에서 주석 도구를 사용하여 문서에 주석을 추가하고 문서의 콘텐츠를 작업 제품으로 재배치할 수 있습니다. 검토하는 동안 주석으로 작성되거나 편집된 문서의 PDF 버전을 생성하여 문서의 원시 버전을 내보낼 위험을 줄입니다.

   - [사례 데이터를 분석합니다.](analyzing-data-in-review-set.md) Advanced eDiscovery의 분석 기능은 강력합니다. 검토 집합의 데이터에 대한 분석을 실행한 후 중복에 가까운 검색, 전자 메일 스레딩 및 검토해야 하는 문서의 양을 줄이는 데 도움이 되는 테마 등의 분석을 수행 합니다. 또한 분석 실행 결과를 요약하는 분석 보고서를 생성합니다. 앞서 설명한 것 처럼 분석을 실행하면 변호사-클라이언트 권한 검색 [모델도 실행됩니다.](attorney-privilege-detection.md#use-the-attorney-client-privilege-detection-model)

5. **사례 데이터를 내보내고 다운로드합니다.** 사례 데이터를 수집, 검토 및 분석한 후의 마지막 단계는 외부 검토를 위해 고급 eDiscovery에서 내보내거나 조사 팀 외부의 사람이 검토하는 것입니다. 데이터를 내보내는 과정은 2단계 프로세스입니다. 첫 번째 단계는 [](export-documents-from-review-set.md) 검토 집합에서 데이터를 내보내고 다른 Azure Storage 위치(Microsoft에서 제공하거나 조직에서 관리하는 Azure Storage 위치)에 복사하는 것입니다. 그런 다음 Azure Storage Explorer를 사용하여 [로컬](download-export-jobs.md) 컴퓨터에 데이터를 다운로드합니다. 내보내는 데이터 파일 외에 내보내기 패키지의 포함에는 내보내기 보고서, 요약 보고서 및 오류 보고서도 포함되어 있습니다.

## <a name="advanced-ediscovery-architecture"></a>고급 eDiscovery 아키텍처

다음은 단일 위치 환경 및 다중 위치 환경의 Advanced eDiscovery 종단식 워크플로와 전자 검색 참조 모델과 정렬된 종단-종단 데이터 흐름을 보여 [줍니다.](overview-ediscovery-20.md#advanced-ediscovery-alignment-with-the-electronic-discovery-reference-model)

[![모델 포스터: Microsoft 365의 Advanced eDiscovery 아키텍처](../media/solutions-architecture-center/ediscovery-poster-thumb.png)](../media/solutions-architecture-center/m365-advanced-ediscovery-architecture.png)

[이미지로 보기](../media/solutions-architecture-center/m365-advanced-ediscovery-architecture.png)

[PDF 파일로 다운로드](https://download.microsoft.com/download/d/1/c/d1ce536d-9bcf-4d31-b75b-fcf0dc560665/m365-advanced-ediscovery-architecture.pdf)

[Visio 파일로 다운로드](https://download.microsoft.com/download/d/1/c/d1ce536d-9bcf-4d31-b75b-fcf0dc560665/m365-advanced-ediscovery-architecture.vsdx)
