---
title: 고급 eDiscovery 사례에 custodians 추가
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
description: Advanced eDiscovery의 기본 제공 관리 도구를 사용하여 워크플로를 조정하고 관련 데이터 원본을 식별하는 방법에 대해 자세히 알아보습니다.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 9468fb889e9115b3652d1dba8a6c6632bb367fe3
ms.sourcegitcommit: 36d12e02f6fda199ae7f2fb72fe52d7e2b5b4efd
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/31/2020
ms.locfileid: "49740345"
---
# <a name="add-custodians-to-an-advanced-ediscovery-case"></a>고급 eDiscovery 사례에 custodians 추가

Advanced eDiscovery의 기본 제공 관리 도구를 사용하여 보호자 관리 및 사례와 관련된 관련성 있는 데이터 원본 식별과 관련된 워크플로를 조정합니다. 보유자를 추가하면 시스템에서 Exchange 사서함 및 비즈니스용 OneDrive 계정을 자동으로 식별하고 보류할 수 있습니다. 조사를 진행하는 동안, 보호자들이 액세스하거나 참가한 다른 데이터 원본(예: 사서함, 사이트 또는 Teams)을 식별할 수도 있습니다. 이 경우 관리 도구를 사용하여 해당 데이터 원본을 특정 관리인과 연결할 수 있습니다. 사례에 양도인을 추가하고 다른 데이터 원본을 연결한 후 데이터를 빠르게 보존하고 양도 데이터를 검색할 수 있습니다.

Advanced eDiscovery 사례에서 다음 4단계로 보안 주도를 추가하고 관리할 수 있습니다.

1. 양도인을 식별합니다.

2. 보호자 데이터 위치를 선택하십시오.

3. 보류 설정을 구성합니다.

