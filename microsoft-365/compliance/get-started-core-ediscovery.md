---
title: Microsoft 365에서 핵심 eDiscovery 사례 시작
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
description: 이 문서에서는 Microsoft 365에서 핵심 eDiscovery를 사용하는 방법을 설명합니다. eDiscovery 권한을 할당하고 사례를 만든 후 구성원을 추가하고 eDiscovery 보류를 만든 다음 조사와 관련된 데이터를 검색하고 내보낼 수 있습니다.
ms.openlocfilehash: 94c85987be4cbc5da7a378abb7ea74294f6fe740
ms.sourcegitcommit: 9ce9001aa41172152458da27c1c52825355f426d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/03/2020
ms.locfileid: "47357916"
---
# <a name="get-started-with-core-ediscovery"></a>핵심 eDiscovery 시작

Microsoft 365의 Core eDiscovery는 조직이 Microsoft 365 및 Office 365에서 콘텐츠를 검색하고 내보내는 데 사용할 수 있는 기본 eDiscovery 도구를 제공합니다. Core eDiscovery를 사용하여 Exchange 사서함, SharePoint 사이트, OneDrive 계정 및 Microsoft Teams와 같은 콘텐츠 위치에 eDiscovery 보류를 사용할 수도 있습니다. Core eDiscovery를 배포할 필요는 없지만 조직에서 Core eDiscovery를 사용하여 콘텐츠를 검색, 내보내고 보존하기 전에 IT 관리자 및 eDiscovery 관리자가 완료해야 하는 몇 가지 선행 작업이 있습니다.

이 문서에서는 Core eDiscovery를 설정하는 데 필요한 단계에 대해 논의합니다. 여기에는 Core eDiscovery에 액세스하고 콘텐츠 위치에 eDiscovery 보류를 설정하는 데 필요한 적절한 라이선싱을 보장하는 것뿐만 아니라 사례에 액세스하고 관리할 수 있도록 IT, 법률 및 조사 팀에 사용 권한을 할당하는 작업도 포함됩니다. 또한 이 문서에서는 사례를 사용하여 콘텐츠를 검색하고 내보내는 방법을 간략하게 소개합니다.

## <a name="step-1-verify-and-assign-appropriate-licenses"></a>1단계: 적절한 라이선스 확인 및 할당

Core eDiscovery 라이선스를 사용하려면 적절한 조직 구독 및 사용자당 라이선스가 필요합니다.

- **조직 구독:** Microsoft 365 규정 준수 센터 또는 Office 365 보안 & 준수 센터에서 Core eDiscovery에 액세스하고 보류 및 내보내기 기능을 사용하려면 조직에 Microsoft 365 E3 또는 Office 365 E3 이상 구독이 있어야 합니다.

- **사용자당 라이선스:** 사서함 및 사이트에 eDiscovery 보류를 설정하려면 조직 구독에 따라 사용자에게 다음 라이선스 중 하나를 할당해야 합니다.

  - Microsoft 365 E3 또는 Office 365 E3 라이선스 이상

   또는

  - Exchange Online 계획 2 또는 추가 기능 라이선스가 있는 Office 365 E1 Exchange Online Archiving 라이선스

  그리고

  - SharePoint Online 계획 2 또는 비즈니스용 OneDrive 계획 2 추가 기능 라이선스가 있는 Office 365 E1 라이선스
  
  라이선스를 할당하는 방법에 대한 자세한 내용은 사용자에게 라이선스 할당을 [참조하세요.](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users)

라이선스에 대한 자세한 내용은

