---
title: 공격 노출 영역 축소 규칙 사용
description: ASR(공격 표면 축소) 규칙을 사용하도록 설정하여 매크로, 스크립트 및 일반적인 삽입 기술을 사용하는 공격으로부터 장치를 보호합니다.
keywords: 공격 표면 감소, hips, 호스트 침입 방지 시스템, 보호 규칙, 악용 방지, 악용, 감염 방지, 사용, 켜기
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
audience: ITPro
author: jweston-1
ms.author: v-jweston
ms.reviewer: oogunrinde
manager: dansimp
ms.technology: mde
ms.topic: how-to
ms.date: 08/17/2021
ms.collection: m365-security-compliance
ms.openlocfilehash: 2b399e306e766a4bb1d723bd93ed22d88a72c55b
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2021
ms.locfileid: "60174894"
---
# <a name="enable-attack-surface-reduction-rules"></a>공격 노출 영역 축소 규칙 사용

**적용 대상:**

- [엔드포인트용 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> [!TIP]
> Endpoint용 Defender를 경험하고 싶나요? [무료 평가판을 신청하세요.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-assignaccess-abovefoldlink)

ASR [규칙(공격](attack-surface-reduction.md) 표면 축소 규칙)은 맬웨어가 장치 및 네트워크를 손상하기 위해 자주 남용되는 작업을 방지하는 데 도움이 됩니다.

## <a name="requirements"></a>요구 사항

여러 버전에서 공격 Windows 기능

다음 버전 및 버전의 디바이스를 실행하는 장치에 대해 공격 표면 감소 규칙을 설정할 수 Windows.

- Windows 10 Pro 버전 [1709](/windows/whats-new/whats-new-windows-10-version-1709) 이상
- Windows 10 Enterprise 버전 [1709](/windows/whats-new/whats-new-windows-10-version-1709) 이상
- Windows 서버, [버전 1803(반기 채널)](/windows-server/get-started/whats-new-in-windows-server-1803) 이상
- [Windows Server 2019](/windows-server/get-started-19/whats-new-19)
- Windows Server 2022

공격 표면 감소 규칙의 전체 기능 집합을 사용하려면 다음이 필요합니다.

- Windows Defender 바이러스 백신 AV로 사용(실시간 보호 기능)
- [클라우드 배달 보호](/windows/security/threat-protection/microsoft-defender-antivirus/enable-cloud-protection-microsoft-defender-antivirus) 기능 사용(일부 규칙의 경우
- Windows 10 Enterprise E5 또는 E3 라이선스 또는 Microsoft 365 라이선스

공격 표면 감소 규칙에는 [Windows E5](/windows/deployment/deploy-enterprise-licenses)라이선스가 필요하지는 않습니다. Windows E5 라이선스가 있는 경우 끝점용 Defender에서 사용 가능한 모니터링, 분석 및 워크플로를 비롯한 고급 관리 기능과 Microsoft 365 보안 센터의 보고 및 구성 기능을 사용할 수 있습니다. E3 라이선스에서는 이러한 고급 기능을 사용할 수 없지만 이벤트 뷰어를 사용하여 공격 표면 축소 규칙 이벤트를 검토할 수 있습니다.

각 ASR 규칙에는 다음 네 가지 설정 중 하나가 포함되어 있습니다.

- **구성되지 않은 경우:** ASR 규칙을 사용하지 않도록 설정
- **차단:** ASR 규칙 사용
- **감사:** ASR 규칙이 사용하도록 설정된 경우 조직에 미치는 영향 평가
- **경고:** ASR 규칙을 사용하도록 설정하지만 최종 사용자가 차단을 무시하도록 허용

> [!IMPORTANT]
> 현재 MEM(2013)에서 ASR 규칙을 구성할 때 세 가지 ASR 규칙에 대해 경고 Microsoft Endpoint Manager 지원되지 않습니다. 자세한 내용은 경고 모드가 지원되지 [않는 경우를 참조합니다.](attack-surface-reduction.md#cases-where-warn-mode-is-not-supported)

Windows E5 라이선스(또는 유사한 라이선스 SKU)와 함께 ASR 규칙을 사용하여 [끝점용 Microsoft Defender(Endpoint용 Defender)에서](microsoft-defender-endpoint.md) 사용할 수 있는 고급 모니터링 및 보고 기능을 활용하는 것이 좋습니다. 그러나 고급 모니터링 및 보고 기능을 포함하지 않는 Windows Professional 또는 Windows E3와 같은 다른 라이선스가 있는 경우 ASR 규칙이 트리거될 때 각 끝점에서 생성되는 이벤트(예: 이벤트 전달)에서 자체 모니터링 및 보고 도구를 개발할 수 있습니다.

> [!TIP]
> 라이선스 라이선스에 대한 Windows 자세한 내용은 [](https://www.microsoft.com/licensing/product-licensing/windows10?activetab=windows10-pivot:primaryr5) Windows 10 라이선스를 참조하고 에 대한 볼륨 라이선스 [가이드를 Windows 10.](https://download.microsoft.com/download/2/D/1/2D14FE17-66C2-4D4C-AF73-E122930B60F6/Windows-10-Volume-Licensing-Guide.pdf)

다음 방법을 사용하여 공격 표면 감소 규칙을 사용하도록 설정할 수 있습니다.

- [Microsoft Intune](#intune)
- [MDM(모바일 장치 관리)](#mdm)
- [Microsoft Endpoint Configuration Manager](#microsoft-endpoint-configuration-manager)
- [그룹 정책](#group-policy)
- [PowerShell](#powershell)

Enterprise Intune 또는 Microsoft Endpoint Manager 수준의 관리가 권장됩니다. Enterprise 수준 관리는 시작 시 충돌하는 그룹 정책 또는 PowerShell 설정을 덮어 덮어 덮어 야 합니다.

## <a name="exclude-files-and-folders-from-asr-rules"></a>ASR 규칙에서 파일 및 폴더 제외

대부분의 공격 표면 감소 규칙에 의해 평가되지 않는 파일 및 폴더를 제외할 수 있습니다. 즉, ASR 규칙이 파일 또는 폴더에 악의적인 동작이 포함되어 있는지 확인한 경우에도 파일이 실행되는 것을 차단하지 않습니다. 이렇게 하면 안전하지 않은 파일이 실행되고 장치를 감염시킬 수 있습니다.

끝점 파일 및 인증서 표시기를 위해 지정된 Defender를 허용하여 인증서 및 파일 해시에 따라 ASR 규칙을 트리거하지 못하게 제외할 수도 있습니다. [(표시기 관리를](manage-indicators.md)참조합니다.)

> [!IMPORTANT]
> 파일 또는 폴더를 제외하면 ASR 규칙에서 제공하는 보호를 심각하게 줄일 수 있습니다. 제외된 파일은 실행될 수 있으며 보고서나 이벤트는 기록되지 않습니다.
> ASR 규칙이 검색되지 않는 것으로 생각되는 파일을 검색하는 경우 먼저 감사 모드를 사용하여 규칙을 [테스트해야 합니다.](evaluate-attack-surface-reduction.md)

개별 파일 또는 폴더(폴더 경로 또는 정식 리소스 이름을 사용하여)를 지정할 수 있지만 제외가 적용되는 규칙을 지정할 수 없습니다. 제외는 제외된 응용 프로그램 또는 서비스가 시작될 때만 적용됩니다. 예를 들어 이미 실행 중인 업데이트 서비스에 대해 제외를 추가하는 경우 업데이트 서비스는 서비스가 중지되고 다시 시작될 때까지 이벤트를 계속 트리거합니다.

ASR 규칙은 환경 변수 및 와일드카드를 지원합니다. 와일드카드 사용에 대한 자세한 내용은 파일 이름 및 폴더 경로 또는 확장명 제외 목록에 와일드카드 사용을 [참조하세요.](configure-extension-file-exclusions-microsoft-defender-antivirus.md#use-wildcards-in-the-file-name-and-folder-path-or-extension-exclusion-lists)

ASR 규칙을 사용하도록 설정하는 다음 절차에는 파일 및 폴더를 제외하는 방법에 대한 지침이 포함되어 있습니다.

## <a name="intune"></a>Intune

1. 장치 **구성** \> **프로필을 선택합니다.** 기존 끝점 보호 프로필을 선택하거나 새 끝점 보호 프로필을 만들 수 있습니다. 새 프로필을 만들하려면 프로필 만들기를 **선택하고** 이 프로필에 대한 정보를 입력합니다. 프로필 **유형에서** **끝점 보호를 선택합니다.** 기존 프로필을 선택한 경우 속성을  선택한 다음 을 **설정.**

2. 끝점 보호 창에서 **Exploit** **Guard** Windows Defender 선택하고 공격 표면 **감소를 선택합니다.** 각 ASR 규칙에 대해 원하는 설정을 선택합니다.

3. 공격 **표면 감소 예외에서** 개별 파일 및 폴더를 입력합니다. 가져오기 **를** 선택하여 ASR 규칙에서 제외할 파일 및 폴더가 포함된 CSV 파일을 가져올 수도 있습니다. CSV 파일의 각 줄 서식은 다음과 같이 지정해야 합니다.

   `C:\folder`, `%ProgramFiles%\folder\file`, `C:\path`

4. 세 **개의 구성** 창에서 확인을 선택합니다. 그런 다음 **새** 끝점 보호 파일을 만드는  경우 만들기를 선택하고 기존 끝점 보호 파일을 편집하는 경우 저장을 선택합니다.

## <a name="mem"></a>MEM

MEM(Microsoft Endpoint Manager) OMA-URI를 사용하여 사용자 지정 ASR 규칙을 구성할 수 있습니다. 다음 절차에서는 이 예제에 악용된 취약한 드라이버의 [남용](attack-surface-reduction-rules.md#block-abuse-of-exploited-vulnerable-signed-drivers) 차단 규칙을 사용합니다.

1. MEM(Microsoft Endpoint Manager) 관리 센터를 열 수 있습니다. 홈 **메뉴에서** **장치,** 구성 **프로필을** 선택한 다음 프로필 **만들기를 클릭합니다.**

   > [!div class="mx-imgBorder"]
   > ![MEM 프로필 만들기.](images/mem01-create-profile.png)

2. 프로필 **만들기의** 다음 두 드롭다운 목록에서 다음을 선택합니다.

   - **플랫폼에서** 추가 Windows 10 **이상을 선택합니다.**
   - 프로필 **유형에서** **템플릿을 선택합니다.**

   사용자 **지정 을** 선택한 다음 만들기를 **클릭합니다.**

   > [!div class="mx-imgBorder"]
   > ![MEM 규칙 프로필 특성](images/mem02-profile-attributes.png)

3. 사용자 지정 서식 파일 도구가 **1단계 기본 으로 열립니다.** **1 기본 사항 의** **이름에** 서식 파일 이름을  입력하고 설명에 설명을 입력할 수 있습니다(선택 사항).

   > [!div class="mx-imgBorder"]
   > ![MEM 기본 특성.](images/mem03-1-basics.png)

4. **다음** 을 클릭합니다. **2단계 구성 설정이** 열립니다. OMA-URI 설정 추가를 **클릭합니다.** 이제 추가 및 **내보내기의 두 가지** 옵션이 **표시됩니다.**

   > [!div class="mx-imgBorder"]
   > ![MEM 구성 설정.](images/mem04-2-configuration-settings.png)

5. 추가를 **다시** 클릭합니다. 행 **추가 OMA-URI** 설정 열립니다. 행 **추가에서** 다음을 합니다.

   - **이름에** 규칙의 이름을 입력합니다.
   - **설명에** 간단한 설명을 입력합니다.
  - **OMA-URI에서** 추가하는 규칙에 대한 특정 OMA-URI 링크를 입력하거나 붙여넣습니다. 이 예제 규칙에 사용할 OMA-URI에 대해 이 항목의 앞부분에 있는 MEM 섹션을 참조하세요. ASR 규칙 GUIDS에 대한 자세한 내용은 [공격](attack-surface-reduction-rules.md#per-rule-descriptions) 표면 감소 규칙 항목의 규칙 설명을 참조하세요.
   - 데이터 **형식에서** 문자열 을 **선택합니다.**
   - **값에서** GUID 값, 부호 및 상태 값을 공백이 없는 상태로 입력하거나 \= 붙여넣습니다(_GUID=StateValue)._ Where: {0 : Disable (Disable the ASR rule)}, {1 : Block (Enable the ASR rule)}, {2 : Audit (Evaluate how the ASR rule would impact your organization if enabled)}, {6 : Warn (Enable the ASR rule but allow the end-user to bypass the block)}

   > [!div class="mx-imgBorder"]
   > ![MEM OMA URI 구성.](images/mem05-add-row-oma-uri.png)

6. **저장** 을 클릭합니다. **행 추가** 닫기 사용자 **지정에서** 다음 을 **클릭합니다.** **3단계 범위 태그에서** 범위 태그는 선택 사항입니다. 다음 중 하나를 수행합니다.

   - 범위 **태그 선택을 클릭하고** 범위 태그(선택 사항)를 선택한 후 다음 을 **클릭합니다.**
   - 또는 **다음을 클릭합니다.**

7. **4단계 할당 의** **포함** 그룹 - 이 규칙을 적용할 그룹에 대해 다음 옵션에서 선택합니다.

   - **그룹 추가**
   - **모든 사용자 추가**
   - **모든 장치 추가**

   > [!div class="mx-imgBorder"]
   > ![MEM 할당.](images/mem06-4-assignments.png)

8. 제외된 **그룹에서** 이 규칙에서 제외할 그룹을 선택하고 다음 을 **클릭합니다.**

9. **5단계에서** 다음 설정에 대한 적용성 규칙을 적용합니다.

   - **규칙에서**, 다음의 경우 프로필 할당을 **선택하거나,** 프로필 할당 안 **의 경우**
   - **속성에서** 이 규칙을 적용할 속성을 선택합니다.
   - **값에** 해당하는 값 또는 값 범위를 입력합니다.

   > [!div class="mx-imgBorder"]
   > ![MEM 적용성 규칙.](images/mem07-5-applicability-rules.png)

10. **다음** 을 클릭합니다. **6단계 검토 + 만들기에서** 선택한 후 입력한 설정 및 정보를 검토하고 만들기를 **클릭합니다.**

    > [!div class="mx-imgBorder"]
    > ![MEM 검토 및 만들기.](images/mem08-6-review-create.png)

    > [!NOTE]
    > 규칙은 활성화된 후 몇 분 내에 활성화됩니다.

> [!NOTE]
> 충돌 처리:
>
> 디바이스에 두 가지 서로 다른 ASR 정책을 할당하는 경우 충돌이 처리되는 방법은 서로 다른 상태의 규칙이 할당되어 있으며, 충돌 관리가 없는 것이고 그 결과로 오류가 발생합니다.
>
> 충돌하지 않는 규칙은 오류를 발생하지 않습니다. 규칙이 올바르게 적용됩니다. 결과적으로 첫 번째 규칙이 적용되고 이후에 충돌하지 않는 규칙이 정책에 병합됩니다.

## <a name="mdm"></a>MDM

[./Vendor/MSFT/Policy/Config/Defender/AttackSurfaceReductionRules](/windows/client-management/mdm/policy-csp-defender#defender-attacksurfacereductionrules) CSP(구성 서비스 공급자)를 사용하여 각 규칙에 대해 모드를 개별적으로 사용하도록 설정하고 설정할 수 있습니다.

다음은 공격 표면 감소 규칙에 GUID 값을 사용하는 참조용 [샘플입니다.](attack-surface-reduction-rules.md)

`OMA-URI path: ./Vendor/MSFT/Policy/Config/Defender/AttackSurfaceReductionRules`

`Value: 75668c1f-73b5-4cf0-bb93-3ecf5cb7cc84=2|3b576869-a4ec-4529-8536-b80a7769e899=1|d4f940ab-401b-4efc-aadc-ad5f3c50688a=2|d3e037e1-3eb8-44c8-a917-57927947596d=1|5beb7efe-fd9a-4556-801d-275e5ffc04cc=0|be9ba2d9-53ea-4cdc-84e5-9b1eeee46550=1`

감사 모드에서 사용(차단), 사용 안 하도록 설정, 경고 또는 사용 하도록 설정할 값은:

- 0: 사용 안 하게(ASR 규칙 사용 안 하게)
- 1: 차단(ASR 규칙 사용)
- 2: 감사(ASR 규칙이 사용하도록 설정된 경우 조직에 어떤 영향을 미치는지 평가)
- 6: 경고(ASR 규칙을 사용하도록 설정하지만 최종 사용자가 차단을 무시하도록 허용). 이제 경고 모드를 대부분의 ASR 규칙에 사용할 수 있습니다.

[./Vendor/MSFT/Policy/Config/Defender/AttackSurfaceReductionOnlyExclusions](/windows/client-management/mdm/policy-csp-defender#defender-attacksurfacereductiononlyexclusions) CSP(구성 서비스 공급자)를 사용하여 제외를 추가합니다.

예제:

`OMA-URI path: ./Vendor/MSFT/Policy/Config/Defender/AttackSurfaceReductionOnlyExclusions`

`Value: c:\path|e:\path|c:\Exclusions.exe`

> [!NOTE]
> 공백 없이 OMA-URI 값을 입력해야 합니다.

## <a name="microsoft-endpoint-configuration-manager"></a>Microsoft Endpoint Configuration Manager

1. 이 Microsoft Endpoint Configuration Manager Exploit **Guard에서** 자산 및 규정 준수 Endpoint Protection \>  \> **Windows Defender 로 이동합니다.**

2. 홈 **Exploit** \> **Guard 정책 만들기 를 선택합니다.**

3. 이름과 설명을 입력하고 공격 **표면 감소를 선택하고** 다음 을 **선택합니다.**

4. 작업을 차단하거나 감사할 규칙을 선택하고 다음 을 **선택합니다.**

5. 설정을 검토하고 **다음을** 선택하여 정책을 만들 수 있습니다.

6. 정책을 만든 후 를 **닫습니다.**

## <a name="group-policy"></a>그룹 정책

> [!WARNING]
> Intune, Configuration Manager 또는 기타 엔터프라이즈 수준 관리 플랫폼을 사용하여 컴퓨터와 장치를 관리하는 경우 관리 소프트웨어가 시작 시 충돌하는 그룹 정책 설정을 덮어 덮어 덮어 사용합니다.

1. 그룹 정책 관리 컴퓨터에서 [그룹 정책 관리 콘솔](https://technet.microsoft.com/library/cc731212.aspx)을 열고 구성하려는 그룹 정책 개체를 마우스 오른쪽 단추로 클릭한 다음 **편집** 을 선택합니다.

2. **그룹 정책 관리 편집기** 에서 **컴퓨터 구성** 으로 이동하여 **관리 템플릿** 을 선택합니다.

3. 공격 표면 **감소를 Windows 구성** \> **Microsoft Defender 바이러스 백신** \> **Microsoft Defender Exploit Guard** \> **트리를 확장합니다.**

4. 공격 **표면 축소 규칙 구성을 선택하고** 사용 을 **선택합니다.** 그런 다음 옵션 섹션에서 각 규칙에 대한 개별 상태를 설정할 수 있습니다.

     **표시...를** 선택하고 값 이름 열에 규칙 ID를 입력하고 다음과 같이 값 열에 선택한 상태를 입력합니다.

   - 0: 사용 안 하게(ASR 규칙 사용 안 하게)
   - 1: 차단(ASR 규칙 사용)
   - 2: 감사(ASR 규칙이 사용하도록 설정된 경우 조직에 어떤 영향을 미치는지 평가)
   - 6: 경고(ASR 규칙을 사용하도록 설정하지만 최종 사용자가 차단을 무시하도록 허용)

   :::image type="content" source="images/asr-rules-gp.png" alt-text="그룹 정책의 ASR 규칙":::

5. ASR 규칙에서 파일 및 폴더를  제외하려면 공격 표면 축소 규칙에서 파일 및 경로 제외 설정을 선택하고 옵션을 사용으로 **설정합니다.** 표시를 **선택하고** 값 이름 열에 각 파일 또는 **폴더를 입력합니다.** 각 항목의 값 **열에** **0을** 입력합니다.

   > [!WARNING]
   > 값 이름 열이나 값 열에 대해  지원되지 않는 따옴표를 사용하지 **않습니다.**

## <a name="powershell"></a>PowerShell

> [!WARNING]
> Intune, Configuration Manager 또는 다른 엔터프라이즈 수준의 관리 플랫폼을 사용하여 컴퓨터 및 장치를 관리하는 경우 관리 소프트웨어가 시작 시 충돌하는 PowerShell 설정을 덮어 덮어 덮어 습니다. 사용자가 PowerShell을 사용하여 값을 정의할 수 있도록 허용하기 위해 관리 플랫폼에서 규칙에 대해 "사용자 정의" 옵션을 사용합니다.

1. 목록에서 **powershell을** 시작 메뉴 마우스 오른쪽 단추로 Windows PowerShell **관리자** 권한으로 **실행을 선택합니다.**

2. 다음 cmdlet 중 하나를 입력합니다. (규칙 [ID와](attack-surface-reduction-rules.md) 같은 자세한 내용은 공격 표면 축소 규칙을 참조합니다.)

    ```PowerShell
    Set-MpPreference -AttackSurfaceReductionRules_Ids <rule ID> -AttackSurfaceReductionRules_Actions Enabled
    ```

    감사 모드에서 ASR 규칙을 사용하도록 설정하려면 다음 cmdlet을 사용 합니다.

    ```PowerShell
    Add-MpPreference -AttackSurfaceReductionRules_Ids <rule ID> -AttackSurfaceReductionRules_Actions AuditMode
    ```

    경고 모드에서 ASR 규칙을 사용하도록 설정하려면 다음 cmdlet을 사용 합니다.

    ```PowerShell
    Add-MpPreference -AttackSurfaceReductionRules_Ids <rule ID> -AttackSurfaceReductionRules_Actions Warn
    ```

    악용된 취약한 드라이버의 남용을 ASR로 차단하려면 다음 cmdlet을 사용 합니다.

   ```PowerShell
   Add-MpPreference -AttackSurfaceReductionRules_Ids 56a863a9-875e-4185-98a7-b882c64b5ce5 -AttackSurfaceReductionRules_Actions Enabled
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
    > `Set-MpPreference` 는 항상 기존 규칙 집합을 덮어 덮어 들이게 됩니다. 기존 집합에 추가하려는 경우 대신 `Add-MpPreference` 사용합니다.
    > 를 사용하여 규칙 및 규칙의 현재 상태 목록을 얻을 수 `Get-MpPreference` 있습니다.

3. ASR 규칙에서 파일 및 폴더를 제외하려면 다음 cmdlet을 사용 합니다.

    ```PowerShell
    Add-MpPreference -AttackSurfaceReductionOnlyExclusions "<fully qualified path or resource>"
    ```

    계속 사용하여 목록에 파일 및 `Add-MpPreference -AttackSurfaceReductionOnlyExclusions` 폴더를 더 추가합니다.

    > [!IMPORTANT]
    > 목록에 `Add-MpPreference` 앱을 추가하거나 추가하는 데 사용할 수 있습니다. `Set-MpPreference`cmdlet을 사용하여 기존 목록을 덮어 습니다.

## <a name="related-articles"></a>관련 문서

- [공격 표면 감소 규칙](attack-surface-reduction-rules.md)
- [공격 표면 감소 평가](evaluate-attack-surface-reduction.md)
- [공격 표면 감소 FAQ](attack-surface-reduction.md)
