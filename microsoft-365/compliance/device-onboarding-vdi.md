---
title: 비영구 가상 데스크톱 인프라(VDI) 장치 온보딩
f1.keywords: NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.localizationpriority: medium
ms.collection:
- M365-security-compliance
search.appverid:
- MET150
description: VDI(가상 데스크톱 인프라) 장치에 구성 패키지를 배포하여 끝점 데이터 손실 방지 서비스에 Microsoft 365 배포합니다.
ms.openlocfilehash: 6ac13edde066319a5174234450dac67c29209b1b
ms.sourcegitcommit: 8eca41cd21280ffcb1f50cafce7a934e5544f302
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/12/2021
ms.locfileid: "60950885"
---
# <a name="onboard-non-persistent-virtual-desktop-infrastructure-devices"></a>비영구적 가상 데스크톱 인프라 장치 온보드

**적용 대상:**

- [Microsoft 365 DLP(데이터 손실 방지)](./endpoint-dlp-learn-about.md)
- [내부자 위험 관리](insider-risk-management.md#learn-about-insider-risk-management-in-microsoft-365)

- VDI(가상 데스크톱 인프라) 장치

> [!WARNING]
> Microsoft 365 가상 데스크톱에 대한 끝점 데이터 손실 Windows 지원에서는 단일 세션 시나리오를 지원합니다. 가상 데스크톱의 다중 세션 Windows 현재 지원되지 않습니다.

## <a name="onboard-vdi-devices"></a>VDI 장치 온보드

Microsoft 365 비영구 가상 데스크톱 인프라(VDI) 세션 온보더링을 지원합니다.

> [!NOTE]
> 비영구적 VDI 세션을 온보드하려면 VDI 장치가 1809 이상인 Windows 10 있어야 합니다.

VIS를 온보드할 때 관련 문제가 있을 수 있습니다. 이 시나리오의 일반적인 문제는 다음과 같습니다.

- 실제 프로비전 전에 세션에 온보드해야 하는 Microsoft 365 세션의 초기 온보드를 즉각적으로 진행합니다.
- 일반적으로 장치 이름은 새 세션에 다시 사용합니다.

VDI 장치는 다음 중 Microsoft 365 준수 센터에 표시될 수 있습니다.

- 각 디바이스에 대한 단일 항목입니다.
이 경우 세션을  만들 때(예: 무인 응답 파일 사용) 동일한 장치 이름을 구성해야 합니다.
- 각 디바이스에 대한 여러 항목( 각 세션에 대해 하나씩)

다음 단계에서는 VDI 장치를 등록하는 단계를 안내하고 단일 항목과 여러 항목에 대한 단계를 강조합니다.

> [!WARNING]
> 리소스 구성이 낮은 환경에서는 VDI 부팅 절차로 장치 온보더링 프로세스가 느려질 수 있습니다.

1. Microsoft 준수 센터에서 VDI .zip *파일(* [DeviceCompliancePackage.zip)을 다운로드합니다.](https://compliance.microsoft.com)

2. 탐색 창에서 장치 **온보 설정**  >  **를**  >  **선택합니다.**

3. 배포 **방법 필드에서** 비영구 끝점에 **대한 VDI 온보딩 스크립트를 선택합니다.**

4. 패키지 **다운로드를** 클릭하고 파일 .zip 저장합니다.

5. .zip 파일에서 추출한 DeviceCompliancePackage 폴더의 파일을 경로의 `golden/master` 이미지로 `C:\WINDOWS\System32\GroupPolicy\Machine\Scripts\Startup` 복사합니다.

6. 각 장치에 대해 단일 항목을 구현하지 않는 경우 DeviceComplianceOnboardingScript.cmd를 복사합니다.

7. 각 장치에 대해 단일 항목을 구현하는 경우 Onboard-NonPersistentMachine.ps1 및 DeviceComplianceOnboardingScript.cmd를 모두 복사합니다.

    > [!NOTE]
    > 폴더가 없는 경우 `C:\WINDOWS\System32\GroupPolicy\Machine\Scripts\Startup` 숨겨져 있을 수 있습니다. 파일 탐색기에서 숨겨진 파일 및 **폴더 표시** 옵션을 선택해야 합니다.

8. 로컬 그룹 정책 편집기 창을 열고 컴퓨터 **구성** Windows 설정  >    >    >  **시작으로 이동합니다.**

   > [!NOTE]
   > 도메인 그룹 정책은 비영구적 VDI 장치를 온보드하는 데도 사용할 수 있습니다.

9. 구현할 메서드에 따라 적절한 단계를 수행합니다.

   **각 장치에 대한 단일 항목의 경우**

   **PowerShell 스크립트 탭을** 선택한  다음 추가를 클릭합니다(Windows 탐색기가 앞에서 온보딩 스크립트를 복사한 경로에서 직접 열립니다). 온보딩 PowerShell 스크립트로 `Onboard-NonPersistentMachine.ps1` 이동합니다.

   **각 장치에 대한 여러 항목의 경우**:

   스크립트 **탭을** 선택한 다음  추가를 클릭합니다(Windows 탐색기가 앞에서 온보딩 스크립트를 복사한 경로에서 직접 열립니다). 온보딩 bash 스크립트로 `DeviceComplianceOnboardingScript.cmd` 이동합니다.

10. 솔루션을 테스트합니다.
    1. 하나의 장치로 풀을 만들 수 있습니다.
    1. 장치에 로그온합니다.
    1. 장치에서 로그프합니다.
    1. 다른 사용자와 함께 장치에 로그온합니다.
    1. **각 디바이스에 대한** 단일 항목: 각 디바이스에서 하나의 항목만 Microsoft Defender 보안 센터.
       **각 디바이스에 대한 여러 항목에 대해:** 각 디바이스에서 여러 Microsoft Defender 보안 센터.

11. 탐색 **창에서** 장치 목록을 클릭합니다.

12. 장치 이름을 입력하고 검색 유형으로 **장치를** 선택하여 검색 기능을 사용합니다.

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

1. 온라인 서비스 또는 패치에 대한 마스터 이미지를 부팅한 후 오프보딩 스크립트를 실행하여 Microsoft 365 장치 모니터링 센서를 해제합니다. 자세한 내용은 [로컬 스크립트를 사용하여 장치 오프보드를 참조하세요.](device-onboarding-script.md#offboard-devices-using-a-local-script)

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
    REG DELETE “HKLM\SOFTWARE\Microsoft\Windows Advanced Threat Protection" /v senseGuid /f
    exit
    ```

5. 평소처럼 골든/마스터 이미지를 다시 봉인합니다.

## <a name="related-topics"></a>관련 항목

- [그룹 정책을 Windows 10 Windows 11 장치 온보드 및 장치 관리](device-onboarding-gp.md)
- [Windows 10 Windows 10 및 Windows 11 장치 온보드 Microsoft Endpoint Configuration Manager](device-onboarding-sccm.md)
- [모바일 Windows 10 도구를 Windows 11 장치 온보드 및 장치 관리](device-onboarding-mdm.md)
- [로컬 스크립트를 Windows 10 Windows 11 및 장치 온보딩](device-onboarding-script.md)
- [Microsoft Defender Advanced Threat Protection 온보딩 문제 해결](/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding)
