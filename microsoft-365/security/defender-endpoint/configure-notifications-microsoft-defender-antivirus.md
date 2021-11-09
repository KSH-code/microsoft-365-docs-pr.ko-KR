---
title: 알림 Microsoft Defender 바이러스 백신 구성
description: 끝점에서 표준 및 기타 Microsoft Defender 바이러스 백신 알림을 구성하고 사용자 지정하는 방법을 학습합니다.
keywords: 알림, defender, 바이러스 백신, 끝점, 관리, 관리자
ms.prod: m365-security
ms.technology: mde
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
author: denisebmsft
ms.topic: article
ms.author: deniseb
ms.custom: nextgen
ms.date: 10/18/2021
ms.reviewer: ''
manager: dansimp
ms.collection: M365-security-compliance
ms.openlocfilehash: b2b23a52312b3f384122f34b054b65bd6aa486a2
ms.sourcegitcommit: e09ced3e3628bf2ccb84d205d9699483cbb4b3b0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/09/2021
ms.locfileid: "60881916"
---
# <a name="configure-microsoft-defender-antivirus-notifications-that-appear-on-endpoints"></a>끝점에 Microsoft Defender 바이러스 백신 알림 구성

**적용 대상:**

- [엔드포인트용 Microsoft Defender](/microsoft-365/security/defender-endpoint/)

이러한 Windows 10 Windows 11 맬웨어 검색 및 수정에 대한 응용 프로그램 알림은 더욱 강력하고 일관되고, 일관성이 있습니다. Microsoft Defender 바이러스 백신 검사가 완료되고 위협이 감지되면 끝점에 알림이 표시됩니다. 알림은 예약된 검사와 수동 트리거된 검사 모두를 따르게 됩니다. 이러한 알림은 알림 센터에도 **표시될** 수 있으며, 검사 및 위협 검색 요약은 정기적인 간격으로 표시됩니다.

조직의 보안 팀에 속하는 경우 시스템 재부팅을 요청하는 알림이나 위협이 감지되고 수정된 것을 나타내는 알림과 같이 끝점에 알림이 나타나는 방법을 구성할 수 있습니다.

## <a name="configure-antivirus-notifications-using-group-policy-or-the-windows-security-app"></a>그룹 정책 또는 앱 앱을 사용하여 바이러스 Windows 보안 구성

최신 위협 감지 요약과 같은 추가 알림 표시를 Windows 보안 [그룹](microsoft-defender-security-center-antivirus.md) 정책을 사용하여 구성할 수 있습니다.

> [!NOTE]
> Windows 10 버전 1607에서는 이 기능을 고급  알림이라고 하여 Windows 설정  업데이트 & \> **보안** \> Windows Defender. 모든 버전의 Windows 10 및 Windows 11 그룹 정책 설정에서 알림 기능을 고급 알림이라고 **합니다.**

### <a name="use-group-policy-to-disable-additional-notifications"></a>그룹 정책을 사용하여 추가 알림을 사용하지 않도록 설정

1. 그룹 정책 관리 컴퓨터에서 [그룹 정책 관리 콘솔](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))을 엽니다.

2. 구성할 그룹 정책 개체를 마우스 오른쪽 단추로 클릭한 다음 편집 **을 선택합니다.**

3. 그룹 정책 **관리 편집기에서** 컴퓨터 **구성으로 이동하십시오.**

4. 관리 **템플릿 을 선택합니다.**

5. **보고**에서 Windows 구성** \> **Microsoft Defender 바이러스 백신** > 확장합니다.

6. 향상된 알림 **끄기** 를 두 번 클릭하고 옵션을 사용으로 **설정합니다.** 그런 다음 **확인** 을 선택합니다. 이렇게 하면 추가 알림이 나타나지 않습니다.

> [!IMPORTANT]
> 추가 알림을 사용하지 않도록 설정하면 위협 감지 및 수정 경고와 같은 중요한 알림이 비활성화되지 않습니다.

### <a name="use-the-windows-security-app-to-disable-additional-notifications"></a>앱 Windows 보안 사용하여 추가 알림을 사용하지 않도록 설정