4. 양도인을 검토하고 프로세스를 완료합니다.

   [![Advanced eDiscovery 사례의 원본 탭 ](../media/AeD-Sources-Tab.png)](../media/AeD-Sources-Tab.png#lightbox)

## <a name="make-sure-you-have-the-necessary-permissions"></a>필요한 사용 권한이 있는지 확인

사례에 관리자를 추가하려면 eDiscovery 관리자 역할 그룹의 구성원이 되어야 합니다. 이렇게 하면 보유자에 사례를 추가하고 보유 데이터 원본을 보류하는 데 필요한 권한이 부여됩니다. 자세한 내용은 [eDiscovery 권한 할당](get-started-with-advanced-ediscovery.md#step-2-assign-ediscovery-permissions)을 참조하세요.

## <a name="step-1-identify-custodians"></a>1단계: 양도자 식별

1. 적절한 eDiscovery 권한이 할당된 사용자 계정으로 이동하여 [https://compliance.microsoft.com](https://compliance.microsoft.com) 로그인합니다.

2. Microsoft 365 규정 준수 센터의 왼쪽 탐색 창에서 모두 표시를 클릭한 다음 **eDiscovery**> 클릭합니다.

3. Advanced **eDiscovery** 페이지에서 사례  탭을 클릭한 다음, 보금주를 추가할 사례를 선택합니다.

4. 데이터 원본 **탭을 클릭한** 다음 데이터 원본 추가를   >  클릭합니다.

5. 사용자 이름 또는 별칭의 첫 번째 부분을 입력하여 조직의 한 명 이상의 사용자를 케이스에 관리인으로 추가합니다. 올바른 사람을 찾은 후 이름을 선택하여 목록에 추가합니다.

## <a name="step-2-choose-custodian-data-locations"></a>2단계: 보호자 데이터 위치 선택

관리인을 선택한 후 시스템은 이러한 사용자 및 해당 데이터 원본을 자동으로 식별하고 확인하려고 시도합니다. 목록에 관리인을 추가한 후 도구에는 각 관리인에 대한 기본 사서함 및 OneDrive 계정이 자동으로 포함됩니다. 사례에 보호자 추가 시 이러한 데이터 원본을 포함하지 않을 수 있습니다.

관리인의 사서함 및 OneDrive 계정 외에, 다른 데이터 위치(예: SharePoint 사이트 또는 관리인이 구성원인 Microsoft 팀)에 연결될 수도 있습니다. 이를 통해 사례의 보호자와 연결된 다른 데이터 원본의 콘텐츠를 보존, 수집, 분석 및 검토할 수 있습니다.

관리자에 대한 기본 사서함 및 OneDrive 계정을 선택을 선택을 하려면

1. 각 보호자에 자동으로 연결된 기본 데이터 위치를 볼 수 있는 보호자 확장

2. 사서함 **또는**  **OneDrive** 옆의 지우기를 선택하여 이 관리인의 데이터 위치로 연결되지 못하게 하는 보호자 사서함 또는 OneDrive 계정을 제거합니다.

   ![관리인과 연결하도록 위치 구성](../media/ConfigureCustodianLocations.png)

다른 사서함, 사이트, Teams 또는 Yammer 특정 Yammer 연결:

1. 보호자 확장을 확장하여 다음 서비스를 표시하여 데이터 위치를 관리인과 연결합니다. 서비스 **옆에** 있는 편집을 클릭하여 데이터 위치를 추가합니다.

   - **Exchange**: 다른 사서함을 거래소에 연결하는 데 사용할 수 있습니다. 사용자 사서함 또는 메일 그룹의 이름 또는 별칭(최소 3자)을 검색 상자에 입력합니다. Custodian에 할당할 사서함을 선택한 다음 추가를 **클릭합니다.**

   - **SharePoint**: SharePoint 사이트를 양도자에 연결하는 데 사용할 수 있습니다. 목록에서 사이트를 선택하거나 검색 상자에 URL을 입력하여 사이트를 검색합니다. 양도자에 할당할 사이트를 선택한 다음 추가를 **클릭합니다.**

   - **Teams:** Microsoft Teams를 현재 구성원으로 할당하는 데 사용할 수 있습니다. 양도자에 할당할 팀을 선택한 다음 추가를 **클릭합니다.** 팀을 추가한 후 시스템은 자동으로 해당 팀에 연결된 SharePoint 사이트 및 그룹 사서함을 식별하고 찾아서 관리인에게 할당합니다.

   - **Yammer**: Yammer 현재 구성원인 그룹 그룹을 할당하는 데 사용할 수 있습니다. 양도자에 할당할 그룹을 선택한 다음 추가를 **클릭합니다.** 팀을 추가한 후 시스템은 자동으로 해당 그룹에 연결된 SharePoint 사이트 및 그룹 사서함을 식별하고 찾아서 관리인에게 할당합니다.

   > [!NOTE]
   > **Exchange** 및 **SharePoint** 위치 선택을 사용하여 다른 팀 또는 Yammer 그룹(보류자는 구성원이 아닌 그룹)을 교환원과 연결할 수 있습니다. 이 작업을 위해 각 팀 또는 그룹과 연결된 사서함과 사이트를 Yammer 합니다.

2. 표의 각 관리인을 확장하여 각 Yammer 할당된 사서함, 사이트, Teams 및 Yammer 그룹의 총 수를 볼 수 있습니다. 각 관리자에 대해 할당된 데이터 위치를 완료하면 이러한 연결은 Advanced eDiscovery 워크플로의 수집, 처리 및 검토 단계에서 유지 관리 및 사용됩니다.

3. 보유자 추가 및 데이터 위치 구성 후 다음을 클릭하여 보류 설정 **페이지로** 이동합니다.   

## <a name="step-3-configure-hold-settings"></a>3단계: 보류 설정 구성

 보유자 및 해당 데이터 위치를 마무리한 후 보유자 중 일부 또는 전체를 보류할 수 있습니다. 보유자는 보류를 해제하거나 보류에서 해제할 때까지 보유자와 연결된 모든 콘텐츠 위치에 있는 모든 콘텐츠가 보존됩니다. 경우에 따라 보유를 보류하지 않고 사례에 추가해야 할 수 있습니다.

보유자 및 데이터 원본을 보류합니다.

1. 보류 **설정 페이지에서** 보류 열 아래에 있는 확인란을 선택하여 개별 보유자에 보류를 적용할 **수** 있습니다.

   또는 열의 맨 위에 있는 보류 확인란을 선택하여  모든 보유자에 대한 보류를 할 수 있습니다.

2. 보유 선택을 확인하고 다음을 **클릭합니다.**

   > [!NOTE]
   > 보유자에 보류를 두지 않는 경우 보유자 및 관련 데이터 원본이 사례에 추가되지만 해당 데이터 원본의 콘텐츠는 사례와 연결된 보류로 보존되지 않습니다.

## <a name="step-4-review-the-custodians-and-complete-the-process"></a>4단계: 양도인 검토 및 프로세스 완료

실제로 보유자에 사례를 추가하기 전에 보유자 목록, 보유자에 할당된 데이터 위치 및 보류 설정을 검토할 수 있습니다.

1. 테이블의 각 보유자에 연결된 모든 데이터 원본 수 및 보류 설정을 확인하고 검토합니다. 필요한 경우 보유자 식별 **또는** 설정 보류 페이지로 돌아가서 변경합니다. 

2. **제출을** 클릭하여 보유자 및 해당 데이터 위치를 사례에 추가하고 모든 보유 설정을 적용합니다.

   새 보호자는 사례에 추가되고 데이터 원본 **탭에** 표시됩니다.

   [![데이터 원본 탭에 나열된 보호자 ](../media/DataSourcesTab.png)](../media/DataSourcesTab.png#lightbox)
