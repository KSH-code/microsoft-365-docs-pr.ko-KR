---
title: 앱 컨트롤 사용
description: ''
keywords: Microsoft Managed Desktop, Microsoft 365, 서비스, 문서
ms.service: m365-md
author: jaimeo
ms.author: jaimeo
manager: laurawi
audience: ITpro
ms.topic: article
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: 74cd1ec93058ed733e7d79da2d6932f04acfa5da
ms.sourcegitcommit: 63887d742c59cc660fc85537b335e98a9dc66fbe
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/18/2020
ms.locfileid: "45170717"
---
# <a name="work-with-app-control"></a>앱 컨트롤 사용

응용 프로그램 제어가 환경에 배포 되 면 사용자와 Microsoft의 관리 되는 데스크톱 작업에 모두 지속적인 책임이 있습니다. 예를 들어 환경에서 새 앱을 추가 하거나 신뢰할 수 있는 서명자를 추가 (또는 제거) 할 수 있습니다. 보안을 향상 시키기 위해 모든 앱은 최종 사용자에 게 릴리스하기 전에 코드 서명 되어야 합니다. 앱의 게시자 세부 정보에는 서명자에 대 한 정보가 포함 됩니다.


## <a name="add-a-new-app"></a>새 앱 추가

새 앱을 추가 하려면 다음 단계를 수행 합니다.

1. [Microsoft Intune](https://docs.microsoft.com/mem/intune/apps/apps-win32-app-management)에 앱을 추가 합니다.
2. 테스트 링의 모든 장치에 앱을 배포 합니다. 
3. 표준 비즈니스 프로세스에 따라 앱을 테스트 합니다. 
4. **응용 프로그램 및 서비스 Logs\Microsoft\Windows\AppLocker**에서 이벤트 뷰어를 확인 하 여 **8003** 또는 **8006** 이벤트를 검색 합니다. 이러한 이벤트는 앱이 차단 됨을 나타냅니다. 모든 앱 락커 이벤트와 해당 의미에 대 한 자세한 내용은 [AppLocker와 함께 이벤트 뷰어 사용](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/applocker/using-event-viewer-with-applocker)을 참조 하십시오.
5. 이러한 이벤트가 발견 되 면 Microsoft Managed Desktop 작업을 사용 하 여 서명자 요청을 엽니다.

## <a name="add-or-remove-a-trusted-signer"></a>신뢰할 수 있는 서명자 추가 (또는 제거)

서명자 요청을 열 때 먼저 몇 가지 중요 한 게시자 정보를 제공 해야 합니다. 그런 후 다음 단계를 수행 합니다.

1. [게시자 세부 정보를 수집](#gather-publisher-details)합니다.
2. Microsoft Managed Desktop 작업을 사용 하 여 티켓을 열어 서명자 규칙을 요청 하 고 다음 세부 정보를 포함 합니다.  
    - 응용 프로그램 이름 
    - 응용 프로그램 버전 
    - 설명 
    - 변경 유형 ("추가" 또는 "제거")  
    - 게시자 세부 정보 (예: "O = <publisher name> , L = <location> , S = State, C = Country") 

> [!NOTE]
> 앱에 대 한 트러스트를 제거 하려면 동일한 단계를 따르고 **변경 유형을** *제거*로 설정 합니다.

작업에서는 다음 일정에 따라 배포 그룹에 정책을 점진적으로 배포 합니다.


|배포 그룹  |정책 유형  |출시 시기  |
|---------|---------|---------|
|테스트     |  감사       |  일 0       |
|가장     | Enforced        | 1일        |
|신속한     | Enforced        |  3일       |
|폭     | Enforced        |  7일       |


롤아웃 중에 언제 든 지 배포를 일시 중지 하거나 롤백할 수 있습니다. 이렇게 하려면 작업이 포함 된 다른 서비스 요청을 엽니다.

> [!NOTE]
> 서명자 규칙의 릴리스를 일시 중지 하는 경우에는 해당 규칙을 먼저 롤백하거나 완료 해야 다른 롤아웃을 시작할 수 있습니다.

## <a name="gather-publisher-details"></a>게시자 세부 정보 수집

앱에 대 한 게시자 데이터에 액세스 하려면 다음 단계를 수행 합니다.

1. 감사 모드 정책이 적용 된 테스트 링에서 Microsoft Managed Desktop 장치를 찾습니다. 
2. 장치에 앱을 설치 해 봅니다.
3. 해당 장치에서 이벤트 뷰어를 엽니다. 
4. 이벤트 뷰어에서 **응용 프로그램 및 서비스 Logs\Microsoft\Windows**으로 이동한 다음 **AppLocker**를 선택 합니다. 
5. **8003** 또는 **8006** 이벤트를 찾은 다음 이벤트에서 정보를 복사 합니다. 
    - 응용 프로그램 이름 
    - 응용 프로그램 버전 
    - 설명 
    - 게시자 세부 정보 (예: "O = <publisher name> , L = <location> , S = State, C = Country") 