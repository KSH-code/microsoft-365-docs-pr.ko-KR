---
title: 공격 표면 감소 규칙 사용자 지정
description: 개별적으로 감사, 차단 또는 비활성화 모드에서 규칙을 설정하고 공격 표면 감소 규칙에서 제외해야 하는 파일 및 폴더를 추가합니다.
keywords: 공격 표면 감소, hips, 호스트 침입 방지 시스템, 보호 규칙, 악용 방지, 악용, 감염 방지, 사용자 지정, 구성, 제외
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: Normal
audience: ITPro
author: jweston-1
ms.author: v-jweston
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.topic: article
ms.collection: M365-security-compliance
ms.openlocfilehash: 92cb643d0e133f0b850e16e076a88901b595e426
ms.sourcegitcommit: 6968594dc8cf8b30a4c958df6d65dfd0cd2cfae1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/23/2021
ms.locfileid: "59490958"
---
# <a name="customize-attack-surface-reduction-rules"></a>공격 표면 감소 규칙 사용자 지정

**적용 대상:**

- [엔드포인트용 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Endpoint용 Defender를 경험하고 싶나요? [무료 평가판을 신청하세요.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-assignaccess-abovefoldlink)

> [!IMPORTANT]
> 일부 정보는 상용으로 출시되기 전에 실질적으로 수정될 수 있는 사전 릴리스된 제품과 관련이 있습니다. Microsoft는 여기에서 제공하는 정보와 관련하여 명시적이거나 묵시적인 어떠한 보증도 제공하지 않습니다.

[공격 표면 감소 규칙은](enable-attack-surface-reduction.md) 장치 또는 네트워크를 손상하기 위해 자주 남용되는 소프트웨어 동작을 방지하는 데 도움이 됩니다. 예를 들어 공격자는 USB 드라이브에서 부호 없는 스크립트를 실행하려고 시도하거나, 문서의 매크로가 Office Win32 API를 직접 호출할 수 있습니다. 공격 표면 감소 규칙은 이러한 종류의 위험한 동작을 제한하고 조직의 방어적 자세를 개선할 수 있습니다.

파일 및 폴더를 제외하거나 [](#exclude-files-and-folders) 사용자 컴퓨터에 나타나는 알림 [](#customize-the-notification) 경고에 사용자 지정 텍스트를 추가하여 공격 표면 감소 규칙을 사용자 지정하는 방법을 학습합니다.

다음 버전 및 버전의 디바이스를 실행하는 장치에 대해 공격 표면 감소 규칙을 설정할 수 Windows.

- Windows 10 Pro 버전 [1709](/windows/whats-new/whats-new-windows-10-version-1709) 이상
- Windows 10 Enterprise 버전 [1709](/windows/whats-new/whats-new-windows-10-version-1709) 이상
- Windows 서버, [버전 1803(반기 채널)](/windows-server/get-started/whats-new-in-windows-server-1803) 이상
- [Windows Server 2019](/windows-server/get-started-19/whats-new-19)

그룹 정책, PowerShell 및 MDM(모바일 장치 관리) CSP(구성 서비스 공급자)를 사용하여 이러한 설정을 구성할 수 있습니다.

[지원되는](enable-attack-surface-reduction.md#requirements) 운영 체제 및 추가 요구 사항에 대한 자세한 내용은 "공격 표면 감소 규칙 사용" 문서의 요구 사항을 참조하세요.

## <a name="exclude-files-and-folders"></a>파일 및 폴더 제외

파일 및 폴더가 공격 표면 축소 규칙에 의해 평가되지 못하게 제외할 수 있습니다. 제외된 경우 공격 표면 감소 규칙이 파일에 악의적인 동작이 포함되어 있는 것을 감지한 경우에도 파일이 실행되지 않습니다.

예를 들어 랜섬웨어 규칙을 고려합니다.

랜섬웨어 규칙은 기업 고객이 비즈니스 연속성을 보장하면서 랜섬웨어 공격의 위험을 줄일 수 있도록 고안된 규칙입니다. 기본적으로 랜섬웨어 규칙 오류는 신중하게 처리하고 아직 충분한 신뢰도와 신뢰를 거치지 않은 파일에 대해 보호합니다. 다시 강조하기 위해 랜섬웨어 규칙은 수백만 고객의 사용 메트릭에 따라 충분히 긍정적인 평판과 보전을 얻지 않은 파일에만 트리거합니다. 일반적으로 각 파일의 "신뢰도 및 신뢰" 값은 문제가 없는 사용이 증가하면 증분적으로 업그레이드하기 때문에 블록이 자체적으로 해결됩니다.

블록이 제시간에 자체적으로 해결되지 않는 경우 고객은 셀프 서비스 메커니즘 또는 IOC(손상 표시기) 기반 "허용 목록" 기능을 사용하여 파일 차단을 해제할 수 있습니다. 

> [!WARNING]
> 파일 또는 폴더를 제외하거나 차단 해제하면 안전하지 않은 파일이 실행되고 장치를 감염시킬 수 있습니다. 파일 또는 폴더를 제외하면 공격 표면 감소 규칙에서 제공하는 보호가 크게 감소할 수 있습니다. 규칙에 의해 차단된 파일은 실행할 수 있으며 보고서나 이벤트가 기록되지 않습니다.

제외는 제외를 허용하는 모든 규칙에 적용됩니다. 개별 파일, 폴더 경로 또는 리소스의 정식 도메인 이름을 지정할 수 있습니다. 그러나 특정 규칙에 대한 제외는 제한할 수 없습니다.

제외는 제외된 응용 프로그램 또는 서비스가 시작될 때만 적용됩니다. 예를 들어 이미 실행 중인 업데이트 서비스에 대해 제외를 추가하는 경우 업데이트 서비스는 서비스가 중지되고 다시 시작될 때까지 이벤트를 계속 트리거합니다.

공격 범위 축소는 환경 변수 및 와일드카드를 지원합니다. 와일드카드 사용에 대한 자세한 내용은 파일 이름 및 폴더 경로 또는 확장명 제외 목록에서 와일드카드 [사용을 참조하세요.](configure-extension-file-exclusions-microsoft-defender-antivirus.md#use-wildcards-in-the-file-name-and-folder-path-or-extension-exclusion-lists)
검색되지 않을 것으로 생각되는 파일을 검색하는 규칙에 문제가 발생하는 경우 감사 모드를 사용하여 규칙을 [테스트합니다.](evaluate-attack-surface-reduction.md)

<br>

****

|규칙 설명|GUID|
|---|---|
|악용된 취약한 서명된 드라이버의 남용 차단|`56a863a9-875e-4185-98a7-b882c64b5ce5`|
|Adobe Reader에서 하위 프로세스를 만들지 차단|`7674ba52-37eb-4a4f-a9a1-f0f9a1619a2c`|
|모든 Office 응용 프로그램에서 자식 프로세스를 만들지 차단|`d4f940ab-401b-4efc-aadc-ad5f3c50688a`|
|로컬 보안 기관 하위 Windows(lsass.exe)에서 자격 증명 도용 차단|`9e6c4e1f-7d60-472f-ba1a-a39ef669e4b2`|
|전자 메일 클라이언트 및 웹 메일에서 실행 가능한 콘텐츠 차단|`be9ba2d9-53ea-4cdc-84e5-9b1eeee46550`|
|실행 파일이 보전, 보존 또는 신뢰할 수 있는 목록 조건을 충족하지 않는 한 실행 파일이 실행되지 못하게 차단|`01443614-cd74-433a-b99e-2ecdc07bfc25`|
|잠재적으로 난치될 수 있는 스크립트의 실행 차단|`5beb7efe-fd9a-4556-801d-275e5ffc04cc`|
|JavaScript 또는 VBScript에서 다운로드한 실행 콘텐츠 시작 차단|`d3e037e1-3eb8-44c8-a917-57927947596d`|
|응용 Office 콘텐츠 만들기 차단|`3b576869-a4ec-4529-8536-b80a7769e899`|
|응용 Office 코드 삽입 차단|`75668c1f-73b5-4cf0-bb93-3ecf5cb7cc84`|
|통신 Office 자식 프로세스를 만들지 차단|`26190899-1602-49e8-8b27-eb1d0a1ce869`|
|WMI 이벤트 구독을 통한 지속성 차단|`e6db77e5-3df2-4cf1-b95a-636979351e5b`|
|PSExec 및 WMI 명령에서 시작된 프로세스 생성 차단|`d1e49aac-8f56-4280-b9ba-993a6d77406c`|
|USB에서 실행된 무단 및 사인되지 않은 프로세스 차단|`b2b3f03d-6a65-4f7b-a9c7-1c7ef74a9ba4`|
|매크로에서 Win32 API Office 차단|`92e97fa1-2edf-4476-bdd6-9dd0b4dddc7b`|
|랜섬웨어에 대한 고급 보호 사용|`c1db55ab-c21a-4637-bb3f-a12568109d35`|
|

각 [규칙에 대한 자세한](attack-surface-reduction.md) 내용은 공격 표면 축소 항목을 참조하세요.

### <a name="use-group-policy-to-exclude-files-and-folders"></a>그룹 정책을 사용하여 파일 및 폴더 제외

1. 그룹 정책 관리 컴퓨터에서 [그룹 정책 관리 콘솔](https://technet.microsoft.com/library/cc731212.aspx)을 열고 구성하려는 그룹 정책 개체를 마우스 오른쪽 단추로 클릭한 다음 **편집** 을 선택합니다.

2. 그룹 정책 **관리 편집기에서** 컴퓨터 **구성으로 이동하여** 관리 템플릿 **을 클릭합니다.**

3. 공격 표면 **감소를 Windows 구성** \> **Microsoft Defender 바이러스 백신** \> **Microsoft Defender Exploit Guard** \> **트리를 확장합니다.**

4. 공격 표면 축소 **규칙에서** 파일 및 경로 제외 설정을 두 번 클릭하고 옵션을 사용으로 **설정합니다.** 표시를 **선택하고** 값 이름 열에 각 파일 또는 **폴더를 입력합니다.** 각 항목의 값 **열에** **0을** 입력합니다.

> [!WARNING]
> 값 이름 열이나 값 열에 대해  지원되지 않는 따옴표를 사용하지 **않습니다.**

### <a name="use-powershell-to-exclude-files-and-folders"></a>PowerShell을 사용하여 파일 및 폴더 제외

1. 목록에서 **powershell을** 시작 메뉴 마우스 오른쪽 **단추로** 클릭하고 Windows PowerShell 관리자 권한으로 **실행을 선택합니다.**
2. 다음 cmdlet을 입력합니다.

    ```PowerShell
    Add-MpPreference -AttackSurfaceReductionOnlyExclusions "<fully qualified path or resource>"
    ```

계속 사용하여 `Add-MpPreference -AttackSurfaceReductionOnlyExclusions` 목록에 폴더를 더 추가합니다.

> [!IMPORTANT]
> 목록에 `Add-MpPreference` 앱을 추가하거나 추가하는 데 사용할 수 있습니다. `Set-MpPreference`cmdlet을 사용하여 기존 목록을 덮어 습니다.

### <a name="use-mdm-csps-to-exclude-files-and-folders"></a>MDM CSP를 사용하여 파일 및 폴더 제외

[./Vendor/MSFT/Policy/Config/Defender/AttackSurfaceReductionOnlyExclusions](/windows/client-management/mdm/policy-csp-defender#defender-attacksurfacereductiononlyexclusions) CSP(구성 서비스 공급자)를 사용하여 제외를 추가합니다.

## <a name="customize-the-notification"></a>알림 사용자 지정

규칙이 트리거되는 경우 알림을 사용자 지정하고 앱 또는 파일을 차단할 수 있습니다. 자세한 [내용은 Windows 보안](/windows/security/threat-protection/windows-defender-security-center/windows-defender-security-center#customize-notifications-from-the-windows-defender-security-center) 참조하세요.

## <a name="related-topics"></a>관련 항목

- [공격 표면 감소 규칙을 사용하여 공격 표면 감소](attack-surface-reduction.md)
- [공격 표면 감소 규칙 사용](enable-attack-surface-reduction.md)
- [공격 표면 감소 규칙 평가](evaluate-attack-surface-reduction.md)
- [공격 표면 감소 FAQ](attack-surface-reduction.md)
