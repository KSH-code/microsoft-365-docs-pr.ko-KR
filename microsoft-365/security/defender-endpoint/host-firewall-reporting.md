---
title: 엔드포인트용 Microsoft Defender 호스트 방화벽 보고
description: 보안 센터에서 방화벽 보고를 Microsoft 365 볼 수 있습니다.
keywords: windows defender, 방화벽
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
audience: ITPro
ms.topic: article
author: dansimp
ms.author: dansimp
manager: dansimp
ms.technology: mde
ms.collection: m365-security-compliance
ms.openlocfilehash: 6dc04eb51346b078218117d35f1b7a5b2d1c9268
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2021
ms.locfileid: "60174738"
---
# <a name="host-firewall-reporting-in-microsoft-defender-for-endpoint"></a>엔드포인트용 Microsoft Defender 호스트 방화벽 보고

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**적용 대상:**
- [엔드포인트용 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

관리자인 경우 이제 보안 센터 에 방화벽 [보고를 Microsoft 365 있습니다.](https://security.microsoft.com) 이 기능을 사용하면 중앙 위치에서 Windows 10, Windows Server 2019 및 Windows Server 2022 방화벽 보고를 볼 수 있습니다.

## <a name="what-do-you-need-to-know-before-you-begin"></a>시작하기 전에 알아야 할 내용

- Server 2019 또는 Windows 10 Windows 또는 Windows 실행 중이야 합니다.
- 디바이스를 Microsoft Defender for Endpoint 서비스에 온보딩하는 경우 여기를 [참조하세요.](onboard-configure.md)
- 보안 Microsoft 365 센터에서 데이터 수신을 시작하려면 고급  보안이 있는 방화벽에 Windows Defender 감사 이벤트를 사용하도록 설정해야 합니다.
  - [필터링 플랫폼 패킷 삭제 감사](/windows/security/threat-protection/auditing/audit-filtering-platform-packet-drop)
  - [필터링 플랫폼 연결 감사](/windows/security/threat-protection/auditing/audit-filtering-platform-connection)
- 그룹 정책 개체 편집기, 로컬 보안 정책 또는 로컬 보안 정책을 사용하여 이러한 이벤트를 auditpol.exe 사용합니다. 자세한 내용은 여기를 [참조하세요.](/windows/win32/fwp/auditing-and-logging)
  - PowerShell 명령은 다음 두 가지입니다.
    - **auditpol /set /subcategory:"Filtering Platform Packet Drop" /failure:enable**
    - **auditpol /set /subcategory:"Filtering Platform Connection" /failure:enable**

## <a name="the-process"></a>프로세스

> [!NOTE]
> 위 섹션의 지침을 따르고 초기 미리 보기 참가를 위해 장치를 올바르게 구성해야 합니다.

- 이벤트를 사용하도록 설정하면 Microsoft 365 센터에서 데이터 모니터링을 시작하게 됩니다.
  - 원격 IP, 원격 포트, 로컬 포트, 로컬 IP, 컴퓨터 이름, 인바운드 및 아웃바운드 연결에서 프로세스
- 이제 관리자는 여기에서 방화벽 Windows 볼 수 [있습니다.](https://security.microsoft.com/firewall)
  - 사용자 지정 보고 스크립트를 다운로드하여 [](https://github.com/microsoft/MDATP-PowerBI-Templates/tree/master/Firewall) 추가 보고를 용이하게 할 수 Windows Defender 방화벽 활동을 모니터링할 수 Power BI.
  - 데이터가 반영되기까지 최대 12시간이 걸릴 수 있습니다.

## <a name="supported-scenarios"></a>지원되는 시나리오

링0 미리 보기 중에 지원되는 시나리오는 다음과 같습니다.

### <a name="firewall-reporting-in-security-center"></a>보안 센터의 방화벽 보고

다음은 방화벽 보고서 페이지의 몇 가지 예입니다. 여기에서 인바운드, 아웃바운드 및 응용 프로그램 활동에 대한 요약을 찾을 수 있습니다. 로 이동하여 이 페이지에 직접 액세스할 수 https://security.microsoft.com/firewall 있습니다.

> [!div class="mx-imgBorder"]
> ![방화벽 보고 페이지를 호스트합니다.](\images\host-firewall-reporting-page.png)

방화벽 차단 인바운드 연결  카드 아래쪽에 있는 보고서 보안 보고서 장치(섹션)로 이 보고서에 액세스할 \>  \>  **수도** 있습니다.

### <a name="from-computers-with-a-blocked-connection-to-device"></a>"차단된 연결이 있는 컴퓨터"에서 장치로

카드는 대화형 개체를 지원합니다. 새 탭에서 시작되는 장치 이름을 클릭하여 디바이스의 활동을 드릴다운하고 장치 타임라인 탭으로 바로 https://securitycenter.microsoft.com 이동하면 됩니다. 

> [!div class="mx-imgBorder"]
> ![연결이 차단된 컴퓨터.](\images\firewall-reporting-blocked-connection.png)

이제 타임라인  탭을 선택하여 해당 디바이스와 연결된 이벤트 목록을 제공합니다.

보기 창의  오른쪽 위 모서리에 있는 필터 단추를 클릭한 후 원하는 이벤트 유형을 선택합니다. 이 경우 방화벽 이벤트를 **선택하면** 창이 방화벽 이벤트로 필터링됩니다.

> [!div class="mx-imgBorder"]
> ![필터 단추.](\images\firewall-reporting-filters-button.png)

### <a name="drill-into-advanced-hunting-preview-refresh"></a>고급 헌팅 드릴(미리 보기 새로 고침)

방화벽 보고서는 고급 헌팅  열기 단추를 클릭하여 카드에서 고급 헌팅으로 직접 드릴링을 **지원합니다.** 쿼리가 미리 채워집니다.

> [!div class="mx-imgBorder"]
> ![고급 헌팅 단추를 니다.](\images\firewall-reporting-advanced-hunting.png)

이제 쿼리를 실행할 수 있으며 지난 30일 동안의 모든 관련 방화벽 이벤트를 탐색할 수 있습니다.

추가 보고 또는 사용자 지정 변경의 경우 추가 분석을 위해 쿼리를 Power BI 수 있습니다. 사용자 지정 보고 스크립트를 다운로드하여 [](https://github.com/microsoft/MDATP-PowerBI-Templates/tree/master/Firewall) 사용자 지정 보고를 통해 방화벽 Windows Defender 모니터링할 수 Power BI.