1. 작업 Windows 보안 방패 아이콘을 클릭하거나 보안에 대한 시작 메뉴를 검색하여 앱 앱을 열 **수 있습니다.**

2. 바이러스 **& 보호** 타일(또는 왼쪽 메뉴 표시줄의 방패 아이콘)을 선택한 다음 바이러스 & 보호 설정을 **선택합니다.**

3. 알림 **섹션으로 스크롤하고** 알림 설정 **변경을 선택합니다.**

4. 스위치를 **끄기** 또는 **켜기로 밀어** 추가 알림을 사용하지 않도록 설정하거나 사용하도록 설정할 수 있습니다.

> [!IMPORTANT]
> 추가 알림을 사용하지 않도록 설정하면 위협 감지 및 수정 경고와 같은 중요한 알림이 비활성화되지 않습니다.

## <a name="configure-standard-notifications-on-endpoints-using-group-policy"></a>그룹 정책을 사용하여 끝점에서 표준 알림 구성

그룹 정책을 사용하여 다음을 할 수 있습니다.

- 사용자가 작업을 수행해야 하는 경우 끝점에 추가 사용자 지정 텍스트 표시
- 끝점에서 모든 알림 숨기기
- 끝점에서 다시 시작 알림 숨기기

알림 숨기기는 전체 알림 인터페이스를 숨길 수 없는 Microsoft Defender 바이러스 백신 있습니다. 자세한 내용은 사용자가 사용자 인터페이스를 [보거나](prevent-end-user-interaction-microsoft-defender-antivirus.md) 상호 작용하지 못하도록 Microsoft Defender 바이러스 백신 참조하세요. 알림 숨기기는 정책이 배포된 끝점에서만 발생합니다. 재부팅과 같이 취해야 하는 작업과 관련된 알림은 모니터링 대시보드 및 보고서의 Microsoft Endpoint Manager Endpoint Protection [표시됩니다.](/configmgr/protect/deploy-use/monitor-endpoint-protection) 

끝점 알림에 사용자 지정 연락처 정보를 추가하기 위해 조직에 대한 Windows 보안 [사용자 지정을 참조하세요.](/windows/security/threat-protection/windows-defender-security-center/windows-defender-security-center)

### <a name="use-group-policy-to-hide-notifications"></a>그룹 정책을 사용하여 알림 숨기기

1. 그룹 정책 관리 컴퓨터에서 [그룹 정책 관리 콘솔](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))을 엽니다.

2. 구성할 그룹 정책 개체를 마우스 오른쪽 단추로 클릭한 다음 편집 **을 선택합니다.**

3. 그룹 정책 **관리 편집기에서** 컴퓨터 **구성으로 이동한** 다음 관리 템플릿 **을 선택합니다.**

4. 클라이언트 인터페이스에서 **구성 Windows** \> **트리를 Microsoft Defender 바이러스 백신** \> **확장합니다.** 

5. 모든 알림 표시 **안 를 두 번 클릭하고** 옵션을 사용으로 **설정합니다.** 

6. **확인** 을 선택합니다. 이렇게 하면 추가 알림이 나타나지 않습니다.

### <a name="use-group-policy-to-hide-reboot-notifications"></a>그룹 정책을 사용하여 재부팅 알림 숨기기

1. 그룹 정책 관리 컴퓨터에서 [그룹 정책 관리 콘솔](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))을 엽니다.

2. 구성할 그룹 정책 개체를 마우스 오른쪽 단추로 클릭한 다음 편집 을 **선택합니다.**

2. 그룹 정책 **관리 편집기에서** 컴퓨터 **구성으로 이동하십시오.**

3. 관리 **템플릿 을 클릭합니다.**

4. 클라이언트 인터페이스에서 **구성 Windows** \> **트리를 Microsoft Defender 바이러스 백신** \> **확장합니다.**

5. 다시 시작 알림 표시 안 를 두 번 **클릭하고** 옵션을 사용으로 **설정합니다.** 

5. **확인** 을 선택합니다. 이렇게 하면 추가 알림이 나타나지 않습니다.

