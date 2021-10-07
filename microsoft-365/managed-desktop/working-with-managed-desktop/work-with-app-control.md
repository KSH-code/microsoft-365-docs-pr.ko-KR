---
title: 앱 제어 작업
description: ''
keywords: Microsoft Managed Desktop, Microsoft 365, 서비스, 문서
ms.service: m365-md
author: jaimeo
ms.author: jaimeo
manager: laurawi
audience: ITpro
ms.topic: article
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
ms.openlocfilehash: c1600381062aa61b79ba757d530afef07aca26e6
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2021
ms.locfileid: "60208676"
---
# <a name="work-with-app-control"></a>앱 제어 작업

사용자 환경의 앱 컨트롤이 배포되면 사용자와 사용자 모두에게 Microsoft Managed Desktop 지속적인 책임이 있습니다. 예를 들어 환경에 새 앱을 추가하거나 신뢰할 수 있는 서명자(또는 제거)를 할 수 있습니다. 보안을 강화하기 위해 사용자에게 릴리스하기 전에 모든 앱에 코드 서명을 해야 합니다. 앱의 게시자 세부 정보에는 서명자에 대한 정보가 포함됩니다.


## <a name="add-a-new-app"></a>새 앱 추가

새 앱을 추가하기 위해 다음 단계를 수행합니다.

1. 에 앱을 [Microsoft Intune.](/mem/intune/apps/apps-win32-app-management)
2. 테스트 링의 모든 디바이스에 앱을 배포합니다. 
3. 표준 비즈니스 프로세스에 따라 앱을 테스트합니다. 
4. Application **and Services Logs\Microsoft\Windows\AppLocker에서** 이벤트 뷰어를 확인하고 **8003 또는 8006** 이벤트를 **찾아야** 합니다. 이러한 이벤트는 앱이 차단될 것 것 을 나타냅니다. 모든 앱 보관 이벤트 및 해당 의미에 대한 자세한 내용은 [AppLocker와 함께](/windows/security/threat-protection/windows-defender-application-control/applocker/using-event-viewer-with-applocker)이벤트 뷰어 사용을 참조하세요.
5. 이러한 이벤트가 발견되는 경우 Operations를 통해 서명자 요청을 Microsoft Managed Desktop 을 하세요.

## <a name="add-or-remove-a-trusted-signer"></a>신뢰할 수 있는 서명자 추가(또는 제거)

서명자 요청을 열면 먼저 몇 가지 중요한 게시자 세부 정보를 제공해야 합니다. 그런 다음 다음 단계를 수행합니다.

1. [게시자 세부 정보를 수집합니다.](#gather-publisher-details)
2. Microsoft Managed Desktop 티켓을 열어 서명자 규칙을 요청하고 다음 세부 정보를 포함합니다.  
    - 애플리케이션 이름 
    - 응용 프로그램 버전 
    - 설명 
    - 변경 유형("추가" 또는 "제거")  
    - Publisher 세부 정보(예: "O= <publisher name> ,L= <location> ,S=State,C=Country") 

> [!NOTE]
> 앱에 대한 트러스트는 제거하려면 동일한 단계를 따르지만 변경 유형을 **설정하여** 를 *제거합니다.*

작업은 이 일정에 따라 배포 그룹에 정책을 점진적으로 배포합니다.


|배포 그룹  |정책 유형  |출시 시기  |
|---------|---------|---------|
|테스트     |  감사       |  0일       |
|첫 번째     | Enforced        | 1일        |
|빠르기     | Enforced        |  2일       |
|광범위     | Enforced        |  3일       |


배포 중에는 배포를 일시 중지하거나 롤백할 수 있습니다. 이 작업을 수행하기 위해 Operations를 통해 다른 서비스 요청을 열 수 있습니다.

> [!NOTE]
> 서명자 규칙 릴리스를 일시 중지하는 경우 다른 출시를 시작하기 전에 해당 규칙을 롤백하거나 완료해야 합니다.

## <a name="gather-publisher-details"></a>게시자 세부 정보 수집

앱의 게시자 데이터에 액세스하기 위해 다음 단계를 수행합니다.

1. 감사 Microsoft Managed Desktop 정책이 적용된 테스트 링에서 디바이스를 찾을 수 있습니다. 
2. 디바이스에 앱을 설치하려고 합니다.
3. 디바이스에서 이벤트 뷰어를 니다. 
4. 이벤트 뷰어에서 응용 프로그램 및 서비스 **로그\Microsoft\Windows** 로 이동한 다음 **AppLocker 를 선택합니다.** 
5. **8003** 또는 **8006 이벤트를 찾은** 다음 이벤트에서 정보를 복사합니다. 
    - 애플리케이션 이름 
    - 응용 프로그램 버전 
    - 설명 
    - Publisher 세부 정보(예: "O= <publisher name> , L= <location> , S=State, C=Country")