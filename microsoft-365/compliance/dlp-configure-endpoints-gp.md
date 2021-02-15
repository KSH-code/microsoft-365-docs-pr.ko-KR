---
title: 그룹 정책을 통한 Windows 10 장치 온보딩
f1.keywords: NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
search.appverid:
- MET150
description: 그룹 정책을 사용하여 Windows 10 장치에 구성 패키지를 배포하여 서비스에 온보드됩니다.
ms.openlocfilehash: a9e91f41b6e86e9f75d79d420c0ee830f1e3acf3
ms.sourcegitcommit: 6647055154002c7d3b8f7ce25ad53c9636bc8066
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2020
ms.locfileid: "48769448"
---
# <a name="onboard-windows-10-devices-using-group-policy"></a>그룹 정책을 사용하여 Windows 10 장치 온보드 

**적용 대상:**

- [Microsoft 365 끝점 DLP(데이터 손실 방지)](/microsoft-365/compliance/endpoint-dlp-learn-about)
- 그룹 정책

> [!NOTE]
> GP(그룹 정책) 업데이트를 사용하여 패키지를 배포하려면 Windows Server 2008 R2 이상에 있어야 합니다.

> Windows Server 2019의 경우 그룹 정책 기본 설정에서 만드는 XML 파일의 NT AUTHORITY\Well-Known-System-Account를 NT AUTHORITY\SYSTEM으로 대체해야 할 수 있습니다.

## <a name="onboard-devices-using-group-policy"></a>그룹 정책을 사용하여 디바이스 온보드

