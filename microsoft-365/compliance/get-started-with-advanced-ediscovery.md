---
title: Microsoft 365의 고급 eDiscovery 시작
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
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: 이 문서에서는 Microsoft 365에서 고급 eDiscovery 사용을 시작 하는 방법을 설명 합니다. 몇 가지 빠른 단계를 완료 한 후에는 고급 eDiscovery 도구를 사용할 준비가 된 것입니다. 첫 번째 단계는 사례를 만든 다음 고급 eDiscovery 기능 및 기능 사용을 시작 하는 것입니다.
ms.openlocfilehash: 1f3eb78ab9f9e96eaa95dbfbc7e087fa1514b836
ms.sourcegitcommit: 053d42480d8aa3792ecb0027ddd53d383a029474
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/07/2020
ms.locfileid: "43100871"
---
# <a name="get-started-with-advanced-ediscovery"></a>Advanced eDiscovery 시작

Microsoft 365의 고급 eDiscovery는 조직의 내부 및 외부 조사에 응답 하는 데이터를 보존, 수집, 검토, 분석 및 내보내기 위한 종단 간 워크플로를 제공 합니다. 고급 eDiscovery를 배포 하는 데 필요한 것은 아니지만 조직에서 고급 eDiscovery 사례를 만들고 사용 하 여 조사를 관리 하기 전에 IT 관리자 및 eDiscovery 관리자가 완료 해야 하는 몇 가지 필수 구성 요소가 있습니다.

이 문서에서는 고급 eDiscovery를 설정 하는 데 필요한 단계에 대해 설명 합니다. 여기에는 고급 eDiscovery에 액세스 하 고 사례에 custodians을 추가 하는 데 필요한 적절 한 라이선스를 보장 하 고, 법률 및 관리 팀이 사례에 액세스 하 고 관리할 수 있도록 권한을 할당 하는 것도 포함 됩니다. 또한이 문서에서는 법적 조사를 위해 고급 eDiscovery 워크플로를 관리 하는 사례를 사용 하는 방법에 대 한 개략적인 개요를 제공 합니다.

## <a name="step-1-verify-and-assign-appropriate-licenses"></a>1 단계: 적절 한 라이선스 확인 및 할당

고급 eDiscovery에 대 한 라이선스에는 적절 한 조직 구독 및 사용자 단위 라이선스가 필요 합니다.

