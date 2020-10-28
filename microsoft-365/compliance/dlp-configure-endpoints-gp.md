---
title: 그룹 정책을 통한 Windows 10 장치 온보드
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
description: 그룹 정책을 사용 하 여 Windows 10 장치에 구성 패키지를 배포 하 여 서비스에 등록 되도록 합니다.
ms.openlocfilehash: a9e91f41b6e86e9f75d79d420c0ee830f1e3acf3
ms.sourcegitcommit: 6647055154002c7d3b8f7ce25ad53c9636bc8066
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2020
ms.locfileid: "48769448"
---
# <a name="onboard-windows-10-devices-using-group-policy"></a>그룹 정책을 사용 하는 온보드 Windows 10 장치 

**적용 대상:**

- [Microsoft 365 Endpoint data 손실 방지 (DLP)](/microsoft-365/compliance/endpoint-dlp-learn-about)
- 그룹 정책

> [!NOTE]
> GP (그룹 정책) 업데이트를 사용 하 여 패키지를 배포 하려면 Windows Server 2008 R2 이상 이어야 합니다.

> Windows Server 2019의 경우 NT AUTHORITY\Well-Known-System-Account를 그룹 정책 기본 설정에서 만드는 XML 파일의 NT 권한 서버를 교체 해야 할 수 있습니다.

## <a name="onboard-devices-using-group-policy"></a>그룹 정책을 사용 하는 온보드 장치

