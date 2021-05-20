---
title: Microsoft Defender 바이러스 백신 알림 구성
description: 엔드포인트에서 표준 및 추가 Microsoft Defender 바이러스 백신 알림을 모두 구성하고 사용자 지정하는 방법을 알아봅니다.
keywords: 알림, 수비수, 바이러스 백신, 끝점, 관리, 관리자
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 05/17/2021
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.topic: article
ms.openlocfilehash: f885b6d7991e4175cd14be5bbe9e0a7c96b1580f
ms.sourcegitcommit: 0936f075a1205b8f8a71a7dd7761a2e2ce6167b3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/19/2021
ms.locfileid: "52572348"
---
# <a name="configure-the-notifications-that-appear-on-endpoints"></a>끝점에 나타나는 알림 구성

**적용 대상:**

- [엔드포인트용 Microsoft Defender](/microsoft-365/security/defender-endpoint/)

Windows 10 맬웨어 탐지 및 수정에 대한 응용 프로그램 알림은 보다 강력하고 일관되며 간결합니다.

수동으로 트리거되고 예약된 검사가 완료되고 위협이 감지되면 끝점에 알림이 표시됩니다. 이러한 알림은 **알림 센터에도** 표시되며 검사 및 위협 탐지 요약은 정기적인 시간 간격으로 표시됩니다.

재부팅 알림 또는 위협이 검색되고 수정된 시기와 같이 끝점에 표준 알림이 표시되는 방식을 구성할 수도 있습니다.

## <a name="configure-the-additional-notifications-that-appear-on-endpoints"></a>끝점에 나타나는 추가 알림 구성

최근 위협 탐지 요약, [Windows 보안 앱](microsoft-defender-security-center-antivirus.md) 및 그룹 정책과 같은 추가 알림 표시를 구성할 수 있습니다.

> [!NOTE]
> Windows 10 버전 1607에서 기능은 **향상된 알림이라고** 불렸으며 **보안** Windows Defender Windows 설정 업데이트 & 아래에서 구성할 수  >    >  **있습니다.** Windows 10 모든 버전의 그룹 정책 설정에서 **향상된 알림이라고** 합니다.

> [!IMPORTANT]
> 추가 알림을 사용하지 않도록 설정하면 위협 탐지 및 수정 경고와 같은 중요한 알림이 비활성화되지 않습니다.

**Windows 보안 앱을 사용하여 추가 알림을 사용하지 않도록 설정합니다.**

1. 작업 표시줄의 쉴드 아이콘을 클릭하거나 보안에 대한 시작 메뉴를 검색하여 Windows 보안 앱을 **엽니다.**

2. **바이러스 & 위협 보호** 타일(또는 왼쪽 메뉴 표시줄의 쉴드 아이콘)을 선택한 다음 위협 보호 설정을 & 바이러스를 선택합니다. 

3. **알림** 섹션으로 스크롤하여 **알림 설정 변경을** 클릭합니다.

4. 스위치를 **끄거나** **켜기로** 밀어 내거나 추가 알림을 비활성화하거나 활성화합니다.

**그룹 정책을 사용하여 추가 알림을 사용하지 않도록 설정합니다.**

1. 그룹 정책 관리 컴퓨터에서 [그룹 정책 관리 콘솔을](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))열고 구성하려는 그룹 정책 개체를 마우스 오른쪽 단추로 클릭하고 **편집을 클릭합니다.**

2. 그룹 **정책 관리 편집기에서** **컴퓨터 구성으로** 이동합니다.

3. **관리 템플릿을 클릭합니다.**

4. 트리를 확장하여 **> Microsoft Defender 바이러스 백신 > 구성 요소를 Windows 보고할 > Microsoft Defender 바이러스 백신 >** 있습니다.

5. 향상된 알림을 두 번 **클릭하고** 활성화할 수 있는 옵션을 **설정합니다.** **확인** 을 클릭합니다. 이렇게 하면 추가 알림이 표시되지 않습니다.

## <a name="configure-standard-notifications-on-endpoints"></a>끝점에 표준 알림 구성

그룹 정책을 사용하여 다음을 수행할 수 있습니다.

- 사용자가 작업을 수행해야 할 때 끝점에 사용자 지정 된 추가 텍스트 표시
- 끝점에 모든 알림 숨기기
- 끝점에 재부팅 알림 숨기기

알림을 숨기는 것은 전체 Microsoft Defender 바이러스 백신 인터페이스를 숨길 수 없는 경우에 유용할 수 있습니다. 자세한 내용은 [사용자가 Microsoft Defender 바이러스 백신 사용자 인터페이스를 보거나 상호 작용하지 못하도록 하십시오.](prevent-end-user-interaction-microsoft-defender-antivirus.md) 

> [!NOTE]
> 숨기기 알림은 정책이 배포된 끝점에서만 발생합니다. 수행해야 하는 작업(예: 재부팅)과 관련된 알림은 [대시보드 및 보고서에 Microsoft Endpoint Manager Endpoint Protection 모니터링됩니다.](/configmgr/protect/deploy-use/monitor-endpoint-protection) 

사용자가 컴퓨터에 표시되는 알림에 사용자 지정 연락처 정보를 추가하는 지침은 [조직에 대한 Windows 보안 앱 사용자 지정을](/windows/security/threat-protection/windows-defender-security-center/windows-defender-security-center) 참조하십시오.

**그룹 정책을 사용하여 알림을 숨깁니다.**

1. 그룹 정책 관리 컴퓨터에서 [그룹 정책 관리 콘솔을](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))열고 구성할 그룹 정책 개체를 마우스 오른쪽 단추로 클릭하고 **편집을 클릭합니다.**

2. 그룹 **정책 관리 편집기에서** **컴퓨터 구성으로** 이동하여 **관리 템플릿을 클릭합니다.**

3. **클라이언트 인터페이스에 > Microsoft Defender 바이러스 백신 > 구성 요소Windows** 로트리를 확장합니다. 

4. 두 번 **클릭하면 모든 알림 억제** 및 활성화 옵션을 **설정합니다.** **확인** 을 클릭합니다. 이렇게 하면 추가 알림이 표시되지 않습니다.

**그룹 정책을 사용하여 재부팅 알림을 숨깁니다.**

1. 그룹 정책 관리 컴퓨터에서 [그룹 정책 관리 콘솔을](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))열고 구성하려는 그룹 정책 개체를 마우스 오른쪽 단추로 클릭하고 **편집을 클릭합니다.**

2. 그룹 **정책 관리 편집기에서** **컴퓨터 구성으로** 이동합니다.

3. **관리 템플릿을 클릭합니다.**

4. **클라이언트 인터페이스에 > Microsoft Defender 바이러스 백신 > 구성 요소Windows** 로트리를 확장합니다.

5. 두 번 **클릭으로 알림을 재부팅하지 않으며** **활성화옵션을 설정합니다.** **확인** 을 클릭합니다. 이렇게 하면 추가 알림이 표시되지 않습니다.

## <a name="related-topics"></a>관련 항목

- [Windows 10의 Microsoft Defender 바이러스 백신](microsoft-defender-antivirus-in-windows-10.md)
- [Microsoft Defender 바이러스 백신 최종 사용자 상호 작용 구성](configure-end-user-interaction-microsoft-defender-antivirus.md)
