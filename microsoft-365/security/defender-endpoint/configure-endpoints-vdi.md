---
title: 비영구 가상 데스크톱 인프라(VDI) 장치 온보딩
description: 끝점 서비스용 Microsoft Defender에 온보딩할 수 있도록 VDI(가상 데스크톱 인프라) 장치에 구성 패키지를 배포합니다.
keywords: VDI(가상 데스크톱 인프라) 장치 구성, vdi, 장치 관리, 끝점용 Microsoft Defender 구성, 끝점
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.date: 09/22/2021
ms.technology: mde
ms.openlocfilehash: 931edcd890148a828a6d189722e8f29907c15b79
ms.sourcegitcommit: 3140e2866de36d57a27d27f70d47e8167c9cc907
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/23/2021
ms.locfileid: "60553691"
---
# <a name="onboard-non-persistent-virtual-desktop-infrastructure-vdi-devices-in-microsoft-365-defender"></a>영구적이지 않은 VDI(가상 데스크톱 인프라) 장치를 Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**적용 대상:**
- [엔드포인트용 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)
- VDI(가상 데스크톱 인프라) 장치
- Windows 10, Windows 11, Windows Server 2019, Windows Server 2022, Windows Server 2008R2/2012R2/2016

> Endpoint용 Defender를 경험하고 싶나요? [무료 평가판을 신청하세요.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-configvdi-abovefoldlink)

 > [!NOTE]
  > **영구 VDI**  -  [영구 VDI](configure-endpoints.md) 머신을 Microsoft Defender for Endpoint에 온보딩하는 것은 데스크톱 또는 노트북과 같은 실제 컴퓨터 온보딩과 동일한 방식으로 처리됩니다. 그룹 정책, Microsoft Endpoint Manager 및 기타 메서드를 사용하여 영구 컴퓨터 온보드할 수 있습니다. 보안 센터에서( 온보더링에서 기본 설정 온보더링 방법을 선택하고 해당 유형에 대한 https://security.microsoft.com) 지침을 따릅니다. 

## <a name="onboarding-non-persistent-virtual-desktop-infrastructure-vdi-devices"></a>비영구 가상 데스크톱 인프라(VDI) 장치 온보드

Endpoint용 Defender는 비영구 VDI 세션 온보딩을 지원합니다.

VIS를 온보드할 때 관련 문제가 있을 수 있습니다. 이 시나리오의 일반적인 문제는 다음과 같습니다.

- 실제 프로비전 전에 Endpoint용 Defender에 온보딩해야 하는 짧은 세션의 즉각적인 초기 온보딩.
- 일반적으로 장치 이름은 새 세션에 다시 사용합니다.

VDI 장치는 Endpoint 포털용 Defender에 다음 중 하나와 같은 표시될 수 있습니다.

- 각 디바이스에 대한 단일 항목입니다.

  > [!NOTE]
  > 이 경우 세션을 만들 때(예: 무인 응답 파일 사용) 동일한 장치 이름을 구성해야 합니다. 

- 각 디바이스에 대한 여러 항목( 각 세션에 대해 하나씩)

다음 단계에서는 VDI 장치를 등록하는 단계를 안내하고 단일 항목과 여러 항목에 대한 단계를 강조합니다.

> [!WARNING]
> 리소스 구성이 낮은 환경에서는 VDI 부팅 절차로 끝점 센서의 Defender 온보딩 속도가 느려질 수 있습니다.

### <a name="for-windows-10-or-windows-11-or-windows-server-2019-or-windows-server-2022"></a>Windows 10 또는 Windows 11 또는 Windows Server 2019 또는 Windows Server 2022의 경우

1.  서비스 온보더링 마법사에서 .zip 다운로드한 *VDI* 구성 패키지 파일(WindowsDefenderATPOnboardingPackage.zip)을 열 수 있습니다. 다음 포털에서 패키지를 [Microsoft 365 Defender 있습니다.](https://security.microsoft.com/)

    1. 탐색 창에서 **끝점 설정**  >  **관리**  >    >  **온보더링** 을 선택합니다.

    1. 운영 체제를 선택합니다.

    1.  배포 **방법 필드에서** 비영구 끝점에 **대한 VDI 온보딩 스크립트를 선택합니다.**

    1. 패키지 **다운로드를** 클릭하고 파일 .zip 저장합니다.

2. .zip 파일에서 추출한 WindowsDefenderATPOnboardingPackage 폴더의 파일을 경로 아래에 있는 골든/마스터 이미지로 `C:\WINDOWS\System32\GroupPolicy\Machine\Scripts\Startup` 복사합니다. 

2. .zip 파일에서 추출한 WindowsDefenderATPOnboardingPackage 폴더의 파일을 경로 아래에 있는 골든/마스터 이미지로 `C:\WINDOWS\System32\GroupPolicy\Machine\Scripts\Startup` 복사합니다.
    1. 각 디바이스에 대해 여러 항목을 구현하는 경우 각 세션에 대해 하나씩 WindowsDefenderATPOnboardingScript.cmd를 복사합니다.
    2. 각 장치에 대해 단일 항목을 구현하는 경우 Onboard-NonPersistentMachine.ps1 및 WindowsDefenderATPOnboardingScript.cmd를 모두 복사합니다.

    > [!NOTE]
    > 폴더가 없는 경우 `C:\WINDOWS\System32\GroupPolicy\Machine\Scripts\Startup` 숨겨져 있을 수 있습니다. 파일 탐색기에서 숨겨진 파일 및 **폴더 표시** 옵션을 선택해야 합니다.

3. 로컬 그룹 정책 편집기 창을 열고 컴퓨터 **구성** Windows 설정 \>  \>  \> **시작으로 이동합니다.**

   > [!NOTE]
   > 도메인 그룹 정책은 비영구적 VDI 장치를 온보드하는 데도 사용할 수 있습니다.

4. 구현할 메서드에 따라 적절한 단계를 수행합니다.
    - 각 디바이스에 대한 단일 항목:

         **PowerShell 스크립트 탭을** 선택한  다음 추가를 클릭합니다(Windows 탐색기가 앞에서 온보딩 스크립트를 복사한 경로에서 직접 열립니다). 온보딩 PowerShell 스크립트로 `Onboard-NonPersistentMachine.ps1` 이동합니다. 다른 파일은 자동으로 트리거되어 다른 파일을 지정할 필요가 없습니다.

    - 각 장치에 대한 여러 항목의 경우:

         스크립트 **탭을** 선택한 다음  추가를 클릭합니다(Windows 탐색기가 앞에서 온보딩 스크립트를 복사한 경로에서 직접 열립니다). 온보딩 bash 스크립트로 `WindowsDefenderATPOnboardingScript.cmd` 이동합니다.

5. 솔루션을 테스트합니다.
   1. 하나의 장치로 풀을 만들 수 있습니다.
   2. 장치에 로그온합니다.
   3. 장치에서 로그오프합니다.
   4. 다른 사용자와 함께 장치에 로그온합니다.
   5. 구현할 메서드에 따라 적절한 단계를 수행합니다.
      - 각 디바이스에 대한 단일 항목: 포털에서 하나의 Microsoft 365 Defender 확인합니다.
      - 각 디바이스에 대한 여러 항목에 대해: 포털에서 여러 Microsoft 365 Defender 확인합니다.

6. 탐색 **창에서** 장치 목록을 클릭합니다.

7. 장치 이름을 입력하고 검색 유형으로 **장치를** 선택하여 검색 기능을 사용합니다.

## <a name="for-downlevel-skus-windows-server-2008-r22012-r22016"></a>다운클래블 SKUS(Windows Server 2008 R2/2012 R2/2016)의 경우

> [!NOTE]
> 다음 레지스트리는 '각 장치에 대한 단일 항목'을 달성하는 것이 목표인 경우만 관련이 있습니다.

1. 레지스트리 값을 다음으로 설정

    ```console
   [HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection\DeviceTagging]
    "VDI"="NonPersistent"
    ```

    또는 명령줄 사용:

    ```console
    reg add "HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection\DeviceTagging" /v VDI /t REG_SZ /d "NonPersistent" /f
    ```

2. 서버 [온보더링 프로세스를 따르는 경우.](configure-server-endpoints.md) 

## <a name="updating-non-persistent-virtual-desktop-infrastructure-vdi-images"></a>비영구적 VDI(가상 데스크톱 인프라) 이미지 업데이트

최상의 방법은 오프라인 서비스 도구를 사용하여 골든/마스터 이미지를 패치하는 것이 좋습니다.

예를 들어 아래 명령을 사용하여 이미지가 오프라인 상태로 유지되는 동안 업데이트를 설치할 수 있습니다.

```console
DISM /Mount-image /ImageFile:"D:\Win10-1909.vhdx" /index:1 /MountDir:"C:\Temp\OfflineServicing"
DISM /Image:"C:\Temp\OfflineServicing" /Add-Package /Packagepath:"C:\temp\patch\windows10.0-kb4541338-x64.msu"
DISM /Unmount-Image /MountDir:"C:\Temp\OfflineServicing" /commit
```

DISM 명령 및 오프라인 서비스에 대한 자세한 내용은 아래 문서를 참조하세요.

- [DISM을 Windows 이미지 수정](/windows-hardware/manufacture/desktop/mount-and-modify-a-windows-image-using-dism)
- [DISM 이미지 관리 Command-Line 옵션](/windows-hardware/manufacture/desktop/dism-image-management-command-line-options-s14)
- [오프라인 저장소 이미지에서 구성 요소 저장소 Windows 줄이기](/windows-hardware/manufacture/desktop/reduce-the-size-of-the-component-store-in-an-offline-windows-image)

오프라인 서비스에서 비영구적 VDI 환경에 대한 사용 가능한 옵션이 아닌 경우 일관성 및 센서 상태 보장을 위해 다음 단계를 따라야 합니다.

1. 온라인 서비스 또는 패치에 대한 마스터 이미지를 부팅한 후 오프보딩 스크립트를 실행하여 Endpoint용 Defender 센서를 해제합니다. 자세한 내용은 [로컬 스크립트를 사용하여 장치 오프보드를 참조하세요.](configure-endpoints-script.md#offboard-devices-using-a-local-script)

2. CMD 창에서 아래 명령을 실행하여 센서가 중지되도록 합니다.

   ```console
   sc query sense
   ```

3. 필요한 경우 이미지를 서비스합니다.

4. 부팅 후 센서가 누적할 수 있는 사이버 폴더 콘텐츠를 정리하기 위해 다운로드할 수 있는 PsExec.exe 명령을 사용하여 다음 명령을 https://download.sysinternals.com/files/PSTools.zip) 실행합니다.

    ```console
    PsExec.exe -s cmd.exe
    cd "C:\ProgramData\Microsoft\Windows Defender Advanced Threat Protection\Cyber"
    del *.* /f /s /q
    REG DELETE "HKLM\SOFTWARE\Microsoft\Windows Advanced Threat Protection" /v senseGuid /f
    exit
    ```

5. 평소와 처럼 골든/마스터 이미지를 다시 비우는 것이 가장 까다로워질 수 있습니다.

## <a name="related-topics"></a>관련 항목
- [그룹 정책을 사용하여 Windows 장치 온보딩](configure-endpoints-gp.md)
- [Microsoft Endpoint Configuration Manager를 사용하여 Windows 컴퓨터 온보딩](configure-endpoints-sccm.md)
- [모바일 장치 관리 도구를 사용한 Windows 장치 온보딩](configure-endpoints-mdm.md)
- [로컬 스크립트를 사용하여 Windows 장치 온보딩](configure-endpoints-script.md)
- [끝점 온보딩 문제에 대한 Microsoft Defender 문제 해결](troubleshoot-onboarding.md)
