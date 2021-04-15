---
title: Microsoft Defender 바이러스 백신 알림 구성
description: 끝점에서 표준 및 추가 Microsoft Defender 바이러스 백신 알림을 구성하고 사용자 지정하는 방법을 학습합니다.
keywords: 알림, defender, 바이러스 백신, 끝점, 관리, 관리자
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 09/03/2018
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: a91da48f27450d6f4a6fd2b9607aa979458ccf71
ms.sourcegitcommit: 7a339c9f7039825d131b39481ddf54c57b021b11
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2021
ms.locfileid: "51765098"
---
# <a name="configure-the-notifications-that-appear-on-endpoints"></a>끝점에 나타나는 알림 구성

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**적용 대상:**

- [엔드포인트용 Microsoft Defender](/microsoft-365/security/defender-endpoint/) 

Windows 10에서 맬웨어 검색 및 수정에 대한 응용 프로그램 알림은 더 강력하고 일관되고, 일관성이 있습니다.

수동으로 트리거되고 예약된 검사가 완료되고 위협이 감지되면 알림이 끝점에 표시됩니다. 이러한 알림은 알림 센터에도 **표시될** 수 있으며, 검사 및 위협 검색 요약은 정기적인 간격으로 표시됩니다.

다시 시작 알림이나 위협이 감지되고 수정된 경우와 같이 끝점에 표준 알림이 나타나는 방법을 구성할 수도 있습니다.

## <a name="configure-the-additional-notifications-that-appear-on-endpoints"></a>끝점에 나타나는 추가 알림 구성

Windows 보안 앱 및 그룹 정책을 사용하여 [최근](microsoft-defender-security-center-antivirus.md) 위협 감지 요약과 같은 추가 알림 표시를 구성할 수 있습니다.

> [!NOTE]
> Windows 10 버전 1607에서는 이  기능을 고급 알림이라고 하여 **Windows** 설정 업데이트 및 보안 &  >  **에서 구성할**  >  **수 Windows Defender.** 모든 버전의 Windows 10의 그룹 정책 설정에서 이를 고급 **알림이라고 합니다.**

> [!IMPORTANT]
> 추가 알림을 사용하지 않도록 설정하면 위협 감지 및 수정 경고와 같은 중요한 알림이 비활성화되지 않습니다.

**Windows 보안 앱을 사용하여 추가 알림을 사용하지 않도록 설정할 수 있습니다.**

1. 작업 표시줄에서 방패 아이콘을 클릭하거나 **Defender의** 시작 메뉴를 검색하여 Windows 보안 앱을 열 수 있습니다.

2. 바이러스 & **위협** 방지 타일(또는 왼쪽 메뉴 표시줄의 방패 **아이콘)을** 클릭한 다음 바이러스 & 보호 설정 레이블을 클릭합니다.

    ![Windows 보안 앱의 바이러스 & 보호 설정 레이블 스크린샷](images/defender/wdav-protection-settings-wdsc.png)

3. 알림 **섹션으로 스크롤하고** 알림 설정 **변경을 클릭합니다.**

4. 스위치를 **끄기** 또는 **켜기로 밀어** 추가 알림을 사용하지 않도록 설정하거나 사용하도록 설정할 수 있습니다.

**그룹 정책을 사용하여 추가 알림을 사용하지 않도록 설정:**

1. 그룹 정책 관리 컴퓨터에서 그룹 [](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))정책 관리 콘솔을 열고 구성할 그룹 정책 개체를 마우스 오른쪽 단추로 클릭하고 편집을 **클릭합니다.**

2. 그룹 정책 **관리 편집기에서** 컴퓨터 **구성으로 이동하십시오.**

3. 관리 **템플릿 을 클릭합니다.**

4. 보고 에서 Microsoft Defender 바이러스 > Windows 구성 **> 확장합니다.**

5. 향상된 알림 **끄기** 를 두 번 클릭하고 옵션을 사용으로 **설정합니다.** **확인** 을 클릭합니다. 이렇게 하면 추가 알림이 나타나지 않습니다.

## <a name="configure-standard-notifications-on-endpoints"></a>끝점에서 표준 알림 구성

그룹 정책을 사용하여 다음을 할 수 있습니다.

- 사용자가 작업을 수행해야 하는 경우 끝점에 추가 사용자 지정 텍스트 표시
- 끝점에서 모든 알림 숨기기
- 끝점에서 다시 시작 알림 숨기기

알림 숨기기는 전체 Microsoft Defender 바이러스 백신 인터페이스를 숨길 수 없는 상황에서 유용할 수 있습니다. 자세한 [내용은 사용자가 Microsoft Defender 바이러스](prevent-end-user-interaction-microsoft-defender-antivirus.md) 백신 사용자 인터페이스를 보거나 상호 작용하지 못하도록 방지를 참조하세요. 

> [!NOTE]
> 알림 숨기기는 정책이 배포된 끝점에서만 발생합니다. 재부팅과 같이 취해야 하는 작업과 관련된 알림은 Microsoft [Endpoint Manager Endpoint Protection](/configmgr/protect/deploy-use/monitor-endpoint-protection)모니터링 대시보드 및 보고서에 계속 표시됩니다. 

사용자의 [컴퓨터 알림에](/windows/security/threat-protection/windows-defender-security-center/windows-defender-security-center) 사용자 지정 연락처 정보를 추가하는 방법에 대한 지침은 조직의 Windows 보안 앱 사용자 지정을 참조하세요.

**그룹 정책을 사용하여 알림을 숨길 수 있습니다.**

1. 그룹 정책 관리 컴퓨터에서 그룹 [](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))정책 관리 콘솔을 열고 구성할 그룹 정책 개체를 마우스 오른쪽 단추로 클릭하고 편집을 **클릭합니다.**

2. 그룹 정책 **관리 편집기에서** 컴퓨터 **구성으로 이동하여** 관리 템플릿 **을 클릭합니다.**

3. Microsoft Defender 바이러스 백신 및 클라이언트 > Windows 구성 **> 확장합니다.** 

4. 모든 알림 표시 **안 를 두 번 클릭하고** 옵션을 사용으로 **설정합니다.** **확인** 을 클릭합니다. 이렇게 하면 추가 알림이 나타나지 않습니다.

**그룹 정책을 사용하여 재부팅 알림을 숨길 수 있습니다.**

1. 그룹 정책 관리 컴퓨터에서 그룹 [](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))정책 관리 콘솔을 열고 구성할 그룹 정책 개체를 마우스 오른쪽 단추로 클릭하고 편집을 **클릭합니다.**

2. 그룹 정책 **관리 편집기에서** 컴퓨터 **구성으로 이동하십시오.**

3. 관리 **템플릿 을 클릭합니다.**

4. Microsoft Defender 바이러스 백신 및 클라이언트 > Windows 구성 **> 확장합니다.**

5. 다시 시작 알림 표시 안 를 두 번 **클릭하고** 옵션을 사용으로 **설정합니다.** **확인** 을 클릭합니다. 이렇게 하면 추가 알림이 나타나지 않습니다.

## <a name="related-topics"></a>관련 항목

- [Windows 10의 Microsoft Defender 바이러스 백신](microsoft-defender-antivirus-in-windows-10.md)
- [Microsoft Defender 바이러스 백신과 최종 사용자 상호 작용 구성](configure-end-user-interaction-microsoft-defender-antivirus.md)