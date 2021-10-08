---
title: Azure Virtual Desktop에서 Windows 세션 장치 온보드
description: 이 문서에서 Azure Virtual Desktop의 다중 세션 Windows 온보더링에 대해 자세히 읽어 주세요.
keywords: Azure Virtual Desktop, WVD, microsoft defender, endpoint, onboard
ms.prod: w10
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
audience: ITPro
ms.topic: article
author: dansimp
ms.author: dansimp
ms.custom: nextgen
ms.reviewer: ''
manager: dansimp
ms.collection: M365-security-compliance
ms.openlocfilehash: 709cd408d548e8a7c16973c08b0369616f3b91d1
ms.sourcegitcommit: be095345257225394674698beb3feeb0696ec86d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/08/2021
ms.locfileid: "60240539"
---
# <a name="onboard-windows-multi-session-devices-in-azure-virtual-desktop"></a>Azure Virtual Desktop에서 Windows 세션 장치 온보드

6분 읽기

적용 대상:

- Windows AVD(가상 데스크톱)에서 실행되는 다중 세션

끝점용 Microsoft Defender는 VDI 및 Azure Virtual Desktop 세션 모두 모니터링을 지원합니다. 조직의 요구에 따라 VDI 또는 Azure Virtual Desktop 세션을 구현하여 직원이 관리되지 않는 디바이스, 원격 위치 또는 유사한 시나리오에서 회사 데이터 및 앱에 액세스하는 데 도움이 될 수 있습니다. 끝점용 Microsoft Defender를 사용하여 이러한 가상 컴퓨터를 모니터링하여 이상한 활동을 모니터링할 수 있습니다.

## <a name="before-you-begin"></a>시작하기 전에