1. 서비스 온보더링 마법사에서 *다운로드한* GP 구성 패키지 .zip 파일(DeviceComplianceOnboardingPackage.zip)을 니다. Microsoft 준수 센터에서 [패키지를 다운로드할 수 있습니다.](https://compliance.microsoft.com/compliancesettings/deviceonboarding)

2. 탐색 창에서 설정 **장치**  >  **온보더링을 선택합니다.**

3. 배포 방법 **필드에서** 그룹 **정책을 선택합니다.**

4. 패키지 **다운로드를 클릭하고** .zip 파일을 저장합니다.

5. .zip 파일의 내용을 장치에서 액세스할 수 있는 읽기 전용 공유 위치로 추출합니다. *OptionalParamsPolicy라는* 폴더와 *DeviceComplianceLocalOnboardingScript.cmd* 파일이 필요합니다.

6. GPMC(그룹 정책 관리 콘솔)를 열고 구성할 GPO(그룹 정책 개체)를 마우스 오른쪽 단추로 클릭하고 편집을 **클릭합니다.** [](https://docs.microsoft.com/internet-explorer/ie11-deploy-guide/group-policy-and-group-policy-mgmt-console-ie11)

7. 그룹 정책 **관리 편집기에서** 컴퓨터 **구성으로** 이동한 다음 기본 설정으로 **이동한** 다음 **제어판 설정으로 이동합니다.**

8. 예약된 **작업을 마우스 오른쪽** 단추로 클릭하고 새로 고침을 클릭한 다음 직접 실행 작업(Windows **7 이상)을 클릭합니다.**

9. 작업 **창이** 열리면 일반 **탭으로** 이동하십시오. 보안 **옵션에서** 사용자 또는 그룹 **변경을** 클릭하고 SYSTEM을 입력한 다음 이름 **확인을** 클릭한 다음 **확인을 클릭합니다.** NT AUTHORITY\SYSTEM은 작업이 실행될 사용자 계정으로 표시됩니다.

10. 사용자가 **로그온되어** 있는지 여부에 따라 실행을 선택하고 가장 높은 권한으로 실행 **확인란을** 선택합니다.

11. 작업 **탭으로** 이동하여 새로 **고치기...** 작업 **필드에서 프로그램** **시작이 선택되어 있도록** 합니다. 공유 *WindowsDefenderATPOnboardingScript.cmd* 파일의 파일 이름과 위치를 입력합니다.

12. 확인을 **클릭하고** 열려 있는 GPMC 창을 닫습니다.


## <a name="offboard-devices-using-group-policy"></a>그룹 정책을 사용하여 디바이스 오프보드
보안상의 이유로 장치의 오프보드에 사용된 패키지는 다운로드한 날짜 30일 후에 만료됩니다. 장치에 전송된 만료된 오프보더 패키지는 거부됩니다. 오프보더 패키지를 다운로드할 때 패키지 만료 날짜에 대한 알림을 하게 되고 패키지 이름에도 포함됩니다.

> [!NOTE]
> 온보드 및 오프보더 정책은 동일한 장치에 동시에 배포하면 안 됩니다. 그렇지 않으면 예측할 수 없는 충돌이 발생할 수 있습니다.

1. Microsoft 준수 센터에서 [오프보더 패키지를 다운로드합니다.](https://compliance.microsoft.com/compliancesettings/deviceonboarding)

2. 탐색 창에서 설정   >  **//장치 온보더링**  >  **오프보더를 선택합니다.**

3. 배포 방법 **필드에서** 그룹 **정책을 선택합니다.**

4. 패키지 **다운로드를 클릭하고** .zip 파일을 저장합니다.

5. .zip 파일의 내용을 장치에서 액세스할 수 있는 읽기 전용 공유 위치로 추출합니다. 이름이 *DeviceComplianceOffboardingScript_valid_until_YYYY-MM-DD.cmd입니다.*

6. GPMC(그룹 정책 관리 콘솔)를 열고 구성할 GPO(그룹 정책 개체)를 마우스 오른쪽 단추로 클릭하고 편집을 **클릭합니다.** [](https://docs.microsoft.com/internet-explorer/ie11-deploy-guide/group-policy-and-group-policy-mgmt-console-ie11)

7. 그룹 정책 관리 **편집기에서** 컴퓨터  **구성,** 기본 설정, 제어판 **설정으로 이동합니다.**

8. 예약된 **작업을 마우스 오른쪽 단추로 클릭하고** 새로 고치고 **직접 실행 작업을 클릭합니다.** 

9. 작업 **창이** 열리면 일반 **탭으로** 이동하십시오. 보안 옵션에서 로컬 시스템 사용자 계정(BUILTIN\SYSTEM)을 **선택합니다.**

10. 사용자가 **로그온되어** 있는지 여부에 따라 실행을 선택하고 가장 높은 권한으로 실행 **확인란을** 선택합니다.

11. 작업 **탭으로** 이동하여 새로 **고치기... 를 클릭합니다.** 작업 **필드에서 프로그램** **시작이 선택되어 있도록** 합니다. 공유  *DeviceComplianceOffboardingScript_valid_until_YYYY-MM-DD.cmd* 파일의 파일 이름과 위치를 입력합니다.

12. 확인을 **클릭하고** 열려 있는 GPMC 창을 닫습니다.

> [!IMPORTANT]
> 오프보더를 통해 디바이스는 포털에 센서 데이터 전송을 중지하지만 장치의 데이터는 전송하지 않습니다.


## <a name="monitor-device-configuration"></a>장치 구성 모니터링
그룹 정책을 사용하는 경우 디바이스에서 정책 배포를 모니터링할 수 있는 옵션이 없습니다. 모니터링은 포털에서 직접 수행하거나 다른 배포 도구를 사용하여 수행될 수 있습니다.

## <a name="monitor-devices-using-the-portal"></a>포털을 사용하여 장치 모니터링
1. Microsoft 준수 [센터로 이동](https://compliance.microsoft.com/)
2. 장치 **목록을** 클릭합니다.
3. 장치가 나타나는지 확인

> [!NOTE]
> 디바이스 목록에 디바이스가 표시하기 시작하는 데 며칠이 **걸릴 수 있습니다.** 여기에는 정책이 장치에 배포되는 데 걸리는 시간, 사용자가 로그온하는 데 걸리는 시간 및 끝점에서 보고를 시작하는 데 걸리는 시간이 포함됩니다.


## <a name="related-topics"></a>관련 항목
- [Microsoft Endpoint Configuration Manager를 사용하여 Windows 10 장치 온보드](dlp-configure-endpoints-sccm.md)
- [모바일 장치 관리 도구를 사용하여 Windows 10 장치 온보딩](dlp-configure-endpoints-mdm.md)
- [로컬 스크립트를 사용하여 Windows 10 장치 온보딩](dlp-configure-endpoints-script.md)
- [비영구 가상 데스크톱 인프라(VDI) 장치 온보딩](dlp-configure-endpoints-vdi.md)
- [새로 온보딩된 Microsoft Defender ATP 장치에서 검색 테스트 실행](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/run-detection-test)
- [Microsoft Defender Advanced Threat Protection 온보딩 문제 해결](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding)
