---
title: Microsoft 365에서 핵심 eDiscovery 사례 시작
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
description: 이 문서에서는 Microsoft 365에서 코어 eDiscovery 사용을 시작 하는 방법에 대해 설명 합니다. EDiscovery 권한을 할당 하 고 사례를 만든 후에는 구성원을 추가 하 고, eDiscovery 보류를 만든 다음, 조사와 관련 된 데이터를 검색 하 고 내보낼 수 있습니다.
ms.openlocfilehash: c9c3d8c3832703e8dbbcf8b2c04a566af0f5eb6b
ms.sourcegitcommit: 60c1932dcca249355ef7134df0ceb0e57757dc81
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/29/2020
ms.locfileid: "43943387"
---
# <a name="get-started-with-core-ediscovery"></a>핵심 eDiscovery 시작

Microsoft 365의 핵심 eDiscovery는 조직이 Microsoft 365 및 Office 365에서 콘텐츠를 검색 하 고 내보내는 데 사용할 수 있는 기본 eDiscovery 도구를 제공 합니다. 또한 코어 eDiscovery를 사용 하 여 Exchange 사서함, SharePoint 사이트, OneDrive 계정, Microsoft 팀 등의 콘텐츠 위치에 eDiscovery 보류를 배치할 수 있습니다. 핵심 eDiscovery를 배포 하는 데 아무 것도 필요 하지 않지만 조직에서 핵심 eDiscovery를 사용 하 여 콘텐츠를 검색, 내보내기 및 보존 하기 전에 IT 관리자 및 eDiscovery 관리자가 완료 해야 하는 몇 가지 필수 작업을 수행할 수 있습니다.

이 문서에서는 핵심 eDiscovery를 설정 하는 데 필요한 단계에 대해 설명 합니다. 여기에는 핵심 eDiscovery에 액세스 하 고 콘텐츠 위치에 eDiscovery 보류를 배치 하는 데 필요한 적절 한 라이선스를 보장 하는 것과 IT, 법률 및 조사 팀이 서비스 케이스에 액세스 하 고 관리할 수 있도록 권한을 할당 하는 것도 포함 됩니다. 이 문서에서는 콘텐츠를 검색 하 고 내보내는 사례를 사용 하는 방법에 대 한 간략 한 개요도 제공 합니다.

## <a name="step-1-verify-and-assign-appropriate-licenses"></a>1 단계: 적절 한 라이선스 확인 및 할당

핵심 eDiscovery에 대 한 라이선스에는 적절 한 조직 구독 및 사용자 단위 라이선스가 필요 합니다.

- **조직 구독:** Microsoft 365 준수 센터 또는 Office 365 보안 & 준수 센터의 핵심 eDiscovery에 액세스 하 고 보류 및 내보내기 기능을 사용 하려면 조직에 Microsoft 365 E3 또는 Office 365 E3 구독 이상이 있어야 합니다.

- **사용자별 라이선스:** 사서함 및 사이트에 eDiscovery 보류를 설정 하려면 조직 구독에 따라 사용자에 게 다음 라이선스 중 하나를 할당 해야 합니다.

  - Microsoft 365 E3 또는 Office 365 E3 라이선스 이상

   또는

  - Exchange Online 계획 2 또는 Exchange Online 보관용 추가 기능 라이선스가 있는 Microsoft 365 E1 또는 Office 365 E1 라이선스

  그리고

  - SharePoint Online 계획 2 또는 비즈니스용 OneDrive 요금제 2 추가 기능 라이선스가 있는 Microsoft 365 E1 또는 Office 365 E1 라이선스
  
  라이선스를 할당 하는 방법에 대 한 자세한 내용은 [사용자에 게 라이선스 할당](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users)을 참조 하세요.

라이선스에 대 한 자세한 내용:

