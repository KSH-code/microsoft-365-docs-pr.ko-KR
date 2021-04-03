---
title: 공격 표면 감소 규칙 사용
description: ASR(공격 표면 축소) 규칙을 사용하도록 설정하여 매크로, 스크립트 및 일반적인 삽입 기술을 사용하는 공격으로부터 장치를 보호합니다.
keywords: 공격 표면 감소, hips, 호스트 침입 방지 시스템, 보호 규칙, 악용 방지, 악용, 감염 방지, 사용, 켜기
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
audience: ITPro
author: dansimp
ms.author: dansimp
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 84947057abbd456dee5cbf5d0c6fea37f679d9ad
ms.sourcegitcommit: 6e5c00f84b5201422aed094f2697016407df8fc2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/02/2021
ms.locfileid: "51570951"
---
# <a name="enable-attack-surface-reduction-rules"></a>공격 표면 감소 규칙 사용

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**적용 대상:**
- [엔드포인트용 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037) 
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>Endpoint용 Defender를 경험하고 싶나요? [무료 평가판에 등록합니다.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

ASR [규칙(공격](attack-surface-reduction.md) 표면 축소 규칙)은 맬웨어가 장치 및 네트워크를 손상하기 위해 자주 남용되는 작업을 방지하는 데 도움이 됩니다. 다음 Windows 버전 및 버전을 실행하는 장치에 대해 ASR 규칙을 설정할 수 있습니다.
- Windows 10 Pro 버전 [1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709) 이상
- Windows 10 Enterprise 버전 [1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709) 이상
- Windows Server, [버전 1803(반기 채널)](https://docs.microsoft.com/windows-server/get-started/whats-new-in-windows-server-1803) 이상
- [Windows Server 2019](https://docs.microsoft.com/windows-server/get-started-19/whats-new-19)

각 ASR 규칙에는 다음 세 가지 설정 중 하나가 포함되어 있습니다.

- 구성되지 않은 경우: ASR 규칙을 사용하지 않도록 설정
- 차단: ASR 규칙 사용
- 감사: ASR 규칙이 사용하도록 설정된 경우 조직에 미치는 영향 평가

Windows E5 라이선스(또는 유사한 라이선스 SKU)와 함께 ASR 규칙을 사용하여 [끝점용 Microsoft Defender(Endpoint용 Defender)에서](https://docs.microsoft.com/windows/security/threat-protection) 사용할 수 있는 고급 모니터링 및 보고 기능을 활용하는 것이 좋습니다. 그러나 고급 모니터링 및 보고 기능에 액세스할 수 없는 Windows Professional 또는 E3와 같은 다른 라이선스의 경우 ASR 규칙이 트리거될 때 각 끝점에서 생성되는 이벤트(예: 이벤트 전달)를 통해 자체 모니터링 및 보고 도구를 개발할 수 있습니다.

> [!TIP]
> Windows 라이선스에 대한 자세한 내용은 Windows 10 라이선스를 참조하고 Windows [10용](https://www.microsoft.com/licensing/product-licensing/windows10?activetab=windows10-pivot:primaryr5) 볼륨 라이선스 [가이드를 참조하세요.](https://download.microsoft.com/download/2/D/1/2D14FE17-66C2-4D4C-AF73-E122930B60F6/Windows-10-Volume-Licensing-Guide.pdf)

다음 방법을 사용하여 공격 표면 감소 규칙을 사용하도록 설정할 수 있습니다.

- [Microsoft Intune](#intune)
- [MDM(모바일 장치 관리)](#mdm)
- [Microsoft Endpoint Configuration Manager](#microsoft-endpoint-configuration-manager)
- [그룹 정책](#group-policy)
- [PowerShell](#powershell)

Intune 또는 Microsoft Endpoint Manager와 같은 엔터프라이즈 수준 관리가 권장됩니다. 엔터프라이즈 수준 관리는 시작 시 충돌하는 그룹 정책 또는 PowerShell 설정을 덮어 덮어 덮어 들이게 됩니다.

## <a name="exclude-files-and-folders-from-asr-rules"></a>ASR 규칙에서 파일 및 폴더 제외

대부분의 공격 표면 감소 규칙에 의해 평가되지 않는 파일 및 폴더를 제외할 수 있습니다. 즉, ASR 규칙이 파일 또는 폴더에 악의적인 동작이 포함되어 있는지 확인한 경우에도 파일이 실행되는 것을 차단하지 않습니다. 이렇게 하면 안전하지 않은 파일이 실행되고 장치를 감염시킬 수 있습니다.

끝점 파일 및 인증서 표시기를 위해 지정된 Defender를 허용하여 인증서 및 파일 해시에 따라 ASR 규칙을 트리거하지 못하게 제외할 수도 있습니다. [(표시기 관리를](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/manage-indicators)참조합니다.)

> [!IMPORTANT]
> 파일 또는 폴더를 제외하면 ASR 규칙에서 제공하는 보호를 심각하게 줄일 수 있습니다. 제외된 파일은 실행될 수 있으며 보고서나 이벤트는 기록되지 않습니다.
> ASR 규칙이 검색되지 않는 것으로 생각되는 파일을 검색하는 경우 먼저 감사 모드를 사용하여 규칙을 [테스트해야 합니다.](evaluate-attack-surface-reduction.md)


개별 파일 또는 폴더(폴더 경로 또는 정식 리소스 이름을 사용하여)를 지정할 수 있지만 제외가 적용되는 규칙을 지정할 수 없습니다. 제외는 제외된 응용 프로그램 또는 서비스가 시작될 때만 적용됩니다. 예를 들어 이미 실행 중인 업데이트 서비스에 대해 제외를 추가하는 경우 업데이트 서비스는 서비스가 중지되고 다시 시작될 때까지 이벤트를 계속 트리거합니다.

ASR 규칙은 환경 변수 및 와일드카드를 지원합니다. 와일드카드 사용에 대한 자세한 내용은 파일 이름 및 폴더 경로 또는 확장명 제외 목록에 와일드카드 사용을 [참조하세요.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-extension-file-exclusions-microsoft-defender-antivirus#use-wildcards-in-the-file-name-and-folder-path-or-extension-exclusion-lists)

ASR 규칙을 사용하도록 설정하는 다음 절차에는 파일 및 폴더를 제외하는 방법에 대한 지침이 포함되어 있습니다.

## <a name="intune"></a>Intune

1. 장치 **구성**  >  **프로필을 선택합니다.** 기존 끝점 보호 프로필을 선택하거나 새 끝점 보호 프로필을 만들 수 있습니다. 새 프로필을 만들하려면 프로필 만들기를 **선택하고** 이 프로필에 대한 정보를 입력합니다. 프로필 **유형에서** **끝점 보호를 선택합니다.** 기존 프로필을 선택한 경우 속성을 선택한 **다음** 설정을 **선택합니다.**

2. 끝점 보호 창에서 **Exploit** **Guard** Windows Defender 선택하고 공격 표면 **감소를 선택합니다.** 각 ASR 규칙에 대해 원하는 설정을 선택합니다.

3. 공격 **표면 감소 예외에서** 개별 파일 및 폴더를 입력합니다. 가져오기 **를** 선택하여 ASR 규칙에서 제외할 파일 및 폴더가 포함된 CSV 파일을 가져올 수도 있습니다. CSV 파일의 각 줄 서식은 다음과 같이 지정해야 합니다.

   `C:\folder`, `%ProgramFiles%\folder\file`, `C:\path`

4. 세 **개의 구성** 창에서 확인을 선택합니다. 그런 다음 **새** 끝점 보호 파일을 만드는  경우 만들기를 선택하고 기존 끝점 보호 파일을 편집하는 경우 저장을 선택합니다.

## <a name="mdm"></a>MDM

[./Vendor/MSFT/Policy/Config/Defender/AttackSurfaceReductionRules](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-attacksurfacereductionrules) CSP(구성 서비스 공급자)를 사용하여 각 규칙에 대해 모드를 개별적으로 사용하도록 설정하고 설정할 수 있습니다.

다음은 ASR 규칙에 GUID 값을 사용하는 참조용 [샘플입니다.](attack-surface-reduction.md#attack-surface-reduction-rules)

`OMA-URI path: ./Vendor/MSFT/Policy/Config/Defender/AttackSurfaceReductionRules`

`Value: 75668C1F-73B5-4CF0-BB93-3ECF5CB7CC84=2|3B576869-A4EC-4529-8536-B80A7769E899=1|D4F940AB-401B-4EfC-AADC-AD5F3C50688A=2|D3E037E1-3EB8-44C8-A917-57927947596D=1|5BEB7EFE-FD9A-4556-801D-275E5FFC04CC=0|BE9BA2D9-53EA-4CDC-84E5-9B1EEEE46550=1`

감사 모드에서 사용, 사용 안 하도록 설정 또는 사용 하도록 설정 하는 값은:

- Disable = 0
- 차단(ASR 규칙 사용) = 1
- 감사 = 2

[./Vendor/MSFT/Policy/Config/Defender/AttackSurfaceReductionOnlyExclusions](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-attacksurfacereductiononlyexclusions) CSP(구성 서비스 공급자)를 사용하여 제외를 추가합니다.

예제:

`OMA-URI path: ./Vendor/MSFT/Policy/Config/Defender/AttackSurfaceReductionOnlyExclusions`

`Value: c:\path|e:\path|c:\Exclusions.exe`

> [!NOTE]
> 공백 없이 OMA-URI 값을 입력해야 합니다.

## <a name="microsoft-endpoint-configuration-manager"></a>Microsoft Endpoint Configuration Manager

1. Microsoft Endpoint Configuration Manager에서 Exploit **Guard의** 자산 및 준수 끝점 보호  >    >  **Windows Defender 로 이동합니다.**

2. 홈 **Exploit**  >  **Guard 정책 만들기 를 선택합니다.**

3. 이름과 설명을 입력하고 공격 **표면 감소를 선택하고** 다음 을 **선택합니다.**

4. 작업을 차단하거나 감사할 규칙을 선택하고 다음 을 **선택합니다.**

5. 설정을 검토하고 **다음을** 선택하여 정책을 만들 수 있습니다.

6. 정책을 만든 후 를 **닫습니다.**

## <a name="group-policy"></a>그룹 정책

> [!WARNING]
> Intune, Configuration Manager 또는 기타 엔터프라이즈 수준 관리 플랫폼을 사용하여 컴퓨터와 장치를 관리하는 경우 관리 소프트웨어가 시작 시 충돌하는 그룹 정책 설정을 덮어 덮어 덮어 사용합니다.

1. 그룹 정책 관리 컴퓨터에서 그룹 정책 관리 콘솔을 [열고](https://technet.microsoft.com/library/cc731212.aspx)구성할 그룹 정책 개체를 마우스 오른쪽 단추로 클릭하고 편집을 **선택합니다.**

2. 그룹 **정책 관리 편집기에서** 컴퓨터 **구성으로 이동하여** 관리 **템플릿을 선택합니다.**

3. **Windows** 구성 요소 Microsoft Defender 바이러스 백신 Microsoft Defender Exploit Guard 공격 표면 감소까지  >    >    >  **트리를 확장합니다.**

4. 공격 **표면 축소 규칙 구성을 선택하고** 사용 을 **선택합니다.** 그런 다음 옵션 섹션에서 각 규칙에 대한 개별 상태를 설정할 수 있습니다.

     **표시...를** 선택하고 값 이름 열에 규칙 ID를 입력하고 다음과 같이 값 열에 선택한 상태를 입력합니다.

   - Disable = 0
   - 차단(ASR 규칙 사용) = 1
   - 감사 = 2

   ![빈 공격 표면 축소 규칙 ID 및 값 1을 보여 주는 그룹 정책 설정](/microsoft-365/security/defender-endpoint/images/asr-rules-gp)

5. ASR 규칙에서 파일 및 폴더를  제외하려면 공격 표면 축소 규칙에서 파일 및 경로 제외 설정을 선택하고 옵션을 사용으로 **설정합니다.** 표시를 **선택하고** 값 이름 열에 각 파일 또는 **폴더를 입력합니다.** 각 항목의 값 **열에** **0을** 입력합니다.

> [!WARNING]
> 값 이름 열이나 값 열에 대해  지원되지 않는 따옴표를 사용하지 **않습니다.**

## <a name="powershell"></a>PowerShell

> [!WARNING]
> Intune, Configuration Manager 또는 다른 엔터프라이즈 수준의 관리 플랫폼을 사용하여 컴퓨터 및 장치를 관리하는 경우 관리 소프트웨어가 시작 시 충돌하는 PowerShell 설정을 덮어 덮어 덮어 습니다. 사용자가 PowerShell을 사용하여 값을 정의할 수 있도록 허용하기 위해 관리 플랫폼에서 규칙에 대해 "사용자 정의" 옵션을 사용합니다.

1. 시작 **메뉴에 powershell을** 입력하고 마우스 오른쪽 단추로 Windows PowerShell **관리자** 권한으로 **실행을 선택합니다.**

2. 다음 cmdlet을 입력합니다.

    ```PowerShell
    Set-MpPreference -AttackSurfaceReductionRules_Ids <rule ID> -AttackSurfaceReductionRules_Actions Enabled
    ```

    감사 모드에서 ASR 규칙을 사용하도록 설정하려면 다음 cmdlet을 사용 합니다.

    ```PowerShell
    Add-MpPreference -AttackSurfaceReductionRules_Ids <rule ID> -AttackSurfaceReductionRules_Actions AuditMode
    ```

    ASR 규칙을 끄기 위해 다음 cmdlet을 사용 합니다.

    ```PowerShell
    Add-MpPreference -AttackSurfaceReductionRules_Ids <rule ID> -AttackSurfaceReductionRules_Actions Disabled
    ```

    > [!IMPORTANT]
    > 각 규칙에 대해 개별적으로 상태를 지정해야 하지만 규칙과 상태를 콤보로 구분된 목록에서 결합할 수 있습니다.
    >
    > 다음 예제에서는 처음 두 규칙을 사용하도록 설정하고, 세 번째 규칙은 사용하지 않도록 설정하고, 네 번째 규칙은 감사 모드에서 사용하도록 설정됩니다.
    >
    > ```PowerShell
    > Set-MpPreference -AttackSurfaceReductionRules_Ids <rule ID 1>,<rule ID 2>,<rule ID 3>,<rule ID 4> -AttackSurfaceReductionRules_Actions Enabled, Enabled, Disabled, AuditMode
    > ```

    PowerShell 동사로 기존 목록에 새 규칙을 `Add-MpPreference` 추가할 수도 있습니다.

    > [!WARNING]
    > `Set-MpPreference` 는 항상 기존 규칙 집합을 덮어 덮어 들이게 됩니다. 기존 집합에 추가하려는 경우 대신 를 `Add-MpPreference` 사용합니다.
    > 를 사용하여 규칙 및 규칙의 현재 상태 목록을 얻을 수 `Get-MpPreference` 있습니다.

3. ASR 규칙에서 파일 및 폴더를 제외하려면 다음 cmdlet을 사용 합니다.

    ```PowerShell
    Add-MpPreference -AttackSurfaceReductionOnlyExclusions "<fully qualified path or resource>"
    ```

    계속 사용하여 목록에 파일 및 `Add-MpPreference -AttackSurfaceReductionOnlyExclusions` 폴더를 더 추가합니다.

    > [!IMPORTANT]
    > 목록에 `Add-MpPreference` 앱을 추가하거나 추가하는 데 사용할 수 있습니다. `Set-MpPreference`cmdlet을 사용하여 기존 목록을 덮어 습니다.

## <a name="related-articles"></a>관련 문서

- [공격 표면 감소 규칙을 사용하여 공격 표면 감소](attack-surface-reduction.md)

- [공격 표면 감소 평가](evaluate-attack-surface-reduction.md)

- [공격 표면 감소 FAQ](attack-surface-reduction.md)