비영구 [VDI에](/microsoft-365/security/defender-endpoint/configure-endpoints-vdi#onboard-non-persistent-virtual-desktop-infrastructure-vdi-devices-1)대한 고려 사항을 잘 알고 있습니다. [Azure Virtual Desktop은](/azure/virtual-desktop/overview) 비영구 옵션을 제공하지는 않는 반면, 새 호스트를 프로비전하고 컴퓨터를 다시 Windows 사용할 수 있는 골든 이미지의 사용 방법을 제공합니다. 이렇게 하면 환경의 변동성이 증가하고 끝점 포털의 Microsoft Defender 포털에서 만들어지고 유지 관리되는 항목에 영향을 주어 보안 분석가의 가시성이 감소할 수 있습니다.

> [!NOTE]
> 선택한 온보딩 방법에 따라 장치가 끝점용 Microsoft Defender 포털에 다음 중 한 가지로 표시될 수 있습니다.
>
> - 각 가상 데스크톱에 대한 단일 항목
> - 각 가상 데스크톱에 대한 여러 항목

Microsoft는 Azure Virtual Desktop을 가상 데스크톱당 단일 항목으로 온보드하는 것이 좋습니다. 이렇게 하면 Microsoft Defender 끝점 포털의 조사 환경이 컴퓨터 이름을 기반으로 한 디바이스의 컨텍스트에 있습니다. WVD 호스트를 자주 삭제하고 다시 배포하는 조직에서는 동일한 컴퓨터의 여러 개체가 끝점용 Microsoft Defender 포털에서 만들어질 수 없습니다. 이로 인해 인시던트 조사 시 혼동을 피할 수 있습니다. 테스트 또는 비휘발성 환경의 경우 다르게 선택할 수 있습니다.

WVD 골든 이미지에 끝점용 Microsoft Defender 온보딩 스크립트를 추가하는 것이 좋습니다. 이렇게 하면 이 온보딩 스크립트가 첫 번째 부팅 시 즉시 실행됩니다. 이 스크립트는 WVD 골든 이미지에서 프로비전된 모든 WVD 컴퓨터의 첫 번째 부팅 시 시작 스크립트로 실행됩니다. 그러나 수정하지 않고 갤러리 이미지 중 하나를 사용하는 경우 스크립트를 공유 위치에 두고 로컬 또는 도메인 그룹 정책에서 호출합니다.

> [!NOTE]
> WVD 골든 이미지에서 VDI 온보딩 시작 스크립트의 배치 및 구성은 WVD가 시작되면 실행되는 시작 스크립트로 구성합니다. 실제 WVD 골든 이미지를 온보드하는 것은 권장되지 않습니다. 또 다른 고려 사항은 스크립트를 실행하는 데 사용되는 메서드입니다. 세션을 받는 데 사용할 수 있는 컴퓨터와 서비스에 대한 장치 온보드 간의 시간을 줄이기 위해 가능한 한 시작/프로비저닝 프로세스 초기에 실행해야 합니다. 아래 시나리오 1에서는 & 2를 고려합니다.

### <a name="scenarios"></a>시나리오

WVD 호스트 컴퓨터는 여러 가지 방법으로 온보드합니다.

- 시작 중에 골든 이미지 또는 공유 위치에서 스크립트를 실행합니다.
- 관리 도구를 사용하여 스크립트를 실행합니다.
- [Azure Defender와의 통합을 통해](azure-server-integration.md)

#### <a name="scenario-1-using-local-group-policy"></a>*시나리오 1: 로컬 그룹 정책 사용*

이 시나리오에서는 스크립트를 골든 이미지에 배치하고 로컬 그룹 정책을 사용하여 부팅 프로세스 초기에 실행해야 합니다.

비영구적 [VDI(가상 데스크톱 인프라) 장치 온보드의 지침을 사용하세요.](configure-endpoints-vdi.md)

각 디바이스에 대한 단일 항목에 대한 지침을 따릅니다.

#### <a name="scenario-2-using-domain-group-policy"></a>*시나리오 2: 도메인 그룹 정책 사용*

이 시나리오에서는 중앙에 있는 스크립트를 사용하고 도메인 기반 그룹 정책을 사용하여 스크립트를 실행합니다. 또한 골든 이미지에 스크립트를 추가하고 동일한 방식으로 실행할 수도 있습니다.

##### <a name="download-the-windowsdefenderatponboardingpackagezip-file-from-the-windows-defender-security-center"></a>WindowsDefenderATPOnboardingPackage.zip 보안 센터에서 Windows Defender 다운로드

1. VDI 구성 패키지 파일(.zip) 열기(WindowsDefenderATPOnboardingPackage.zip)

    1. Microsoft 365 Defender 포털 탐색 창에서 **끝점** 설정(장치 관리 아래)를 \>  \>  **선택합니다.**
    1. 운영 Windows 10 Windows 또는 11을 선택합니다.
    1. 배포 **방법 필드에서** 비영구 끝점에 대한 VDI 온보딩 스크립트를 선택합니다.
    1. 패키지 **다운로드를** 클릭하고 파일 .zip 저장합니다.

2. 디바이스에서 액세스할 수 있는 .zip 읽기 전용 공유 위치로 파일 콘텐츠의 추출 **OptionalParamsPolicy라는** 폴더와 **WindowsDefenderATPOnboardingScript.cmd** 및 **Onboard-NonPersistentMachine.ps1.**

##### <a name="use-group-policy-management-console-to-run-the-script-when-the-virtual-machine-starts"></a>그룹 정책 관리 콘솔을 사용하여 가상 컴퓨터 시작 시 스크립트 실행

1. GPMC(그룹 정책 관리 콘솔)를 열고 구성할 GPO(그룹 정책 개체)를 마우스 오른쪽 단추로 클릭하고 편집을 **클릭합니다.**

2. 그룹 정책 관리 편집기에서 컴퓨터 **구성** 기본 설정 \>  \> **제어판 설정으로 이동합니다.**

3. 예약된 **작업을 마우스** 오른쪽 단추로 클릭하고 새로 고침을 **클릭한** 다음 즉시 실행 작업(최소 Windows 7)을 클릭합니다. 

4. 작업 창이 열리면 일반 **탭으로** 이동됩니다. 보안 **옵션에서** 사용자 또는 **그룹 변경을 클릭하고** SYSTEM을 입력합니다. 이름 **확인을 클릭한** 다음 확인을 클릭합니다. 작업이 실행될 사용자 계정으로 NT AUTHORITY\SYSTEM이 표시됩니다.

5. 사용자가 **로그온되어** 있는지 여부에 따라  실행을 선택하고 가장 높은 권한으로 실행 확인란을 선택합니다.

6. 작업 **탭으로** 이동하여 새로 고기를 **클릭합니다.** 작업 **필드에서 프로그램** 시작이 선택되어 있도록 합니다. 다음을 입력합니다.

   `Action = "Start a program"`

   `Program/Script = C:\WINDOWS\system32\WindowsPowerShell\v1.0\powershell.exe`

   `Add Arguments (optional) = -ExecutionPolicy Bypass -command "& \\Path\To\Onboard-NonPersistentMachine.ps1"`

   그런 다음 **확인을 선택하고** 열려 있는 GPMC 창을 닫습니다.

#### <a name="scenario-3-onboarding-using-management-tools"></a>*시나리오 3: 관리 도구를 사용한 온보드*

관리 도구를 사용하여 컴퓨터를 관리하려면 관리 도구를 사용하여 장치를 온보드할 Microsoft Endpoint Configuration Manager.

자세한 내용은 Configuration Manager를 사용하여 Windows [장치 온보드를 참조하세요.](configure-endpoints-sccm.md)

> [!WARNING]
> 공격 표면 감소 [](attack-surface-reduction-rules.md)규칙을 사용 계획하는 경우 "["PSExec](attack-surface-reduction-rules.md#block-process-creations-originating-from-psexec-and-wmi-commands)및 WMI 명령에서 시작된 프로세스 만들기 차단" 규칙은 해당 규칙을 통해 관리와 Microsoft Endpoint Configuration Manager. 이 규칙은 Configuration Manager 클라이언트가 올바르게 작동하기 위해 사용하는 WMI 명령을 차단합니다.

> [!TIP]
> 장치를 온보드한 후 검색 테스트를 실행하여 장치가 서비스에 제대로 온보드되었는지 확인할 수 있습니다. 자세한 내용은 새로 온보딩된 끝점 디바이스용 Microsoft Defender에서 검색 테스트 [실행을 참조하세요.](run-detection-test.md)

#### <a name="tagging-your-machines-when-building-your-golden-image"></a>골든 이미지를 구축할 때 컴퓨터 태그 지정

온보더링의 일부로 Microsoft 보안 센터에서 WVD 컴퓨터를 보다 쉽게 차별화할 수 있도록 컴퓨터 태그를 설정하는 것을 고려할 수 있습니다. 자세한 내용은 레지스트리 키 값을 설정하여 장치 태그 [추가를 참조하세요.](machine-tags.md#add-device-tags-by-setting-a-registry-key-value)

#### <a name="other-recommended-configuration-settings"></a>기타 권장 구성 설정

골든 이미지를 구축할 때 초기 보호 설정도 구성할 수 있습니다. 자세한 내용은 기타 권장 구성 [설정을 참조하세요.](configure-endpoints-gp.md#other-recommended-configuration-settings)

또한 FSlogix 사용자 프로필을 사용하는 경우 다음 파일을 항상 보호에서 제외하는 것이 좋습니다.

**파일 제외:**

`%ProgramFiles%\FSLogix\Apps\frxdrv.sys`

`%ProgramFiles%\FSLogix\Apps\frxdrvvt.sys`

`%ProgramFiles%\FSLogix\Apps\frxccd.sys`

`%TEMP%\*.VHD`

`%TEMP%\*.VHDX`

`%Windir%\TEMP\*.VHD`

`%Windir%\TEMP\*.VHDX`

`\\storageaccount.file.core.windows.net\share\*\*.VHD`

`\\storageaccount.file.core.windows.net\share\*\*.VHDX`

**프로세스 제외:**

`%ProgramFiles%\FSLogix\Apps\frxccd.exe`

`%ProgramFiles%\FSLogix\Apps\frxccds.exe`

`%ProgramFiles%\FSLogix\Apps\frxsvc.exe`

#### <a name="licensing-requirements"></a>라이선스 요구사항

라이선스에 대한 참고 사항: Windows Enterprise 세션을 사용하는 경우 요구 사항에 따라 모든 사용자를 끝점용 Microsoft Defender를 통해 라이선스를 부여(사용자당), Windows Enterprise E5, Microsoft 365 보안 또는 Microsoft 365 E5 또는 Azure Defender를 통해 VM 라이선스를 부여하도록 선택할 수 있습니다.
끝점용 Microsoft Defender의 라이선스 요구 사항은 라이선스 요구 [사항 에서 찾을 수 있습니다.](minimum-requirements.md#licensing-requirements)

#### <a name="related-links"></a>관련 링크

[PowerShell을 사용하여 Microsoft Defender에 대한 제외 추가](/azure/architecture/example-scenario/wvd/windows-virtual-desktop-fslogix#add-exclusions-for-windows-defender-by-using-powershell)