- [Microsoft 365 준수 라이선스 비교](https://docs.microsoft.com/office365/servicedescriptions/downloads/microsoft-365-compliance-licensing-comparison.xlsx)의 "응답 & 검색" 솔루션을 다운로드 하 여 확인 합니다.

- [보안 & 준수 센터 서비스 설명을](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-securitycompliance-center)참조 하세요.

## <a name="step-2-assign-ediscovery-permissions"></a>2 단계: eDiscovery 권한 할당

핵심 eDiscovery에 액세스 하거나 코어 eDiscovery 사례의 구성원으로 추가 하려면 사용자에 게 적절 한 사용 권한이 할당 되어야 합니다. 특히 Office 365 보안 & 준수 센터에서 eDiscovery 관리자 역할 그룹의 구성원으로 사용자를 추가 해야 합니다. 이 역할 그룹의 구성원은 핵심 eDiscovery 사례를 만들고 관리할 수 있습니다. 구성원을 추가 및 제거 하 고, eDiscovery 보류를 사용자에 게 배치 하 고, 검색을 만들고 편집 하 고, 핵심 eDiscovery 사례에서 콘텐츠를 내보낼 수 있습니다.

다음 단계를 완료 하 여 eDiscovery 관리자 역할 그룹에 사용자를 추가 합니다.

1. [https://protection.office.com/permissions](https://protection.office.com/permissions) 로 이동 하 여 Microsoft 365 또는 Office 365 조직의 관리자 계정에 대 한 자격 증명을 사용 하 여 로그인 합니다.

2. **사용 권한** 페이지에서 **eDiscovery 관리자** 역할 그룹을 선택 합니다.

3. EDiscovery 관리자 플라이 아웃 페이지에서 **Ediscovery 관리자** 섹션 옆에 있는 **편집** 을 클릭 합니다.

4. 역할 그룹 편집 마법사의 **EDiscovery 관리자 선택** 페이지에서 **검색 관리자 선택을**클릭 합니다.

5. **추가** 를 클릭 한 다음 역할 그룹에 추가 하려는 모든 사용자의 확인란을 선택 합니다.

6. **추가** 를 클릭 하 여 선택한 사용자를 추가한 다음 **완료**를 클릭 합니다.

7. **저장** 을 클릭 하 여 역할 그룹에 사용자를 추가 하 고 **닫기를** 클릭 하 여 단계를 완료 합니다.

### <a name="more-information-about-the-ediscovery-manager-role-group"></a>EDiscovery 관리자 역할 그룹에 대 한 추가 정보

EDiscovery 관리자 역할 그룹에는 두 개의 하위 그룹이 있습니다. 이러한 하위 그룹 간의 차이는 범위를 기준으로 합니다.

- **EDiscovery 관리자:** 사용자가 만들거나 구성원으로 속해 있는 핵심 eDiscovery 사례를 보고 관리할 수 있습니다. 다른 eDiscovery 관리자가 사례를 만들지만 두 번째 eDiscovery 관리자를 해당 사례 구성원으로 추가 하지 않는 경우 두 번째 eDiscovery 관리자는 준수 센터의 핵심 eDiscovery 페이지에서 사례를 보거나 열 수 없습니다. 일반적으로 조직의 대부분의 사용자가 eDiscovery 관리자 하위 그룹에 추가 될 수 있습니다.

- **EDiscovery 관리자:** EDiscovery 관리자가 수행할 수 있는 모든 사례 관리 작업을 수행할 수 있습니다. 또한 eDiscovery 관리자(Administrator)는 다음과 같은 작업을 수행할 수 있습니다.

  - 핵심 eDiscovery 페이지에 나열 된 모든 사례를 봅니다.
  
  - 조직의 대/소문자를 구성원으로 추가한 후 조직에서 모든 사례를 관리 합니다.

  - 조직의 모든 경우에 대 한 사례 데이터 액세스 및 내보내기

  액세스 범위가 광범위 하기 때문에 조직은 eDiscovery Administrators 그룹의 구성원 인 관리자를 몇 명만 가져야 합니다.

Ediscovery 권한 및 eDiscovery 관리자 역할 그룹에 할당 된 각 역할에 대 한 설명에 대 한 자세한 내용은 [ediscovery 권한 할당](assign-ediscovery-permissions.md)을 참조 하십시오.

## <a name="step-3-create-a-core-ediscovery-case"></a>3 단계: 핵심 eDiscovery 사례 만들기

다음 단계에서는 사례를 만들고 핵심 eDiscovery 사용을 시작 합니다. 사례를 만들고 구성원을 추가 하려면 다음 단계를 완료 합니다. 서비스 케이스를 만드는 사용자는 자동으로 구성원으로 추가 됩니다.

1. [https://compliance.microsoft.com](https://compliance.microsoft.com) 적절 한 eDiscovery 권한이 할당 된 사용자 계정의 자격 증명을 사용 하 여으로 이동 하 여 로그인 합니다. 또한 조직 관리 역할 그룹의 구성원은 핵심 eDiscovery 사례를 만들 수 있습니다.

2. Microsoft 365 준수 센터의 왼쪽 탐색 창에서 **모두 표시**를 클릭 한 다음 **eDiscovery > 코어**를 클릭 합니다.

3. **핵심 eDiscovery** 페이지에서 **사례 만들기**를 클릭 합니다.

4. **새 사례** 플라이 아웃 페이지에서 사례 이름을 (필수)로 지정 하 고 선택적 사례 번호 및 설명을 입력 합니다. 사례 이름은 조직 내에서 고유 해야 합니다.

5. **저장** 을 클릭 하 여 사례를 만듭니다.

   새 사례가 만들어져 코어 eDiscovery 페이지에 표시 됩니다. 새 대/소문자를 표시 하려면 **새로 고침** 을 클릭 해야 할 수 있습니다. 

## <a name="step-4-optional-add-members-to-a-core-ediscovery-case"></a>4 단계 (선택 사항): 핵심 eDiscovery 사례에 구성원 추가

3 단계에서 사례를 만드는 경우 사례를 사용할 사람만 있으면이 단계를 수행 하지 않아도 됩니다. 사례 사용을 시작 하 여 eDiscovery 보류를 만들거나, 콘텐츠를 검색 하거나, 검색 결과를 내보낼 수 있습니다. 다른 사용자 (또는 역할 그룹)에 게 사례에 대 한 액세스 권한을 부여 하려는 경우이 단계를 수행 합니다.

1. Microsoft 365 준수 센터의 **핵심 eDiscovery** 페이지에서 구성원을 추가 하려는 사례 이름을 클릭 합니다.

2. **이 사례** 플라이 아웃 관리 페이지의 **구성원 관리**에서 **추가** 를 클릭 하 여 사례에 구성원을 추가 합니다. 

    역할 그룹을 사례 구성원으로 추가할 수도 있습니다. **역할 그룹 관리**에서 **추가**를 클릭 합니다. 사용자가 구성원으로 속해 있는 역할 그룹은 사례에만 할당할 수 있습니다. 이는 역할 그룹이 eDiscovery 사례에 구성원을 할당할 수 있는 사람을 제어 하기 때문입니다.

3. 사례 구성원으로 추가할 수 있는 사용자 또는 역할 그룹의 목록에서 추가 하려는 사람 (또는 역할 그룹)의 이름 옆에 있는 확인란을 클릭 합니다. 구성원으로 추가할 수 있는 사용자 목록이 많은 경우에는 **검색** 상자를 사용 하 여 목록에서 특정 사용자를 검색 합니다.
  
4. 사례 구성원으로 추가할 사용자 또는 역할 그룹을 선택한 후 **추가**를 클릭 합니다.

5. **저장** 을 클릭 하 여 사례 구성원의 새 목록을 저장 합니다.

## <a name="explore-the-core-ediscovery-workflow"></a>핵심 eDiscovery 워크플로 살펴보기

핵심 eDiscovery 사용을 시작 하려면 관심 있는 사용자를 위해 eDiscovery 보류를 만들고 조사와 관련 된 콘텐츠를 검색 한 다음 추가 검토를 위해 해당 데이터를 내보내는 간단한 워크플로를 참조 하세요. 이러한 각 단계에서는 탐색할 수 있는 몇 가지 확장 된 필수 eDiscovery 기능도 강조 표시 됩니다.

![핵심 eDiscovery 워크플로](../media/CoreEdiscoveryWorkflow.png)

1. **[EDiscovery 보류를 만듭니다](create-ediscovery-holds.md)**. 사례를 만든 후 첫 번째 단계는 조사에 관심이 있는 사용자의 콘텐츠 위치에 보류 ( *eDiscovery 보류*라고도 함)를 배치 하는 것입니다. 콘텐츠 위치에는 Exchange 사서함, SharePoint 사이트, OneDrive 계정, Microsoft 팀 및 Office 365 그룹과 연결 된 사서함 및 사이트가 포함 됩니다. 이 단계는 선택 사항 이지만 eDiscovery 보존을 만들려면 조사 중에 사례와 관련이 있을 수 있는 콘텐츠를 보존 합니다. EDiscovery 보류를 만들 때 특정 콘텐츠 위치의 모든 콘텐츠를 유지 하거나 쿼리 기반 보존을 만들어 보류 쿼리와 일치 하는 콘텐츠만 보존할 수 있습니다. 콘텐츠를 보존 하는 것 외에도 eDiscovery 보류를 만드는 또 다른 이유는 다음 단계에서 검색을 만들고 실행할 때 보류 중인 콘텐츠 위치를 빠르게 검색 하는 것입니다. 조사를 완료 한 후에는 직접 만든 모든 보류를 해제할 수 있습니다.

2. **[콘텐츠를 검색](search-for-content-in-core-ediscovery.md)** 합니다. EDiscovery 보류를 만든 후 기본 제공 검색 도구를 사용 하 여 보류 중인 콘텐츠 위치를 검색 합니다. 사례와 관련이 있을 수 있는 데이터에 대 한 다른 콘텐츠 위치를 검색할 수도 있습니다. 사례와 연결 된 다른 검색을 만들고 실행할 수 있습니다. 키워드, 속성 및 조건을 사용 하 여 사례와 관련성이 가장 높은 데이터로 검색 결과를 반환 하는 [검색 쿼리를 작성](keyword-queries-and-search-conditions.md) 합니다. 다음 작업도 수행할 수 있습니다.

   - 검색 쿼리를 구체화 하 여 결과 범위를 좁히는 데 도움이 될 수 있는 검색 통계를 확인 합니다.

   - 검색 결과를 미리 보고 관련 데이터를 찾을 수 있는지 여부를 빠르게 확인할 수 있습니다.

   - 쿼리를 수정 하 고 검색을 다시 실행 합니다.

3. **[검색 결과를 내보내고 다운로드](export-content-in-core-ediscovery.md)** 합니다. 조사와 관련 된 데이터를 검색 하 고 찾은 후 조사 팀 외부의 사용자가 검토를 위해 Office 365에서이를 내보낼 수 있습니다. 데이터 내보내기는 두 단계로 진행 됩니다. 첫 번째 단계는 검색 결과를 Office 365의 소문자로 내보내는 것입니다. 검색 결과를 Microsoft에서 제공한 Azure 저장소 위치로 복사 하 여이 작업을 수행 합니다. 다음 단계에서는 eDiscovery 내보내기 도구를 사용 하 여 콘텐츠를 로컬 컴퓨터에 다운로드 합니다. 내보낸 데이터 파일 외에도 내보내기 패키지의 포함에는 내보내기 보고서, 요약 보고서 및 오류 보고서가 포함 되어 있습니다.