1. 서비스 온 보 딩 마법사에서 다운로드 한 GP 구성 패키지 .zip 파일 ( *DeviceComplianceOnboardingPackage.zip* )을 엽니다. [Microsoft 준수 센터](https://compliance.microsoft.com/compliancesettings/deviceonboarding) 에서 패키지를 가져올 수도 있습니다.

2. 탐색 창에서 **설정**  >  **장치 온 보 딩** 을 선택 합니다.

3. **배포 방법** 필드에서 **그룹 정책을** 선택 합니다.

4. **패키지 다운로드** 를 클릭 하 고 .zip 파일을 저장 합니다.

5. 장치에서 액세스할 수 있는 공유 읽기 전용 위치에 .zip 파일의 내용을 추출 합니다. *OptionalParamsPolicy* 라는 폴더와 파일 *Devicecompliancelocalonboardingscript .cmd* 가 있어야 합니다.

6. GPMC ( [그룹 정책 관리 콘솔](https://docs.microsoft.com/internet-explorer/ie11-deploy-guide/group-policy-and-group-policy-mgmt-console-ie11) )를 열고 구성 하려는 GPO (그룹 정책 개체)를 마우스 오른쪽 단추로 클릭 한 다음 **편집** 을 클릭 합니다.

7. **그룹 정책 관리 편집기** 에서 **컴퓨터 구성** , **기본 설정** , **제어판 설정** 으로 이동 합니다.

8. **예약 된 작업** 을 마우스 오른쪽 단추로 클릭 하 고 **새로 만들기** 를 가리킨 다음 **즉시 작업 (Windows 7 이상)** 을 클릭 합니다.

9. **작업** 창이 열리면 **일반** 탭으로 이동 합니다. **보안 옵션** 에서 **사용자 또는 그룹 변경을** 클릭 하 고 시스템을 입력 한 다음 **이름 확인** , **확인** 을 클릭 합니다. NT 권한 \은 작업을 실행할 사용자 계정으로 나타납니다.

10. **사용자의 로그온 여부에 관계 없이 실행** 을 선택 하 고 **가장 높은 수준의 권한으로 실행** 확인란을 클릭 합니다.

11. **작업** 탭으로 이동 하 여 **새로 만들기** ...를 클릭 합니다. **작업** 필드에서 **프로그램 시작** 을 선택 했는지 확인 합니다. 공유 *WindowsDefenderATPOnboardingScript* 파일의 파일 이름과 위치를 입력 합니다.

12. **확인** 을 클릭 하 고 열려 있는 GPMC 창을 닫습니다.


## <a name="offboard-devices-using-group-policy"></a>그룹 정책을 사용 하는 offboard 장치
보안상의 이유로, 보드 장치에 사용 된 패키지는 다운로드 한 날짜 로부터 30 일 후에 만료 됩니다. 만료 된 오프 보 딩 패키지가 장치로 전송 됩니다. 오프 보 딩 패키지를 다운로드할 때 패키지 만료 날짜에 대 한 알림을 받게 되며 패키지 이름에도 포함 됩니다.

> [!NOTE]
> 온 보 딩 및 오프 보 딩 정책은 동시에 같은 장치에 배포 해서는 안 되며 그렇지 않으면 예기치 않은 충돌이 발생 합니다.

1. [Microsoft 준수 센터](https://compliance.microsoft.com/compliancesettings/deviceonboarding)에서 오프 보 딩 패키지를 가져옵니다.

2. 탐색 창에서 **설정** /  >  **장치 온 보** 딩  >  **오프 보 딩** 을 선택 합니다.

3. **배포 방법** 필드에서 **그룹 정책을** 선택 합니다.

4. **패키지 다운로드** 를 클릭 하 고 .zip 파일을 저장 합니다.

5. 장치에서 액세스할 수 있는 공유 읽기 전용 위치에 .zip 파일의 내용을 추출 합니다. *DeviceComplianceOffboardingScript_valid_until_YYYY-MM-DD* 라는 파일이 있어야 합니다.

6. GPMC ( [그룹 정책 관리 콘솔](https://docs.microsoft.com/internet-explorer/ie11-deploy-guide/group-policy-and-group-policy-mgmt-console-ie11) )를 열고 구성 하려는 GPO (그룹 정책 개체)를 마우스 오른쪽 단추로 클릭 한 다음 **편집** 을 클릭 합니다.

7. **그룹 정책 관리 편집기** 에서 **컴퓨터 구성,** **기본 설정** , **제어판 설정** 으로 이동 합니다.

8. **예약 된 작업** 을 마우스 오른쪽 단추로 클릭 하 고 **새로 만들기** 를 가리킨 다음 **즉시 작업** 을 클릭 합니다.

9. **작업** 창이 열리면 **일반** 탭으로 이동 합니다. **보안 옵션** 아래에서 로컬 시스템 사용자 계정 (BUILTIN\SYSTEM)을 선택 합니다.

10. **사용자의 로그온 여부에 관계 없이 실행** 을 선택 하 고 **가장 높은 수준의 권한으로 실행** 확인란을 선택한 다음 확인을 클릭 합니다.

11. **작업** 탭으로 이동 하 여 **새로 만들기** ...를 클릭 합니다. **작업** 필드에서 **프로그램 시작** 을 선택 했는지 확인 합니다. 공유  *DeviceComplianceOffboardingScript_valid_until_YYYY-MM-DD* 파일의 파일 이름과 위치를 입력 합니다.

12. **확인** 을 클릭 하 고 열려 있는 GPMC 창을 닫습니다.

> [!IMPORTANT]
> 오프 보 딩을 통해 장치에서 포털에 센서 데이터를 전송 하는 것을 중지 하 고 장치의 데이터를 보낼 수 없게 됩니다.


## <a name="monitor-device-configuration"></a>장치 구성 모니터링
그룹 정책을 사용 하 여 장치에 대 한 정책 배포를 모니터링할 수 있는 옵션이 없습니다. 모니터링은 포털에서 직접 또는 다양 한 배포 도구를 사용 하 여 수행할 수 있습니다.

## <a name="monitor-devices-using-the-portal"></a>포털을 사용 하 여 장치 모니터링
1. [Microsoft 준수 센터로](https://compliance.microsoft.com/)이동 합니다.
2. **장치** 목록을 클릭 합니다.
3. 장치가 나타나는지 확인 합니다.

> [!NOTE]
> 장치 **목록** 에 장치가 표시 되는 데 며칠 정도 걸릴 수 있습니다. 여기에는 정책을 장치에 배포 하는 데 걸리는 시간, 사용자가 로그온 하기 전 까지의 시간, 끝점에서 보고를 시작 하는 데 걸리는 시간이 포함 됩니다.


## <a name="related-topics"></a>관련 항목
- [Microsoft Endpoint Configuration Manager를 사용 하는 Windows 10 장치 온보드](dlp-configure-endpoints-sccm.md)
- [모바일 장치 관리 도구를 사용 하는 온보드 Windows 10 장치](dlp-configure-endpoints-mdm.md)
- [로컬 스크립트를 사용 하는 온보드 Windows 10 장치](dlp-configure-endpoints-script.md)
- [온보드 VDI (가상 데스크톱 인프라) 장치 (비영구)](dlp-configure-endpoints-vdi.md)
- [새로 등록 Microsoft Defender ATP 장치에서 검색 테스트 실행](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/run-detection-test)
- [Microsoft Defender Advanced Threat Protection 온 보 딩 문제 해결](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding)
