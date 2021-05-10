---
title: 차단 모드에서 끝점 검색 및 응답
description: 차단 모드에서 끝점 검색 및 응답에 대해 자세히 알아보기
keywords: 끝점용 Microsoft Defender, mde, EDR 모드, 수동 모드 차단
search.product: eADQiWindows 10XVcnh
ms.pagetype: security
author: denisebmsft
ms.author: deniseb
manager: dansimp
ms.reviewer: shwetaj
audience: ITPro
ms.topic: article
ms.prod: m365-security
localization_priority: Normal
ms.custom:
- next-gen
- edr
ms.date: 05/08/2021
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.technology: mde
ms.openlocfilehash: 86bb27005365b625ee07feaa067c0ac488c3bb4b
ms.sourcegitcommit: 58d74ff60303a879e35d112f10f79724ba41188f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/10/2021
ms.locfileid: "52302043"
---
# <a name="endpoint-detection-and-response-edr-in-block-mode"></a>차단 모드에서 끝점 EDR(응답)

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**적용 대상:**
- [엔드포인트용 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>Endpoint용 Defender를 경험하고 싶나요? [무료 평가판에 등록합니다.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

## <a name="what-is-edr-in-block-mode"></a>차단 EDR 어떤 것이 있나요?

[차단 모드의](overview-endpoint-detection-response.md) 끝점 감지 및 응답(EDR)은 수동 모드에서 실행되는 경우에도 Microsoft Defender 바이러스 백신 아티팩트로부터 보호합니다. 이 기능을 EDR 차단 모드에서는 디바이스에서 감지되는 악의적인 아티팩트 또는 동작을 차단합니다. EDR 차단 모드에서는 장면 뒤에서 작동하여 위반 후 감지된 악성 아티팩트를 수정합니다. 

EDR 모드는 위협 [요소와 & 취약성 관리.](next-gen-threat-and-vuln-mgt.md) 조직의 보안 팀은 아직 사용하도록 [](tvm-security-recommendation.md) 설정되지 않은 경우 EDR 모드로 전환하는 보안 권장을 받을 수 있습니다. 

:::image type="content" source="images/edrblockmode-TVMrecommendation.png" alt-text="차단 모드에서 EDR 설정하는 권장":::

> [!NOTE]
> 최상의 보호를 위해 끝점 **[기준에 대한 Microsoft Defender를 배포해야 합니다.](configure-machines-security-baseline.md)**

## <a name="what-happens-when-something-is-detected"></a>감지된 경우 어떻게 하나요?

차단 EDR 설정되어 있으며 악의적인 아티팩트가 감지되면 끝점용 Microsoft Defender는 이 아티팩트를 차단하고 수정합니다. 보안 운영 팀에서 검색 상태가 완료된  작업으로 [](respond-machine-alerts.md#check-activity-details-in-action-center)나열된 관리 센터에서 차단 또는 금지로 표시됩니다. 

다음 이미지는 차단 모드에서 검색되고 차단된 원치 않는 소프트웨어의 EDR 보여줍니다.

:::image type="content" source="images/edr-in-block-mode-detection.png" alt-text="EDR 모드로 검색된 것":::


## <a name="enable-edr-in-block-mode"></a>차단 EDR 사용

> [!IMPORTANT]
> 차단 [모드로 전환하기](#requirements-for-edr-in-block-mode) 전에 EDR 충족해야 합니다.

1. Microsoft Defender 보안 센터 [https://securitycenter.windows.com](https://securitycenter.windows.com) ()로 이동하여 로그인합니다. 

2. 고급 **설정**  >  **를 선택 합니다.**

3. 차단 모드에서 **EDR 을 켜야 합니다.**

> [!NOTE]
> EDR 모드로 설정하면 차단 모드에서만 Microsoft Defender 보안 센터. 레지스트리 키, Intune 또는 그룹 정책을 사용하여 차단 모드에서 레지스트리 EDR 수 없습니다.

## <a name="requirements-for-edr-in-block-mode"></a>차단 모드의 EDR 요구 사항

|요구 사항  |세부 정보  |
|---------|---------|
|권한 |에서 할당된 전역 관리자 [또는 보안 Azure Active Directory.](/azure/active-directory/fundamentals/active-directory-users-assign-role-azure-portal) 기본 [사용 권한을 참조합니다.](basic-permissions.md) |
|운영 체제     |다음 버전 중 하나 <br/>- Windows 10(모든 릴리스) <br/>- Windows Server, 버전 1803 이상 <br/>- Windows Server 2019 <br/>- Windows Server 2016(Microsoft Defender 바이러스 백신 모드에 있는 경우만)     |
|Windows E5 등록     |Windows E5는 다음 구독에 포함됩니다. <br/>- Microsoft 365 E5 <br/>- Microsoft 365 E3 Id 및 위협 방지 & 함께 사용할 수 있습니다. <br/><br/>각 [계획의](/microsoft-365/enterprise/microsoft-365-overview#components) 구성 요소 및 [기능을 참조합니다.](https://www.microsoft.com/microsoft-365/compare-all-microsoft-365-plans)       |
|Windows Defender 바이러스 백신  |Microsoft Defender 바이러스 백신 모드 또는 수동 모드에서 설치 및 실행해야 합니다. Microsoft가 아닌 바이러스 백신 Microsoft Defender 바이러스 백신 함께 사용할 수 있습니다. [활성 Microsoft Defender 바이러스 백신 수동 모드에 있는지 확인](#how-do-i-confirm-microsoft-defender-antivirus-is-in-active-or-passive-mode) |
|클라우드 제공 보호 |클라우드 제공 Microsoft Defender 바이러스 백신 사용하도록 구성해야 [합니다.](enable-cloud-protection-microsoft-defender-antivirus.md) |
|Microsoft Defender 바이러스 백신 맬웨어 방지 클라이언트 |클라이언트를 최신으로 유지해야 합니다. PowerShell을 사용하여 [Get-MpComputerStatus](/powershell/module/defender/get-mpcomputerstatus) cmdlet을 관리자 권한으로 실행합니다. **AMProductVersion** 줄에 **4.18.2001.10 이상이** 표시될 것입니다. |
|Microsoft Defender 바이러스 백신 엔진 |엔진을 최신으로 유지해야 합니다. PowerShell을 사용하여 [Get-MpComputerStatus](/powershell/module/defender/get-mpcomputerstatus) cmdlet을 관리자 권한으로 실행합니다. **AMEngineVersion** 줄에 **1.1.16700.2 이상이** 표시될 것입니다. |

> [!IMPORTANT]
> 최상의 보호 값을 얻기 위해 정기적인 업데이트 및 필수 기능을 받도록 바이러스 백신 솔루션이 구성되어 있는지, 그리고 제외가 구성되어 [있는지 확인합니다.](configure-exclusions-microsoft-defender-antivirus.md) EDR 모드는 차단 모드에 대해 정의된 제외를 Microsoft Defender 바이러스 백신.

## <a name="frequently-asked-questions"></a>질문과 대답 

### <a name="do-i-need-to-turn-edr-in-block-mode-on-even-when-i-have-microsoft-defender-antivirus-running-on-devices"></a>장치에서 실행 중인 EDR 차단 모드에서 Microsoft Defender 바이러스 백신 설정해야 하나요?

수동 모드 또는 EDR 모드에 Microsoft Defender 바이러스 백신 차단 모드로 유지하는 것이 좋습니다. EDR 모드에서는 끝점용 Microsoft Defender를 사용하여 또 다른 방어 계층을 제공합니다. 이를 통해 끝점에 대한 Defender는 위반 후 행동 및 검색을 기반으로 EDR 수 있습니다. 

### <a name="will-edr-in-block-mode-have-any-impact-on-a-users-antivirus-protection"></a>차단 EDR 사용자의 바이러스 백신 보호에 영향을 미치나요? 

EDR 모드에서는 사용자의 장치에서 실행되는 타사 바이러스 백신 보호에 영향을 주지 않습니다. EDR 바이러스 백신 솔루션이 누락되거나 위반 후 검색이 있는 경우 차단 모드로 전환됩니다. EDR 모드는 수동 Microsoft Defender 바이러스 백신 마찬가지로 작동하며, 검색된 악성 아티팩트 또는 동작도 차단하고 수정합니다.

### <a name="why-do-i-need-to-keep-microsoft-defender-antivirus-up-to-date"></a>최신으로 유지해야 하는 Microsoft Defender 바이러스 백신 이유는 무엇입니까? 

악의적인 Microsoft Defender 바이러스 백신 감지하고 수정하기 때문에 이를 최신으로 유지하는 것이 중요합니다. 블록 EDR 효과를 위해 최신 장치 학습 모델, 동작 감지 및추론을 사용합니다. 기능의 [끝점용 Defender](microsoft-defender-endpoint.md) 스택은 통합된 방식으로 작동합니다. 최상의 보호 값을 얻기 위해 최신 Microsoft Defender 바이러스 백신 해야 합니다. 자세한 [내용은 Microsoft Defender 바이러스 백신 관리 및 기준 적용을 참조하세요.](manage-updates-baselines-microsoft-defender-antivirus.md) 

### <a name="why-do-we-need-cloud-protection-on"></a>클라우드 보호가 필요한 이유는 무엇입니까? 

디바이스에서 기능을 켜는 데 클라우드 보호가 필요합니다. 클라우드 보호를 [통해 Endpoint용 Defender는](microsoft-defender-endpoint.md) 동작 및 장치 학습 모델과 함께 보안 인텔리전스의 다양한 깊이와 깊이에 따라 최신 및 최고의 보호를 제공할 수 있습니다.

### <a name="how-do-i-set-microsoft-defender-antivirus-to-passive-mode"></a>수동 모드로 Microsoft Defender 바이러스 백신 어떻게 설정하나요?

운영 체제에 따라 Microsoft가 아닌 바이러스 백신/맬웨어 방지 솔루션을 실행하는 장치가 Endpoint용 Defender에 온보딩된 경우 Microsoft Defender 바이러스 백신 수동 모드로 전환될 수 있습니다. 자세한 내용은 How [Microsoft Defender 바이러스 백신 affects Defender for Endpoint functionality을 참조하세요.](microsoft-defender-antivirus-compatibility.md#how-microsoft-defender-antivirus-affects-defender-for-endpoint-functionality) 

### <a name="how-do-i-confirm-microsoft-defender-antivirus-is-in-active-or-passive-mode"></a>활성 모드 또는 Microsoft Defender 바이러스 백신 모드에 있는지 확인하는 방법

활성 모드 Microsoft Defender 바이러스 백신 수동 모드로 실행 중인지 확인하려면 명령 프롬프트 또는 PowerShell을 실행 중인 장치에서 명령 프롬프트를 Windows.


|메서드  |절차  |
|---------|---------|
| PowerShell     | 1. 시작 메뉴를 선택하고 를 입력한 다음 결과에서 Windows PowerShell `PowerShell` 를 열 수 있습니다. <p>2. 를 `Get-MpComputerStatus` 입력합니다. <p>3. 결과 목록의 **AMRunningMode** 행에서 다음 값 중 하나를 검색합니다. <br/>- `Normal` <br/>- `Passive Mode` <br/>- `SxS Passive Mode` <p>자세한 내용은 [Get-MpComputerStatus 를 참조합니다.](/powershell/module/defender/get-mpcomputerstatus)        |
|명령 프롬프트     | 1. 시작 메뉴를 선택하고 를 입력한 다음 결과에서 명령 `Command Prompt` Windows 열 수 있습니다. <p>2. 를 `sc query windefend` 입력합니다. <p>3. 결과 목록의 **STATE** 행에서 서비스가 실행 중인지 선택합니다.         |

### <a name="how-much-time-does-it-take-for-edr-in-block-mode-to-be-disabled"></a>차단 모드에서 EDR 데 얼마나 걸릴까요?

차단 모드에서 EDR 사용하지 않도록 선택한 경우 시스템에서 이 기능을 사용하지 않도록 설정하는 데 최대 30분이 걸릴 수 있습니다.

### <a name="is-edr-in-block-mode-supported-on-windows-server-2016"></a>지원 EDR 차단 모드에서 지원 Windows Server 2016하나요?

활성 Microsoft Defender 바이러스 백신 수동 모드로 실행 중인 경우 EDR 모드로 설정하면 다음 버전의 Windows.

- Windows 10(모든 릴리스)
- Windows 서버, 버전 1803 이상 
- Windows Server 2019 

Windows Server 2016 모드로 Microsoft Defender 바이러스 백신 끝점이 Endpoint용 Defender에 온보딩된 경우 기술적으로 EDR 모드로 실행됩니다. 그러나 EDR 모드는 끝점에서 기본 바이러스 백신 솔루션이 아닌 Microsoft Defender 바이러스 백신 추가 보호를 위해 고안된 것입니다. 이러한 경우 수동 Microsoft Defender 바이러스 백신 실행됩니다. 현재 수동 Microsoft Defender 바이러스 백신 모드로 실행되는 것은 지원되지 Windows Server 2016. 자세한 내용은 Microsoft Defender 바이러스 백신 및 [비 Microsoft 바이러스 백신/맬웨어 방지 솔루션 을 참조하세요.](microsoft-defender-antivirus-compatibility.md#microsoft-defender-antivirus-and-non-microsoft-antivirusantimalware-solutions)

## <a name="see-also"></a>참고 항목

- [기술 Community 블로그: EDR 모드로 전환 소개: 추적에서 공격 중지](https://techcommunity.microsoft.com/t5/microsoft-defender-atp/introducing-edr-in-block-mode-stopping-attacks-in-their-tracks/ba-p/1596617)
- [동작 차단 및 제약](behavioral-blocking-containment.md)

