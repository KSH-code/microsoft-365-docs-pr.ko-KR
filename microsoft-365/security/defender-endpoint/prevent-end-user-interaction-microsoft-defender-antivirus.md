---
title: 인터페이스 Microsoft Defender 바이러스 백신 숨기기
description: 앱의 앱에 바이러스 및 위협 방지 타일을 숨길 Windows 보안 있습니다.
keywords: UI 잠금, 헤드리스 모드, 앱 숨기기, 설정 숨기기, 인터페이스 숨기기
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 09/03/2018
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.topic: article
ms.openlocfilehash: af938fda518e5a7eea3cb9341f04c8573a647044
ms.sourcegitcommit: 4740e69326eb7f8302eec7bab5bd516d498e4492
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/16/2021
ms.locfileid: "59399427"
---
# <a name="prevent-users-from-seeing-or-interacting-with-the-microsoft-defender-antivirus-user-interface"></a>사용자가 사용자 인터페이스를 보거나 상호 작용하지 Microsoft Defender 바이러스 백신 방지

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**적용 대상:**

- [엔드포인트용 Microsoft Defender](/microsoft-365/security/defender-endpoint/)

그룹 정책을 사용하여 끝점의 사용자가 그룹 인터페이스를 볼 수 Microsoft Defender 바이러스 백신 있습니다. 또한 검사가 더이상 실행되지 않도록 차단할 수 있습니다.

## <a name="hide-the-microsoft-defender-antivirus-interface"></a>인터페이스 Microsoft Defender 바이러스 백신 숨기기

Windows 10 버전 1703에서는 인터페이스를 숨기면 Microsoft Defender 바이러스 백신 알림이 숨겨지며 바이러스 & 위협 방지 타일이 Windows 보안 앱에 나타나지 않습니다.

설정이 **사용으로** 설정된 경우 :

:::image type="content" source="../../media/wdav-headless-mode-off-1703.png" alt-text="방패 Windows 보안 및 바이러스 및 위협 방지 섹션이 없는 경우의 스크린샷.":::

설정이 사용 안 하도록 **설정되거나** 구성되지 않은 경우:

:::image type="content" source="../../media/wdav-headless-mode-1703.png" alt-text="방패 Windows 보안 및 위협 방지 섹션이 있는 스크린샷.":::

> [!NOTE]
> 또한 인터페이스를 숨기면 Microsoft Defender 바이러스 백신 끝점에 알림이 나타나지 않습니다. 끝점용 Microsoft Defender 알림이 계속 표시됩니다. 끝점에 나타나는 알림을 개별적으로 [구성할 수도 있습니다.](configure-notifications-microsoft-defender-antivirus.md)

이전 버전의 Windows 10 클라이언트 인터페이스가 Windows Defender 숨겨지게 됩니다. 사용자가 앱을 열려고 하면 "시스템 관리자가 이 앱에 대한 액세스를 제한했습니다."라는 경고가 표시됩니다.

:::image type="content" source="../../media/wdav-headless-mode-1607.png" alt-text="1703 이전 버전에서 헤드리스 모드를 Windows 10 경고 메시지":::

## <a name="use-group-policy-to-hide-the-microsoft-defender-av-interface-from-users"></a>그룹 정책을 사용하여 사용자로부터 Microsoft Defender AV 인터페이스 숨기기

1. 그룹 정책 관리 컴퓨터의 [](/previous-versions/windows/desktop/gpmc/group-policy-management-console-portal)그룹 정책 관리 콘솔을 열고 구성할 그룹 정책 개체를 마우스 오른쪽 단추로 클릭하고 편집을 **클릭합니다.**

2. 그룹 정책 **관리 편집기를 사용하여 컴퓨터** **구성으로 이동하십시오.**

3. 관리 **템플릿 을 클릭합니다.**

4. 클라이언트 인터페이스에서 **구성 Windows 트리를 > Microsoft Defender 바이러스 백신 > 확장합니다.**

5. 헤드리스 UI 모드 사용 설정을 **두 번 클릭하고** 옵션을 사용으로 **설정합니다.** **확인** 을 클릭합니다.

사용자가 [PC에서](configure-local-policy-overrides-microsoft-defender-antivirus.md) 보호를 수정하지 못하도록 하는 데 대한 자세한 옵션은 사용자가 로컬에서 정책 설정을 수정하지 못하도록 방지를 참조하세요.

## <a name="prevent-users-from-pausing-a-scan"></a>사용자가 검색을 시작하지 못하게 방지

사용자가 스캔을 중단하지 못하게 할 수 있습니다. 이렇게 하면 예약된 검사나 필요한 경우 검사가 중단되지 않도록 할 수 있습니다.

> [!NOTE]
> 이 설정은 이 설정에서 지원되지 Windows 10.

### <a name="use-group-policy-to-prevent-users-from-pausing-a-scan"></a>그룹 정책을 사용하여 사용자가 스캔을 시작하지 못하게 차단

1. 그룹 정책 관리 컴퓨터의 [](/previous-versions/windows/desktop/gpmc/group-policy-management-console-portal)그룹 정책 관리 콘솔을 열고 구성할 그룹 정책 개체를 마우스 오른쪽 단추로 클릭하고 편집을 **클릭합니다.**

2. 그룹 정책 **관리 편집기를 사용하여 컴퓨터** **구성으로 이동하십시오.**

3. 관리 **템플릿 을 클릭합니다.**

4. 검색에서 구성 **Windows** \> **트리를 Microsoft Defender 바이러스 백신** \> **확장합니다.**

5. 사용자가 스캔을 일시 **중지할** 수 있도록 허용 설정을 두 번 클릭하고 옵션을 사용 안 **하도록 설정하십시오.** **확인** 을 클릭합니다.

## <a name="related-articles"></a>관련 문서

- [엔드포인트에 표시되는 알림 구성](configure-notifications-microsoft-defender-antivirus.md)
- [사용자와의 최종 사용자 상호 작용 Microsoft Defender 바이러스 백신](configure-end-user-interaction-microsoft-defender-antivirus.md)
- [Windows 10의 Microsoft Defender 바이러스 백신](microsoft-defender-antivirus-in-windows-10.md)