- [Microsoft 365](https://docs.microsoft.com/office365/servicedescriptions/downloads/microsoft-365-compliance-licensing-comparison.xlsx)규정 준수 라이선싱 비교에서 "& 응답 검색" 솔루션을 다운로드하고 참조합니다.

- 보안 및 [& 센터 서비스 설명을 참조하세요.](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-securitycompliance-center)

## <a name="step-2-assign-ediscovery-permissions"></a>2단계: eDiscovery 사용 권한 할당

Core eDiscovery에 액세스하거나 Core eDiscovery 사례의 구성원으로 추가하려면 사용자에게 적절한 사용 권한이 할당되어야 합니다. 특히, 사용자를 Office 365 보안 및 준수 센터에서 eDiscovery 관리자 역할 & 추가해야 합니다. 이 역할 그룹의 구성원은 Core eDiscovery 사례를 만들고 관리할 수 있습니다. 구성원을 추가 및 제거하고, 사용자에게 eDiscovery 보류를 추가하고, 검색을 만들고 편집하고, Core eDiscovery 사례에서 콘텐츠를 내보낼 수 있습니다.

다음 단계를 완료하여 eDiscovery 관리자 역할 그룹에 사용자를 추가합니다.

1. Go to [https://protection.office.com/permissions](https://protection.office.com/permissions) and sign in using the credentials for an admin account in your Microsoft 365 or Office 365 organization.

2. 사용 권한 **페이지에서** **eDiscovery 관리자 역할 그룹을** 선택합니다.

3. eDiscovery 관리자 플라이아웃 페이지에서  **eDiscovery** 관리자 섹션 옆에 있는 편집을 클릭합니다.

4. 역할 그룹 편집 마법사의 **eDiscovery 관리자** 선택 페이지에서 검색 관리자 **선택을 클릭합니다.**

5. **추가를** 클릭한 다음 역할 그룹에 추가할 모든 사용자에 대한 확인란을 선택합니다.

6. **추가를** 클릭하여 선택한 사용자를 추가한 다음 완료를 **클릭합니다.**

7. **저장을** 클릭하여 역할 그룹에 사용자를 추가한 다음 **닫기를** 클릭하여 단계를 완료합니다.

### <a name="more-information-about-the-ediscovery-manager-role-group"></a>eDiscovery 관리자 역할 그룹에 대한 자세한 정보

eDiscovery 관리자 역할 그룹에는 두 개의 하위 그룹이 있습니다. 이러한 하위 그룹 간의 차이는 범위를 기준으로 합니다.

- **eDiscovery 관리자:** 작성하거나 구성원인 Core eDiscovery 사례를 보고 관리할 수 있습니다. 다른 eDiscovery 관리자가 사례를 만들고 두 번째 eDiscovery 관리자를 해당 사례의 구성원으로 추가하지 않는 경우 두 번째 eDiscovery 관리자는 준수 센터의 Core eDiscovery 페이지에서 사례를 보거나 열 수 없습니다. 일반적으로 조직의 대부분의 사람은 eDiscovery 관리자 하위 조직에 추가할 수 있습니다.

- **eDiscovery 관리자:** eDiscovery 관리자가 수행할 수 있는 모든 사례 관리 작업을 수행할 수 있습니다. 또한 eDiscovery 관리자(Administrator)는 다음과 같은 작업을 수행할 수 있습니다.

  - Core eDiscovery 페이지에 나열된 모든 사례를 볼 수 있습니다.
  
  - 자신을 사례의 구성원으로 추가한 후 조직에서 모든 사례를 관리합니다.

  - 조직의 모든 사례에 대한 사례 데이터에 액세스하고 내보낼 수 있습니다.

  액세스 범위가 넓기 때문에 조직에는 eDiscovery Administrators 하위 그룹 구성원인 관리자만 포함해야 합니다.

eDiscovery 사용 권한 및 eDiscovery 관리자 역할 그룹에 할당된 각 역할에 대한 설명에 대한 자세한 내용은 [eDiscovery](assign-ediscovery-permissions.md)권한 할당을 참조하세요.

## <a name="step-3-create-a-core-ediscovery-case"></a>3단계: Core eDiscovery 사례 만들기

다음 단계에서는 사례를 만들고 Core eDiscovery 사용을 시작해야 합니다. 다음 단계를 완료하여 사례를 만들고 구성원을 추가합니다. 사례를 만드는 사용자는 자동으로 구성원으로 추가됩니다.

1. 적절한 eDiscovery 권한이 할당된 사용자 계정의 자격 증명을 사용하여 [https://compliance.microsoft.com](https://compliance.microsoft.com) 로그인합니다. 조직 관리 역할 그룹의 구성원은 Core eDiscovery 사례를 만들 수 있습니다.

2. Microsoft 365 규정 준수 센터의 왼쪽 탐색 창에서 모두 표시를 클릭한 다음 **eDiscovery**> 클릭합니다.

3. Core **eDiscovery 페이지에서** 사례 **만들기를 클릭합니다.**

4. 새 **사례** 플라이아웃 페이지에서 사례에 이름(필수)을 지정한 다음 선택적 사례 번호와 설명을 입력합니다. 사례 이름은 조직에서 고유해야 합니다.

5. 사례를 **만들려면** 저장을 클릭합니다.

   새 사례가 만들어지며 Core eDiscovery 페이지에 표시됩니다. 새 사례를 표시하려면 **새로** 고침을 클릭해야 할 수 있습니다. 

## <a name="step-4-optional-add-members-to-a-core-ediscovery-case"></a>4단계(선택 사항): Core eDiscovery 사례에 구성원 추가

3단계에서 사례를 만들 때 사례를 사용할 유일한 사람인 경우 이 단계를 수행할 수 없습니다. 사례를 사용하여 eDiscovery 보류를 만들거나, 콘텐츠를 검색하거나, 검색 결과를 내보낼 수 있습니다. 다른 사용자(또는 역할 그룹)에게 사례에 대한 액세스 권한을 부여하려는 경우 이 단계를 수행합니다.

1. Microsoft 365 규정 준수 센터의 **Core eDiscovery** 페이지에서 구성원을 추가할 사례의 이름을 클릭합니다.

2. 이 사례 **관리 플라이아웃** 페이지의 구성원 관리에서 **추가를** 클릭하여 사례에 구성원을 추가합니다. 

    역할 그룹을 사례의 구성원으로 추가할 수 있습니다. 역할 **그룹 관리에서** 추가를 **클릭합니다.** 사례에 구성원으로 있는 역할 그룹만 할당할 수 있습니다. 이는 역할 그룹이 eDiscovery 사례에 구성원을 할당할 수 있는 구성원을 제어하기 때문에입니다.

3. 사례의 구성원으로 추가할 수 있는 사용자 또는 역할 그룹 목록에서 추가할 사용자(또는 역할 그룹) 이름 옆에 있는 확인란을 클릭합니다. 구성원으로 추가할 수 있는 사용자 목록이 많은  경우 검색 상자를 사용하여 목록에서 특정 사람을 검색합니다.
  
4. 사례의 구성원으로 추가할 사람 또는 역할 그룹을 선택한 후 추가를 **클릭합니다.**

5. **저장을** 클릭하여 새 사례 구성원 목록을 저장합니다.

## <a name="explore-the-core-ediscovery-workflow"></a>Core eDiscovery 워크플로 살펴보기

핵심 eDiscovery 사용을 시작하기 위해 관심 있는 사용자에 대해 eDiscovery 보류를 만들고, 조사와 관련된 콘텐츠를 검색한 다음 추가 검토를 위해 해당 데이터를 내보내는 간단한 워크플로가 있습니다. 이러한 각 단계에서는 탐색할 수 있는 몇 가지 확장된 Core eDiscovery 기능도 강조합니다.

![핵심 eDiscovery 워크플로](../media/CoreEdiscoveryWorkflow.png)

1. **[eDiscovery 보류를 만드시다.](create-ediscovery-holds.md)** 사례를 작성한 후의 첫 번째 단계는 조사에 관심 있는 사용자 콘텐츠 위치에 *보류(eDiscovery* 보류라고도 합니다.)입니다. 콘텐츠 위치에는 Exchange 사서함, SharePoint 사이트, OneDrive 계정, Microsoft Teams 및 Office 365 그룹과 연결된 사서함 및 사이트가 포함됩니다. 이 단계는 선택 사항이지만 eDiscovery 보류를 만들면 조사 중에 사례와 관련이 있을 수 있는 콘텐츠가 보존됩니다. eDiscovery 보류를 만들 때 특정 콘텐츠 위치에 있는 모든 콘텐츠를 보존하거나 쿼리 기반 보류를 만들어 보류 쿼리와 일치하는 콘텐츠만 보존할 수 있습니다. eDiscovery 보류를 만드는 또 다른 좋은 이유는 다음 단계에서 검색을 만들고 실행할 때 검색할 각 위치를 선택하지 않고 보류된 콘텐츠 위치를 빠르게 검색하는 것입니다. 조사를 완료한 후 만든 보류를 해제할 수 있습니다.

2. **[콘텐츠를 검색합니다.](search-for-content-in-core-ediscovery.md)** eDiscovery 보류를 만든 후 기본 제공 검색 도구를 사용하여 보류된 콘텐츠 위치를 검색합니다. 사례와 관련이 있을 수 있는 데이터의 다른 콘텐츠 위치를 검색할 수도 있습니다. 사례와 연결된 다양한 검색을 만들고 실행할 수 있습니다. 키워드, 속성 및 조건을 사용하여 [](keyword-queries-and-search-conditions.md) 사례와 관련성이 가장 높은 데이터로 검색 결과를 반환하는 검색 쿼리를 작성합니다. 또한 다음을 수행할 수 있습니다.

   - 검색 쿼리를 구체화하여 결과 범위를 좁히는 데 도움이 될 수 있는 검색 통계를 볼 수 있습니다.

   - 검색 결과를 미리 보고 관련 데이터가 있는지 빠르게 확인할 수 있습니다.

   - 쿼리를 변경하고 검색을 다시 실행합니다.

3. **[검색 결과를 내보내고 다운로드합니다.](export-content-in-core-ediscovery.md)** 조사와 관련된 데이터를 검색하고 찾은 후 조사 팀 외부의 사람이 검토하기 위해 Office 365에서 내보낼 수 있습니다. 데이터를 내보내는 과정은 2단계 프로세스입니다. 첫 번째 단계는 Office 365의 경우 검색 결과를 내보내는 것입니다. 이 작업을 수행하기 위해 검색 결과를 Microsoft에서 제공하는 Azure Storage 위치로 복사합니다. 다음 단계에서는 eDiscovery 내보내기 도구를 사용하여 로컬 컴퓨터에 콘텐츠를 다운로드합니다. 내보내는 데이터 파일 외에 내보내기 패키지의 포함에는 내보내기 보고서, 요약 보고서 및 오류 보고서도 포함되어 있습니다.