- **조직 구독:** Microsoft 365 준수 센터 또는 Office 365 보안 & 준수 센터에서 고급 eDiscovery에 액세스 하려면 조직에 다음 중 하나가 있어야 합니다.

  - Microsoft 365 E5 또는 Office 365 E5 구독
  
  - E5 Compliance 추가 기능이 포함된 Microsoft 365 E3 구독

  - E5 eDiscovery 및 감사 추가 기능이 포함 된 Microsoft 365 E3 구독

  기존의 Microsoft 365 E5 요금제가 없고 고급 eDiscovery를 시도 하려는 경우 기존 Office 365 구독에 [microsoft 365을 추가](https://docs.microsoft.com/office365/admin/try-or-buy-microsoft-365) 하거나 Microsoft 365 E5 [평가판을 등록할](https://www.microsoft.com/microsoft-365/enterprise) 수 있습니다.

- **사용자별 라이선스:** 고급 eDiscovery 사례에서 사용자를 custodian으로 추가 하려면 조직 구독에 따라 해당 사용자에 게 다음 라이선스 중 하나를 할당 해야 합니다.

  - Microsoft 365: 사용자에 게 Microsoft 365 E5 라이선스, E5 준수 추가 기능 라이선스 또는 E5 eDiscovery 및 감사 추가 기능 라이선스를 할당 받아야 합니다.

  - Office 365: 사용자에 게 Office 365 E5 라이선스를 할당 해야 합니다.

   라이선스를 할당 하는 방법에 대 한 자세한 내용은 [사용자에 게 라이선스 할당](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users)을 참조 하세요.

> [!NOTE]
> 사용자는 고급 eDiscovery 사례에 custodians으로 추가 되는 E5 라이선스 (또는 적절 한 추가 기능 라이선스)만 필요 합니다. 고급 eDiscovery를 사용 하 여 사례를 관리 하 고 사례 데이터를 검토 하는 IT 관리자, eDiscovery 관리자, 변호사, paralegals 또는 investigators에는 E5 또는 추가 기능 라이선스가 필요 하지 않습니다.

## <a name="step-2-assign-ediscovery-permissions"></a>2 단계: eDiscovery 권한 할당

고급 eDiscovery에 액세스 하거나 고급 eDiscovery 사례의 구성원으로 추가 하려면 사용자에 게 적절 한 사용 권한이 할당 되어 있어야 합니다. 특히 Office 365 보안 & 준수 센터에서 eDiscovery 관리자 역할 그룹의 구성원으로 사용자를 추가 해야 합니다. 이 역할 그룹의 구성원은 고급 eDiscovery 사례를 만들고 관리할 수 있습니다. 구성원을 추가 및 제거 하 고, custodians 및 콘텐츠 위치를 보류 상태로 설정 하 고, 사례에 연결 된 검색을 관리 하 고, 대/소문자를 구분 하 여 검색 결과를 수정 하 고, 검토 집합의 데이터를 분석 하 고, 고급 eDiscovery 사례에서 내보내고 다운로드할 수 있습니다.

다음 단계를 완료 하 여 eDiscovery 관리자 역할 그룹에 사용자를 추가 합니다.

1. [https://protection.office.com/permissions](https://protection.office.com/permissions) 로 이동 하 여 Microsoft 365 조직의 관리자 계정에 대 한 자격 증명을 사용 하 여 로그인 합니다.

2. **사용 권한** 페이지에서 **eDiscovery 관리자** 역할 그룹을 선택 합니다.

3. EDiscovery 관리자 플라이 아웃 페이지에서 **Ediscovery 관리자** 섹션 옆에 있는 **편집** 을 클릭 합니다.

4. 역할 그룹 편집 마법사의 **EDiscovery 관리자 선택** 페이지에서 **검색 관리자 선택을**클릭 합니다.

5. **추가** 를 클릭 한 다음 역할 그룹에 추가 하려는 모든 사용자의 확인란을 선택 합니다.

6. **추가** 를 클릭 하 여 선택한 사용자를 추가한 다음 **완료**를 클릭 합니다.

7. **저장** 을 클릭 하 여 역할 그룹에 사용자를 추가 하 고 **닫기를** 클릭 하 여 단계를 완료 합니다.

### <a name="more-information-about-the-ediscovery-manager-role-group"></a>EDiscovery 관리자 역할 그룹에 대 한 추가 정보

EDiscovery 관리자 역할 그룹에는 두 개의 하위 그룹이 있습니다. 이러한 하위 그룹 간의 차이는 범위를 기준으로 합니다.

- **EDiscovery 관리자:** 사용자가 만들거나 구성원으로 속해 있는 고급 eDiscovery 사례를 보고 관리할 수 있습니다. 다른 eDiscovery 관리자가 사례를 만들지만 두 번째 eDiscovery 관리자를 해당 사례 구성원으로 추가 하지 않는 경우 두 번째 eDiscovery 관리자는 준수 센터의 고급 eDiscovery 페이지에서 사례를 보거나 열 수 없습니다. 일반적으로 조직의 대부분의 사용자가 eDiscovery 관리자 하위 그룹에 추가 될 수 있습니다.

- **EDiscovery 관리자:** EDiscovery 관리자가 수행할 수 있는 모든 사례 관리 작업을 수행할 수 있습니다. 또한 eDiscovery 관리자(Administrator)는 다음과 같은 작업을 수행할 수 있습니다.

  - 고급 eDiscovery 페이지에 나열 된 모든 사례를 봅니다.
  
  - 조직의 대/소문자를 구성원으로 추가한 후 조직에서 모든 사례를 관리 합니다.

  - 조직의 모든 경우에 대 한 사례 데이터 액세스 및 내보내기

  액세스 범위가 광범위 하기 때문에 조직은 eDiscovery Administrators 그룹의 구성원 인 관리자를 몇 명만 가져야 합니다.

Ediscovery 권한 및 eDiscovery 관리자 역할 그룹에 할당 된 각 역할에 대 한 설명에 대 한 자세한 내용은 [Security & 준수 센터에서 ediscovery 사용 권한 할당](assign-ediscovery-permissions.md)을 참조 하십시오.

## <a name="step-3-configure-global-settings-for-advanced-ediscovery"></a>3 단계: 고급 eDiscovery에 대 한 전역 설정 구성

조직의 사용자가 사례 만들기 및 사용을 시작 하기 전에 완료 해야 하는 마지막 단계는 조직의 모든 사례에 적용 되는 전역 설정을 구성 하는 것입니다. 현재로 서의 글로벌 설정은 *변호사-클라이언트 권한 검색* (나중에 더 많은 전역 설정을 사용할 수 있음)입니다. 이 설정은 검토 집합의 데이터를 분석할 때 변호사-클라이언트 권한 모델을 실행할 수 있도록 합니다. 이 모델은 컴퓨터 학습을 사용 하 여 문서에 본래 법적 정보가 포함 되어 있을 가능성을 확인 합니다. 또한 문서 참여자와 해당 모델을 설정할 때 제출 하는 변호사 목록을 비교 하 여 문서에 변호사 인 참가자가 하나 이상 있는지를 확인할 수 있습니다.

변호사 클라이언트 권한 검색 모델을 설정 하 고 사용 하는 방법에 대 한 자세한 내용은 [Set up 변호사-클라이언트 권한 검색에서 고급 eDiscovery](attorney-privilege-detection.md)를 참조 하세요.

> [!NOTE]
> 이 단계는 언제 든 지 수행할 수 있는 옵션입니다. 변호사를 구현 하지 않으면 고급 eDiscovery 사례를 만들고 사용 하는 것을 방지할 수 없습니다.

## <a name="step-4-create-an-advanced-ediscovery-case"></a>4 단계: 고급 eDiscovery 사례 만들기

다음 단계에서는 사례를 만들고 고급 eDiscovery를 사용 하 여 시작 합니다. 사례를 만들고 구성원을 추가 하려면 다음 단계를 완료 합니다. 서비스 케이스를 만드는 사용자는 자동으로 구성원으로 추가 됩니다.

1. [https://compliance.microsoft.com](https://compliance.microsoft.com) 적절 한 eDiscovery 권한이 할당 된 사용자 계정에 대 한 자격 증명을 사용 하 여으로 이동 하 여 로그인 합니다. 또한 조직 관리 역할 그룹의 구성원은 고급 eDiscovery 사례를 만들 수 있습니다.

2. Microsoft 365 준수 센터의 왼쪽에서 **모두 표시**를 클릭 한 다음 **eDiscovery > 고급**을 클릭 합니다.

3. **고급 eDiscovery** 페이지에서 **사례** 탭을 클릭 한 다음 **사례 만들기**를 클릭 합니다.

4. **새 eDiscovery 사례** 플라이 아웃 페이지에서 사례 이름을 (필수)로 지정 하 고 선택적 사례 번호 및 설명을 입력 합니다. 사례 이름은 조직 내에서 고유 해야 합니다.

5. **저장** 을 클릭 하 여 사례를 만듭니다.

   새 사례가 만들어지고 새 사례의 **설정** 탭이 표시 됩니다. 

6. **액세스 & 사용 권한** 타일의 **설정** 탭에서 **선택을**클릭 한 다음 **업데이트**를 클릭 합니다.

7. **업데이트**를 클릭합니다.

8. **이 사례** 플라이 아웃 관리 페이지의 **구성원 관리**에서 **추가** 를 클릭 하 여 사례에 구성원을 추가 합니다.

9. 사용자 목록에서 사례에 추가할 사용자의 이름 옆에 있는 확인란을 선택 합니다. 앞에서 설명한 것 처럼, 사례에 추가 하는 사용자에 게 적절 한 eDiscovery 권한이 할당 되었는지 확인해 보십시오.

10. 서비스 케이스의 구성원으로 추가할 사용자를 선택한 후 **추가**를 클릭 합니다.

11. **이 사례** 플라이 아웃 관리 페이지에서 **저장** 을 클릭 하 여 사례 구성원의 새 목록을 저장 합니다.

12. **홈** 탭을 클릭 하 여 사례 홈 페이지로 이동 합니다.

## <a name="explore-the-advanced-ediscovery-workflow"></a>Advanced eDiscovery 워크플로 살펴보기

고급 eDiscovery 사용을 시작 하려면 [일반적인 ediscovery 방법](overview-ediscovery-20.md#alignment-with-edrm)에 맞게 간단한 워크플로를 확인 하세요. 이러한 각 단계에서는 탐색할 수 있는 일부 확장 된 고급 eDiscovery 기능도 강조 표시 됩니다.

![고급 eDiscovery 워크플로](../media/AeDWorkflow.png)

1. **[Custodians를 사례에 추가](add-custodians-to-case.md)** 합니다. 사례를 만든 후 첫 번째 단계는 custodians를 추가 하는 것입니다. *Custodian* 은 사례와 관련이 있을 수 있는 문서 또는 전자 파일에 대 한 관리 권한이 있는 사용자입니다. Custodians를 사례에 추가할 때 발생 하거나 수행할 수 있는 몇 가지 사항은 다음과 같습니다.

   - Custodian의 Exchange 사서함, OneDrive 계정 및 custodian가 구성원으로 속해 있는 모든 Microsoft 팀 또는 Yammer 그룹의 데이터는 사례에서 custodial 데이터로 "표시" 될 수 있습니다.
  
   - Custodian 데이터는 *고급 인덱싱*이라는 프로세스를 통해 다시 인덱싱됩니다. 이렇게 하면 다음 단계에서 검색을 최적화 하는 데 도움이 됩니다.
  
   - Custodian 데이터를 보유할 수 있습니다. 이렇게 하면 조사 중에 사례와 관련이 있을 수 있는 데이터가 유지 됩니다.
  
   - 다른 데이터 원본을 custodian와 연결할 수 있습니다 (예: SharePoint 사이트 또는 Office 365 그룹을 custodian에 연결할 수 있음)이 데이터를 다시 인덱싱, 유지 및 검색할 수 있도록 하 여 custodian의 사서함 또는 OneDrive 계정에 있는 데이터와 동일 하 게 검색 합니다.

   - Advanced eDiscovery의 [통신 워크플로](managing-custodian-communications.md) 를 사용 하 여 custodians에 법적 보존 알림을 보낼 수 있습니다.

2. **[사례와 관련 된 데이터에 대 한 custodial 데이터 원본을 검색 합니다](collecting-data-for-ediscovery.md)**. Custodians를 사례에 추가한 후에는 기본 제공 검색 도구를 사용 하 여 사례와 관련이 있을 수 있는 데이터에 대 한 custodian 데이터 위치를 검색 합니다. 키워드, 속성 및 조건을 사용 하 여 사례와 관련성이 가장 높은 데이터로 검색 결과를 반환 하는 [검색 쿼리를 작성](building-search-queries.md) 합니다. 다음 작업도 수행할 수 있습니다.

   - 검색 쿼리를 구체화 하 여 결과 범위를 좁히는 데 도움이 될 수 있는 [검색 통계](search-statistics.md) 를 확인 합니다.

   - 검색 결과를 미리 보고 관련 데이터를 찾을 수 있는지 여부를 빠르게 확인할 수 있습니다.

   - 쿼리를 수정 하 고 검색을 다시 실행 합니다.

3. **[검토 집합에 데이터를 추가](add-data-to-review-set.md)** 합니다. 구성 및 검색에서 원하는 데이터가 반환 되는지 확인 한 후에는 검토 집합에 검색 결과를 추가 합니다. 검토 집합에 데이터를 추가 하면 항목이 원래 위치에서 안전한 Azure 저장소 위치로 복사 됩니다. 검토 집합의 항목을 검토 하 고 분석할 때 완벽 하 고 빠른 검색을 위해 데이터를 다시 인덱싱할 수 있습니다. 또한 [검토 집합에 Office가 아닌 365 데이터를 추가할](load-non-office-365-data-into-a-review-set.md)수도 있습니다.

   또한 *대화 검토 집합*이라는 특별 한 종류의 검토를 통해 데이터를 추가할 수 있습니다. 이러한 유형의 검토 집합은 대화 재구성 기능을 제공 하 여 Microsoft 팀과 같은 스레드된 대화를 재구성, 검토 및 내보낼 수 있습니다. 자세한 내용은 [Advanced eDiscovery에서 대화 검토](conversation-review-sets.md)를 참조 하세요.

4. **검토 집합에서 데이터를 검토 하 고 분석**합니다. 이제 데이터가 검토 집합에 포함 된 경우에는 다양 한 도구 및 기능을 사용 하 여 데이터 집합을 파악 하 고 있는 사례와 가장 관련성이 높은 수준으로 줄이는 목표에 따라 사례 데이터를 보고 분석할 수 있습니다. 다음은이 프로세스 중에 사용할 수 있는 몇 가지 도구 및 기능 목록입니다.

   - [문서를 봅니다](view-documents-in-review-set.md). 여기에는 검토 집합의 각 문서에 대 한 메타 데이터 보기 및 해당 기본 버전 또는 텍스트 버전에서 문서 보기 등이 포함 됩니다.

   - [쿼리 및 필터를 만듭니다](review-set-search.md). 모든 [파일 메타 데이터 속성](document-metadata-fields-in-advanced-ediscovery.md)을 검색 하는 기능을 비롯 한 다양 한 검색 조건을 사용 하 여 검색 쿼리를 만들면 사례 데이터를 사례에 가장 적합 한 cull 합니다. 또한 검토 집합 필터를 사용 하 여 검색 쿼리 결과에 추가 조건을 빠르게 적용 하 여 이러한 결과를 보다 구체화할 수 있습니다. 

   - [태그를 만들고 사용](tagging-documents.md)합니다. 검토 집합의 문서에 태그를 적용 하 여 응답 하는 (또는 해당 사례에 응답 하지 않음)를 식별 한 다음 검색 쿼리를 작성 하 여 태그가 지정 된 문서를 포함 하거나 제외할 때 해당 태그를 사용할 수 있습니다. 또한 태그를 지정 하 여 내보낼 문서를 결정할 수도 있습니다.

   - [문서에 주석을 달고 교정](view-documents-in-review-set.md#annotate-view)합니다. 검토에서 주석 도구를 사용 하 여 문서에 주석을 달고 문서 내용을 작업 산출물로 교정 하는 데 사용할 수 있습니다. 검토 중에 PDF 버전의 주석이 지정 되거나 redacted 문서를 생성 하 여 unredacted 네이티브 버전의 문서를 내보낼 위험을 줄입니다.

   - [사례 데이터를 분석](analyzing-data-in-review-set.md)합니다. 고급 eDiscovery의 분석 기능은 강력 합니다. 검토 설정에서 데이터에 대 한 분석을 실행 한 후에는 검토 해야 하는 문서 크기를 줄이는 데 도움이 될 수 있는 유사 중복 검색, 전자 메일 스레딩 및 테마와 같은 분석을 수행 합니다. 또한 실행 중인 분석 결과를 요약 한 분석 보고서도 생성 합니다. 앞에서 설명한 것 처럼 실행 분석 [은 변호사 클라이언트 권한 검색 모델](attorney-privilege-detection.md#use-the-attorney-client-privilege-detection-model)도 실행 합니다.

5. **사례 데이터를 내보내고 다운로드**합니다. 사례 데이터를 수집 하 고, 검토 하 고, 분석 한 후 마지막 단계는 조사 팀 외부의 사용자가 외부를 검토 하거나 검토할 수 있도록 고급 eDiscovery에서이를 내보내는 것입니다. 데이터 내보내기는 두 단계로 진행 됩니다. 첫 번째 단계는 검토 집합을 내보내 다른 Azure Storage location (Microsoft에서 제공 하거나 조직에서 관리 하는 위치)으로 [내보내는](export-documents-from-review-set.md) 것입니다. 그런 다음 Azure Storage Explorer를 사용 하 여 로컬 컴퓨터에 데이터를 [다운로드](download-export-jobs.md) 합니다. 내보낸 데이터 파일 외에도 내보내기 패키지의 포함에는 내보내기 보고서, 요약 보고서 및 오류 보고서가 포함 되어 있습니다.
