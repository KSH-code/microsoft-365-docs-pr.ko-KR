---
title: 로컬 스크립트를 사용 하는 온보드 Windows 10 장치
f1.keywords: NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
search.appverid:
- MET150
description: 로컬 스크립트를 사용 하 여 장치에 구성 패키지를 배포 하 여 서비스에 등록 합니다.
ms.openlocfilehash: 74152f9488623d39e32ee4e47a452bd1daea28c7
ms.sourcegitcommit: 6647055154002c7d3b8f7ce25ad53c9636bc8066
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2020
ms.locfileid: "48769473"
---
# <a name="onboard-windows-10-devices-using-a-local-script"></a>로컬 스크립트를 사용 하는 온보드 Windows 10 장치

**적용 대상:**

- [Microsoft 365 Endpoint data 손실 방지 (DLP)](/microsoft-365/compliance/endpoint-dlp-learn-about)

또한 개별 장치를 수동으로 Microsoft 365 끝점 데이터 손실 방지 기능에 등록할 수도 있습니다. 네트워크의 모든 장치에 대 한 온 보 딩을 커밋 하기 전에 서비스를 테스트할 때 먼저이 작업을 수행 해야 할 수 있습니다.

> [!IMPORTANT]
> 이 스크립트는 최대 10 개의 장치에서 사용 하도록 최적화 되었습니다.
>
> 확장 하 여 배포 하려면 [기타 배포 옵션](dlp-configure-endpoints.md)을 사용 합니다. 예를 들어 [그룹 정책을 사용 하 여 온보드 Windows 10 장치](dlp-configure-endpoints-gp.md)에서 사용 가능한 스크립트를 사용 하 여 프로덕션에서 10 개 보다 많은 장치에 온 보 딩 스크립트를 배포할 수 있습니다.

## <a name="onboard-devices"></a>온보드 장치
 
1.  서비스 온 보 딩 마법사에서 다운로드 한 GP 구성 패키지 .zip 파일 ( *DeviceComplianceOnboardingPackage.zip* )을 엽니다. [Microsoft 준수 센터](https://compliance.microsoft.com) 에서 패키지를 가져올 수도 있습니다.

2. 탐색 창에서 **설정**  >  **장치 온 보 딩** 을 선택 합니다.

3. **배포 방법** 필드에서 **로컬 스크립트** 를 선택 합니다.

4. **패키지 다운로드** 를 클릭 하 고 .zip 파일을 저장 합니다.
  
5. 구성 패키지의 콘텐츠를 온보드 장치 (예: 데스크톱)의 위치로 추출 합니다. *Deviceonboardingscript* 라는 파일이 있어야 합니다.

6.  장치에서 관리자 권한 명령줄 프롬프트를 열고 스크립트를 실행 합니다.

7.  **시작** 으로 이동 하 여 **cmd** 를 입력 합니다.

8.  **명령 프롬프트** 를 마우스 오른쪽 단추로 클릭 하 고 **관리자 권한으로 실행** 을 선택 합니다.

![관리자 권한으로 실행을 가리키는 창 시작 메뉴](../media/dlp-run-as-admin.png)

9.  스크립트 파일의 위치를 입력 합니다. 파일을 데스크톱에 복사한 경우 다음을 입력 합니다. *%userprofile%\Desktop\WindowsDefenderATPOnboardingScript.cmd*

10.  **Enter** 키를 누르거나 **확인을** 클릭 합니다.

장치가 호환 되는지 올바르게 보고 하는 방법에 대 한 자세한 내용은 [Microsoft Defender Advanced Threat Protection 온 보 딩 문제](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding)를 참조 하세요.

## <a name="offboard-devices-using-a-local-script"></a>로컬 스크립트를 사용 하는 offboard 장치
보안상의 이유로, 보드 장치에 사용 된 패키지는 다운로드 한 날짜 로부터 30 일 후에 만료 됩니다. 만료 된 오프 보 딩 패키지가 장치로 전송 거부 됩니다. 오프 보 딩 패키지를 다운로드할 때 패키지 만료 날짜에 대 한 알림을 받게 되며 패키지 이름에도 포함 됩니다.

> [!NOTE]
> 온 보 딩 및 오프 보 딩 정책은 동시에 같은 장치에 배포 해서는 안 되며 그렇지 않으면 예기치 않은 충돌이 발생 합니다.

1. [Microsoft 준수 센터](https://compliance.microsoft.com) 에서 오프 보 딩 패키지 가져오기

2. 탐색 창에서 **설정**  >  **장치 오프 보 딩** 을 선택 합니다.

3. **배포 방법** 필드에서 **로컬 스크립트** 를 선택 합니다.

4. **패키지 다운로드** 를 클릭 하 고 .zip 파일을 저장 합니다.

5. 장치에서 액세스할 수 있는 공유 읽기 전용 위치에 .zip 파일의 내용을 추출 합니다. *DeviceComplianceOffboardingScript_valid_until_YYYY-MM-DD* 라는 파일이 있어야 합니다.

6.  장치에서 관리자 권한 명령줄 프롬프트를 열고 스크립트를 실행 합니다.

7.  **시작** 으로 이동 하 여 **cmd** 를 입력 합니다.

8.  **명령 프롬프트** 를 마우스 오른쪽 단추로 클릭 하 고 **관리자 권한으로 실행** 을 선택 합니다.

![관리자 권한으로 실행을 가리키는 창 시작 메뉴](../media/dlp-run-as-admin.png)

9.  스크립트 파일의 위치를 입력 합니다. 파일을 데스크톱에 복사한 경우에는 *%userprofile%\desktop\ WindowsDefenderATPOffboardingScript_valid_until_YYYY-MM-DD를 입력 합니다.*

10.  **Enter** 키를 누르거나 **확인을** 클릭 합니다.

> [!IMPORTANT]
> 오프 보 딩 장치에서 포털에 대 한 센서 데이터 전송을 중지 합니다.


## <a name="monitor-device-configuration"></a>장치 구성 모니터링
[온 보 딩 문제 해결]의 다양 한 확인 단계를 수행 하 여 https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding) 스크립트가 정상적으로 완료 되 고 에이전트가 실행 되 고 있는지 확인할 수 있습니다.

모니터링은 포털에서 직접 또는 다양 한 배포 도구를 사용 하 여 수행할 수도 있습니다.

### <a name="monitor-devices-using-the-portal"></a>포털을 사용 하 여 장치 모니터링
1. [Microsoft 365 준수 센터로](https://compliance.microsoft.com)이동 합니다.

2. **설정**  >  **장치 온 보 딩**  >  **장치** 를 선택 합니다.

3. 장치가 나타나는지 확인 합니다.


## <a name="related-topics"></a>관련 항목
- [그룹 정책을 사용 하는 온보드 Windows 10 장치](dlp-configure-endpoints-gp.md)
- [Microsoft Endpoint Configuration Manager를 사용 하는 Windows 10 장치 온보드](dlp-configure-endpoints-sccm.md)
- [모바일 장치 관리 도구를 사용 하는 온보드 Windows 10 장치](dlp-configure-endpoints-mdm.md)
- [온보드 VDI (가상 데스크톱 인프라) 장치 (비영구)](dlp-configure-endpoints-vdi.md)
- [새로 등록 Microsoft Defender ATP 장치에서 검색 테스트 실행](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/run-detection-test)
- [Microsoft Defender Advanced Threat Protection 온 보 딩 문제 해결](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding)
