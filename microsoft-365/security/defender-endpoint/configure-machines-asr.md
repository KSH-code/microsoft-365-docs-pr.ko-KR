---
title: ASR 규칙 배포 및 검색 최적화
description: 일반적인 맬웨어 악용을 식별하고 방지하기 위해 ASR(공격 표면 축소) 규칙을 최적화합니다.
keywords: 온보드, Intune 관리, 끝점용 Microsoft Defender, Microsoft Defender, Windows Defender, 공격 표면 감소, ASR, 보안 기준
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 70c9937006183773f0b10e7da20e132785189cee
ms.sourcegitcommit: bf3965b46487f6f8cf900dd9a3af8b213a405989
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/02/2021
ms.locfileid: "60667365"
---
# <a name="optimize-asr-rule-deployment-and-detections"></a>ASR 규칙 배포 및 검색 최적화

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**적용 대상:**
- [엔드포인트용 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Endpoint용 Defender를 경험하고 싶나요? [무료 평가판을 신청하세요.](https://www.microsoft.com/WindowsForBusiness/windows-atp?ocid=docs-wdatp-onboardconfigure-abovefoldlink)

[ASR(공격 표면 감소) 규칙은](./attack-surface-reduction.md) 일반적인 맬웨어 악용을 식별하고 방지합니다. 잠재적으로 악성 코드가 실행될 수 있는 경우와 방법을 제어합니다. 예를 들어 JavaScript 또는 VBScript가 다운로드된 실행 파일을 시작하지 못하게 방지하고, Office 매크로에서 Win32 API 호출을 차단하고, USB 드라이브에서 실행되는 프로세스를 차단할 수 있습니다.


:::image type="content" source="../../media/attack-surface-mgmt.png" alt-text="공격 표면 관리 카드.":::
<br>
*공격 표면 관리 카드*

공격 *표면 관리 카드는* 다음에 사용할 수 있는 Microsoft 365 보안 센터의 도구 진입점입니다.

* ASR 규칙이 현재 조직에 배포되는 방법을 이해합니다.
* ASR 검색을 검토하고 가능한 잘못된 검색을 식별합니다.
* 제외의 영향을 분석하고 제외할 파일 경로 목록을 생성합니다.

공격 **표면 관리** 보고서 공격 표면 축소 규칙 제외 추가로 \>  \>  \> **이동을 선택합니다.** 이 섹션에서 보안 센터의 다른 섹션으로 Microsoft 365 있습니다.

![보안 센터의 공격 표면 축소 규칙 페이지에서 제외 Microsoft 365 추가합니다.](images/secconmgmt_asr_m365exlusions.png)<br>
보안 ***센터의** 공격 표면 축소 규칙 페이지의 제외 Microsoft 365 탭*

> [!NOTE]
> 보안 Microsoft 365 액세스하려면 Microsoft 365 E3 또는 E5 라이선스와 특정 역할이 있는 계정이 Azure Active Directory. [필요한 라이선스 및 사용 권한에 대해 읽어 읽습니다.](/office365/securitycompliance/microsoft-security-and-compliance#required-licenses-and-permissions)

Microsoft 365 센터의 ASR 규칙 배포에 대한 자세한 내용은 ASR 규칙 배포 및 검색 모니터링 및 관리를 [참조하세요.](/office365/securitycompliance/monitor-devices#monitor-and-manage-asr-rule-deployment-and-detections)

**관련 항목**

* [장치가 올바르게 구성되어 있는지 확인](configure-machines.md)
* [끝점용 Microsoft Defender에 장치 온보딩](configure-machines-onboarding.md)
* [끝점 보안 기준에 대한 Microsoft Defender 준수 모니터링](configure-machines-security-baseline.md)
