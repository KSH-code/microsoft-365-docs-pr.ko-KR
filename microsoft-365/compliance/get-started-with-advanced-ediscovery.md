---
title: Microsoft 365에서 Advanced eDiscovery 시작
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
- m365solution-aed
- m365initiative-compliance
search.appverid:
- MOE150
- MET150
description: 이 문서에서는 Microsoft 365에서 Advanced eDiscovery를 사용하는 방법을 설명합니다. 몇 가지 빠른 단계를 완료하면 Advanced eDiscovery 도구를 사용할 수 있습니다. 첫 번째 단계는 사례를 만든 다음 Advanced eDiscovery 기능 사용을 시작하는 단계입니다.
ms.openlocfilehash: 45443620f294489c3afb4392376c9fe999fa098b
ms.sourcegitcommit: 98b889e674ad1d5fa37d4b6c5fc3eda60a1d67f3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/05/2021
ms.locfileid: "49751095"
---
# <a name="get-started-with-advanced-ediscovery"></a>Advanced eDiscovery 시작

Microsoft 365의 Advanced eDiscovery는 조직의 내부 및 외부 조사에 응답하는 데이터를 보존, 수집, 검토, 분석 및 내보내기 위한 종단 간 워크플로를 제공합니다. [](overview-ediscovery-20.md#advanced-ediscovery-architecture) Advanced eDiscovery를 배포할 필요는 없지만 조직에서 Advanced eDiscovery 사례를 만들고 사용하여 조사를 관리하기 전에 IT 관리자 및 eDiscovery 관리자가 완료해야 하는 몇 가지 선행 작업이 있습니다.

이 문서에서는 Advanced eDiscovery를 설정하는 데 필요한 단계에 대해 논의합니다. 여기에는 Advanced eDiscovery에 액세스하고 사례에 보호자를 추가하는 데 필요한 적절한 라이선스를 보장하는 것뿐만 아니라 사례에 액세스하고 관리할 수 있도록 법적 및 조사 팀에 권한을 할당하는 작업도 포함됩니다. 또한 이 문서에서는 사례를 사용하여 법적 조사를 위한 Advanced eDiscovery 워크플로를 관리하는 방법을 간략하게 소개합니다.

## <a name="step-1-verify-and-assign-appropriate-licenses"></a>1단계: 적절한 라이선스 확인 및 할당

Advanced eDiscovery 라이선스를 사용하려면 적절한 조직 구독 및 사용자당 라이선스가 필요합니다.

- **조직 구독:** Microsoft 365 규정 준수 센터 또는 보안 & 준수 센터에서 Advanced eDiscovery에 액세스하려면 조직에 다음 중 한 가지가 있어야 합니다.

  - Microsoft 365 E5 또는 Office 365 E5 구독
  
  - E5 Compliance 추가 기능이 포함된 Microsoft 365 E3 구독

  - E5 eDiscovery 및 감사 추가 기능을 통해 Microsoft 365 E3 구독

  기존 Microsoft 365 E5 요금제가 없는 경우 Advanced eDiscovery를 사용하려는 경우 기존 구독에 Microsoft [](https://www.microsoft.com/microsoft-365/enterprise) [365를](https://docs.microsoft.com/office365/admin/try-or-buy-microsoft-365) 추가하거나 Microsoft 365 E5 평가판을 등록할 수 있습니다.

- **사용자당 라이선스:** Advance eDiscovery 사례에서 사용자를 취득자로 추가하려면 조직 구독에 따라 사용자에게 다음 라이선스 중 하나를 할당해야 합니다.

  - Microsoft 365: 사용자에게 Microsoft 365 E5 라이선스, E5 준수 추가 기능 라이선스 또는 E5 eDiscovery 및 감사 추가 기능 라이선스가 할당되어야 합니다.

  - Office 365: 사용자에게 Office 365 E5 라이선스가 할당되어야 합니다.

   라이선스를 할당하는 방법에 대한 자세한 내용은 사용자에게 라이선스 할당을 [참조하세요.](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users)

> [!NOTE]
> 고급 eDiscovery 사례에 취득자로 추가하려면 E5 라이선스(또는 적절한 추가 기능 라이선스)만 필요합니다. Advanced eDiscovery를 사용하여 사례를 관리하고 사례 데이터를 검토하는 IT 관리자, eDiscovery 관리자, 변호사, paralegals 또는 조사자는 E5 또는 추가 기능 라이선스가 필요하지 않습니다.

## <a name="step-2-assign-ediscovery-permissions"></a>2단계: eDiscovery 사용 권한 할당

Advanced eDiscovery에 액세스하거나 Advanced eDiscovery 사례의 구성원으로 추가하려면 사용자에게 적절한 사용 권한이 할당되어야 합니다. 특히 사용자는 보안 및 준수 센터에서 eDiscovery 관리자 역할 그룹의 구성원으로 & 합니다. 이 역할 그룹의 구성원은 Advanced eDiscovery 사례를 만들고 관리할 수 있습니다. 또한 구성원을 추가 및 제거하고, 보유자 및 콘텐츠 위치를 보류하고, 법적 보유 알림을 관리하고, 사례에 연결된 검색을 만들고 편집하고, 검토 집합에 검색 결과를 추가하고, 검토 집합의 데이터를 분석하고, Advanced eDiscovery 사례에서 데이터를 내보내고 다운로드할 수 있습니다.

다음 단계를 완료하여 eDiscovery 관리자 역할 그룹에 사용자를 추가합니다.

1. Go to [https://protection.office.com/permissions](https://protection.office.com/permissions) and sign in using the credentials for an admin account in your Microsoft 365 organization.

2. 사용 권한 **페이지에서** **eDiscovery 관리자 역할 그룹을** 선택합니다.

3. eDiscovery 관리자 플라이아웃 페이지에서  **eDiscovery** 관리자 섹션 옆에 있는 편집을 클릭합니다.

4. 역할 그룹 편집 마법사의 **eDiscovery 관리자** 선택 페이지에서 **eDiscovery 관리자 선택을 클릭합니다.**

5. **추가를** 클릭한 다음 역할 그룹에 추가할 모든 사용자에 대한 확인란을 선택합니다.

6. **추가를** 클릭하여 선택한 사용자를 추가한 다음 완료를 **클릭합니다.**

7. **저장을** 클릭하여 역할 그룹에 사용자를 추가한 다음 **닫기를** 클릭하여 단계를 완료합니다.

### <a name="more-information-about-the-ediscovery-manager-role-group"></a>eDiscovery 관리자 역할 그룹에 대한 자세한 정보

eDiscovery 관리자 역할 그룹에는 두 개의 하위 그룹이 있습니다. 이러한 하위 그룹 간의 차이는 범위를 기준으로 합니다.

- **eDiscovery 관리자:** 만들거나 구성원으로 있는 Advanced eDiscovery 사례를 보고 관리할 수 있습니다. 다른 eDiscovery 관리자가 사례를 만들고 두 번째 eDiscovery 관리자를 해당 사례의 구성원으로 추가하지 않는 경우 두 번째 eDiscovery 관리자는 준수 센터의 Advanced eDiscovery 페이지에서 사례를 보거나 열 수 없습니다. 일반적으로 조직의 대부분의 사람은 eDiscovery 관리자 하위 조직에 추가할 수 있습니다.

- **eDiscovery 관리자:** eDiscovery 관리자가 수행할 수 있는 모든 사례 관리 작업을 수행할 수 있습니다. 또한 eDiscovery 관리자(Administrator)는 다음과 같은 작업을 수행할 수 있습니다.

  - Advanced eDiscovery 페이지에 나열된 모든 사례를 볼 수 있습니다.
  
  - 자신을 사례의 구성원으로 추가한 후 조직에서 모든 사례를 관리합니다.

  - 조직의 모든 사례에 대한 사례 데이터에 액세스하고 내보낼 수 있습니다.

  액세스 범위가 넓기 때문에 조직에는 eDiscovery Administrators 하위 그룹 구성원인 관리자만 포함해야 합니다.

eDiscovery 사용 권한 및 eDiscovery 관리자 역할 그룹에 할당된 각 역할에 대한 설명에 대한 자세한 내용은 [eDiscovery](assign-ediscovery-permissions.md)권한 할당을 참조하세요.

## <a name="step-3-configure-global-settings-for-advanced-ediscovery"></a>3단계: Advanced eDiscovery에 대한 전역 설정 구성

조직의 사용자가 사례를 만들고 사용하기 전에 완료하는 마지막 단계는 조직의 모든 사례에 적용되는 전역 설정을 구성하는 것입니다. 현재 전역 설정은 *변호사-클라이언트* 권한 검색뿐입니다(향후 더 많은 전역 설정을 사용할 수 있습니다). 이 설정을 사용하면 검토 집합의 데이터를 분석할 때 변호사-클라이언트 권한 모델을 실행할 수 있습니다. 이 모델에서는 기계 학습을 사용하여 문서에 본질적으로 합법적인 콘텐츠가 포함되어 있는지 여부를 확인할 수 있습니다. 또한 문서의 참가자를 변호인 목록(모델을 설정할 때 제출)과 비교하여 문서에 적어도 한 명 이상의 변호사 참가자가 있는지 여부를 확인할 수 있습니다.

변호인 권한 검색 모델을 설정하고 사용하는 데 대한 자세한 내용은 [Advanced eDiscovery에서 변호사-클라이언트](attorney-privilege-detection.md)권한 검색 설정을 참조하세요.

> [!NOTE]
> 이 단계는 언제든지 수행할 수 있는 선택적 단계입니다. 변호인 권한 검색 모델을 구현하지 않는 경우 Advanced eDiscovery 사례를 만들고 사용할 수 있습니다.

## <a name="step-4-create-an-advanced-ediscovery-case"></a>4단계: 고급 eDiscovery 사례 만들기

다음 단계에서는 사례를 만들고 Advanced eDiscovery 사용을 시작해야 합니다. 다음 단계를 완료하여 사례를 만들고 구성원을 추가합니다. 사례를 만드는 사용자는 자동으로 구성원으로 추가됩니다.

1. 적절한 eDiscovery 권한이 할당된 사용자 계정으로 이동하여 [https://compliance.microsoft.com](https://compliance.microsoft.com) 로그인합니다. 조직 관리 역할 그룹의 구성원은 Advanced eDiscovery 사례를 만들 수 있습니다.

2. Microsoft 365 규정 준수 센터의 왼쪽 탐색 창에서 모두 표시를 클릭한 다음 **eDiscovery**> 클릭합니다.

3. Advanced **eDiscovery** 페이지에서 사례  탭을 클릭한 다음 사례 **만들기를 클릭합니다.**

4. New **eDiscovery** 사례 플라이아웃 페이지에서 사례에 이름(필수)을 지정한 다음 선택적 사례 번호와 설명을 입력합니다. 사례 이름은 조직에서 고유해야 합니다.

5. 사례를 **만들려면** 저장을 클릭합니다.

   새 사례가 만들어지며 새 사례의 **설정** 탭이 표시됩니다.

6. 설정 **탭의 Access &** 권한 타일에서 선택을 클릭한 다음 업데이트를  **클릭합니다.**

7. **업데이트** 를 클릭합니다.

8. 이 사례 **관리 플라이아웃** 페이지의 구성원 관리 **아래에서** **추가를** 클릭하여 사례에 구성원을 추가합니다.

9. 사용자 목록에서 사례에 추가할 사용자 이름 옆에 있는 확인란을 선택합니다. 앞서 설명한 경우 사례에 추가하는 사용자에게 적절한 eDiscovery 권한이 할당되어 있는지 확인하십시오.

10. 사례의 구성원으로 추가할 구성원을 선택한 후 추가를 **클릭합니다.**

11. 이 사례 **관리 플라이아웃**  페이지에서 저장을 클릭하여 새 사례 구성원 목록을 저장합니다.

12. 홈 **탭을** 클릭하여 사례 홈 페이지로 이동합니다.

## <a name="explore-the-advanced-ediscovery-workflow"></a>Advanced eDiscovery 워크플로 살펴보기

Advanced eDiscovery 사용을 시작하기 위해 일반적인 [eDiscovery](overview-ediscovery-20.md#alignment-with-edrm)사례에 맞게 간단한 워크플로를 제공합니다. 이러한 각 단계에서는 탐색할 수 있는 몇 가지 확장된 Advanced eDiscovery 기능도 강조합니다.

![Advanced eDiscovery 워크플로](../media/AeDWorkflow.png)

1. **[사례에 보금주를 추가합니다.](add-custodians-to-case.md)** 사례를 만들고 나면 첫 번째 단계는 보금주를 추가하는 것입니다. *양도자는* 사례와 관련이 있을 수 있는 문서 또는 전자 파일의 관리 제어를 갖는 사람입니다. 다음은 사례에 보금주를 추가할 때 발생하거나 할 수 있는 일입니다.

   - 거래소의 Exchange 사서함, OneDrive 계정 및 Yammer가 구성원으로 있는 Microsoft Teams 또는 Yammer 그룹의 데이터는 이 경우 양도 데이터로 "표시"할 수 있습니다.
  
   - 보호자 데이터는 고급 인덱싱이라는 프로세스에 의해 다시 *인덱싱됩니다.* 이렇게 하면 다음 단계에서 검색을 최적화하는 데 도움이 됩니다.
  
   - 보유자 데이터를 보류할 수 있습니다. 이렇게 하면 조사 중에 사례와 관련이 있을 수 있는 데이터가 보존됩니다.
  
   - 다른 데이터 원본을 보유자(예: SharePoint 사이트 또는 Microsoft 365 그룹을 보유자와 연결)하여 보유자 사서함 또는 OneDrive 계정의 데이터와 마찬가지로 이 데이터를 다시 인덱서하고, 보류 중으로 설정하고, 검색할 수 있습니다.

   - Advanced eDiscovery의 통신 워크플로를 사용하여 보유자에 법적 보류 알림을 보낼 수 있습니다. [](managing-custodian-communications.md)

2. **[양도 데이터 원본에서](collecting-data-for-ediscovery.md)** 사례와 관련된 데이터를 검색합니다. 사례에 관리인을 추가한 후 기본 제공 검색 도구를 사용하여 보호자 데이터 위치에서 사례와 관련이 있을 수 있는 데이터를 검색합니다. 키워드, 속성 및 조건을 사용하여 [](building-search-queries.md) 사례와 관련성이 가장 높은 데이터로 검색 결과를 반환하는 검색 쿼리를 작성합니다. 또한 다음을 수행할 수 있습니다.

   - 검색 [쿼리를](search-statistics-in-advanced-ediscovery.md) 구체화하여 결과 범위를 좁히는 데 도움이 될 수 있는 검색 통계를 볼 수 있습니다.

   - 검색 결과를 미리 보고 관련 데이터가 있는지 빠르게 확인할 수 있습니다.

   - 쿼리를 변경하고 검색을 다시 실행합니다.

3. **[검토 집합에 데이터를 추가합니다.](add-data-to-review-set.md)** 검색에서 원하는 데이터를 반환하는지 구성하고 확인한 다음에는 검색 결과를 검토 집합에 추가합니다. 검토 집합에 데이터를 추가하면 항목이 원래 위치에서 안전한 Azure Storage 위치로 복사됩니다. 검토 집합의 항목을 검토하고 분석할 때 철저하고 빠른 검색을 위해 데이터를 다시 인덱서합니다. 또한 검토 집합에 [비 Office 365](load-non-office-365-data-into-a-review-set.md)데이터를 추가할 수도 있습니다.

   또한 대화 검토 집합이라고 하는 데이터를 추가할 수 있는 특별한 종류의 검토 *집합이 있습니다.* 이러한 유형의 검토 집합은 Microsoft Teams에서와 같이 스레드된 대화를 재구성, 검토 및 내보내기 위한 대화 재구성 기능을 제공합니다. 자세한 내용은 [Advanced eDiscovery의 대화 검토를 참조하세요.](conversation-review-sets.md)

4. **검토 집합의 데이터를 검토하고 분석합니다.** 이제 데이터가 검토 집합에 추가되어 데이터 집합을 조사하는 경우와 가장 관련성이 높은 데이터 집합으로 줄이는 목표와 함께 다양한 도구 및 기능을 사용하여 사례 데이터를 보고 분석할 수 있습니다. 다음은 이 프로세스 중에 사용할 수 있는 몇 가지 도구 및 기능 목록입니다.

   - [문서를 보는 중입니다.](view-documents-in-review-set.md) 여기에는 검토 집합의 각 문서에 대한 메타데이터를 보고 기본 버전 또는 텍스트 버전으로 문서를 보는 작업도 포함됩니다.

   - [쿼리 및 필터를 만듭니다.](review-set-search.md) 모든 파일 메타데이터 속성을 검색하는 기능을 포함하여 다양한 검색 [](document-metadata-fields-in-advanced-ediscovery.md)조건을 사용하여 검색 쿼리를 만들어 사례 데이터를 보다 구체화하고 사례와 가장 관련된 데이터로 선형합니다. 또한 검토 집합 필터를 사용하여 검색 쿼리 결과에 추가 조건을 빠르게 적용하여 이러한 결과를 보다 구체화할 수도 있습니다.

   - [태그를 만들고 사용 합니다.](tagging-documents.md) 검토 집합의 문서에 태그를 적용하여 응답하는(또는 사례에 응답하지 않는) 태그를 식별한 다음 검색 쿼리를 만들 때 해당 태그를 사용하여 태그가 지정된 문서를 포함하거나 제외할 수 있습니다. 또한 태그를 지정하여 내보낼 문서를 결정할 수 있습니다.

   - [문서에 주석을 추가하고 문서를 다시 인쇄합니다.](view-documents-in-review-set.md#annotate-view) 검토에서 주석 도구를 사용하여 문서에 주석을 추가하고 문서의 콘텐츠를 작업 제품으로 재배치할 수 있습니다. 검토하는 동안 주석 또는 편집된 문서의 PDF 버전을 생성하여 문서의 편집되지 않은 네이티브 버전을 내보내는 위험을 줄입니다.

   - [대소문자 데이터를 분석합니다.](analyzing-data-in-review-set.md) Advanced eDiscovery의 분석 기능은 매우 강력합니다. Advanced eDiscovery에서는 문서를 분석하여 검토 집합에서 검토할 문서의 양을 추가로 줄일 수 있는 다양한 도구를 제공합니다. 또한 분석 실행 결과를 요약하는 분석 보고서도 생성합니다. 앞서 설명한 것 처럼 분석을 실행하면 [변호사-클라이언트 권한 검색 모델도 실행됩니다.](attorney-privilege-detection.md#use-the-attorney-client-privilege-detection-model)

5. **사례 데이터를 내보내고 다운로드합니다.** 사례 데이터를 수집, 검토 및 분석한 후의 마지막 단계는 외부 검토를 위해 Advanced eDiscovery에서 내보내거나 조사 팀 외부의 사람이 검토하는 것입니다. 데이터를 내보내는 과정은 2단계 프로세스입니다. 첫 번째 단계는 [](export-documents-from-review-set.md) 검토 집합에서 데이터를 내보내고 다른 Azure Storage 위치(Microsoft에서 제공하거나 조직에서 관리하는 Azure Storage 위치)에 복사하는 것입니다. 그런 다음 Azure Storage Explorer를 사용하여 [로컬](download-export-jobs.md) 컴퓨터에 데이터를 다운로드합니다. 내보내는 데이터 파일 외에 내보내기 패키지의 포함에는 내보내기 보고서, 요약 보고서 및 오류 보고서도 포함되어 있습니다.
