---
title: 로컬 스크립트를 Windows 10 Windows 11 및 장치 온보딩
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
ms.custom: admindeeplinkCOMPLIANCE
search.appverid:
- MET150
description: 로컬 스크립트를 사용하여 장치에 구성 패키지를 배포하여 서비스에 온보딩합니다.
ms.openlocfilehash: 14412e782cffd597786a4d2c322fe2b8fc20e5ca
ms.sourcegitcommit: 8eca41cd21280ffcb1f50cafce7a934e5544f302
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/12/2021
ms.locfileid: "60950886"
---
# <a name="onboard-windows-10-and-windows-11-devices-using-a-local-script"></a>로컬 스크립트를 Windows 10 Windows 11 및 장치 온보딩

**적용 대상:**

- [Microsoft 365 DLP(데이터 손실 방지)](./endpoint-dlp-learn-about.md)
- [내부자 위험 관리](insider-risk-management.md#learn-about-insider-risk-management-in-microsoft-365)

개별 디바이스를 수동으로 온보드하여 온보드를 Microsoft 365. 네트워크의 모든 장치를 온보드하기 전에 서비스를 테스트할 때 이 작업을 먼저 수행해야 할 수 있습니다.

> [!IMPORTANT]
> 이 스크립트는 최대 10대의 장치에서 사용하기 위해 최적화되었습니다.
>
> 대규모로 배포하기 위해 다른 [배포 옵션을 사용하세요.](device-onboarding-overview.md) 예를 들어 그룹 정책을 사용하여 온보딩 스크립트를 온보딩 장치에서 사용할 수 있는 스크립트를 사용하여 프로덕션의 10개가 넘는 디바이스에 배포할 [Windows 10 있습니다.](device-onboarding-gp.md)

## <a name="onboard-devices"></a>온보딩 장치
 
1. Microsoft 규정 준수 센터에서 구성 패키지 .zip *파일(* DeviceComplianceOnboardingPackage.zip) [패키지 다운로드](https://compliance.microsoft.com)

2. 탐색 창에서 장치 <a href="https://go.microsoft.com/fwlink/p/?linkid=2174201" target="_blank">**설정**</a>  >  **를 선택합니다.**

3. 배포 **방법 필드에서** 로컬 스크립트 **를 선택합니다.**

4. 패키지 **다운로드를** 클릭하고 파일 .zip 저장합니다.
  
5. 온보더할 디바이스의 위치(예: 데스크톱)에 구성 패키지의 내용을 추출합니다. *이름이 DeviceOnboardingScript.cmd인 파일이 필요합니다.*

6. 디바이스에서 상승된 명령줄 프롬프트를 열고 스크립트를 실행합니다.

7. **시작**(으)로 이동하고 **cmd** 를 입력하십시오.

8. **명령 프롬프트** 을(를) 마우스 오른쪽 버튼으로 클릭하고 **관리자**(으)로 실행을 선택합니다.

    ![관리자 시작 메뉴 실행을 설정하는 창 창입니다.](../media/dlp-run-as-admin.png)

9. 스크립트 파일의 위치를 입력합니다. 바탕 화면에 파일을 복사한 경우 *%userprofile%\Desktop\WindowsDefenderATPOnboardingScript.cmd를 입력합니다.*

10. Enter 키를 **누르거나** 확인을 **클릭합니다.**

디바이스가 규격 및 센서 데이터를 올바르게 보고하는지 수동으로 확인할 수 있는 방법에 대한 자세한 내용은 [Microsoft Defender Advanced Threat Protection 온보딩](/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding)문제 해결을 참조하세요.

## <a name="offboard-devices-using-a-local-script"></a>로컬 스크립트를 사용하여 디바이스 오프보딩

보안상의 이유로, 오프보드 장치에 사용된 패키지는 다운로드한 날짜 30일 후에 만료됩니다. 장치로 전송된 만료된 오프보더 패키지는 거부됩니다. 오프보더 패키지를 다운로드할 때 패키지 만료 날짜에 대한 알림을 하게 되고 패키지 이름에도 포함됩니다.

> [!NOTE]
> 온보드 및 오프보더 정책을 동일한 장치에 동시에 배포하면 안 됩니다. 그렇지 않으면 예측할 수 없는 충돌이 발생할 수 있습니다.

1. 에서 오프보더 <a href="https://go.microsoft.com/fwlink/p/?linkid=2077149" target="_blank">패키지를 Microsoft 365 규정 준수 센터.</a>

2. 탐색 창에서 장치 <a href="https://go.microsoft.com/fwlink/p/?linkid=2174201" target="_blank">**설정**</a>  >  **를 선택합니다.**

3. 배포 **방법 필드에서** 로컬 스크립트 **를 선택합니다.**

4. 패키지 **다운로드를** 클릭하고 파일 .zip 저장합니다.

5. 디바이스에서 액세스할 수 .zip 읽기 전용 공유 위치로 파일 콘텐츠의 추출 이름이 *DeviceComplianceOffboardingScript_valid_until_YYYY-MM-DD.cmd 입니다.*

6. 디바이스에서 상승된 명령줄 프롬프트를 열고 스크립트를 실행합니다.

7. **시작**(으)로 이동하고 **cmd** 를 입력하십시오.

8. **명령 프롬프트** 을(를) 마우스 오른쪽 버튼으로 클릭하고 **관리자**(으)로 실행을 선택합니다.

    ![관리자 시작 메뉴 실행을 설정하는 창 창입니다.](../media/dlp-run-as-admin.png)

9. 스크립트 파일의 위치를 입력합니다. 바탕 화면에 파일을 복사한 경우 *%userprofile%\Desktop\WindowsDefenderATPOffboardingScript_valid_until_YYYY-MM-DD.cmd를 입력합니다.*

10. Enter 키를 **누르거나** 확인을 **클릭합니다.**

> [!IMPORTANT]
> 오프보더링을 통해 디바이스가 포털에 센서 데이터 전송을 중지합니다.

## <a name="monitor-device-configuration"></a>장치 구성 모니터링

[온보딩 문제 해결](/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding)의 다양한 확인 단계를 수행하여 스크립트가 성공적으로 완료되고 에이전트가 실행되고 있는지 확인할 수 있습니다.

모니터링은 포털에서 직접 수행하거나 다른 배포 도구를 사용하여 수행될 수도 있습니다.

### <a name="monitor-devices-using-the-portal"></a>포털을 사용하여 장치 모니터링

1. 준수 [Microsoft 365 로 이동합니다.](https://compliance.microsoft.com)

2. 장치 **설정**  >  **장치를**  >  **선택하세요.**

1. 장치 Microsoft 365 규정 준수 센터 이동하고 장치 <a href="https://go.microsoft.com/fwlink/p/?linkid=2174201" target="_blank">**온보**</a>설정  >  **선택합니다.**  >  

1. 장치가 나타나는지 확인

## <a name="related-topics"></a>관련 항목
- [그룹 정책을 Windows 10 Windows 11 장치 온보드 및 장치 관리](device-onboarding-gp.md)
- [Windows 10 Windows 10 및 Windows 11 장치 온보드 Microsoft Endpoint Configuration Manager](device-onboarding-sccm.md)
- [모바일 Windows 10 도구를 Windows 11 장치 온보드 및 장치 관리](device-onboarding-mdm.md)
- [비영구 VDI(가상 데스크톱 인프라) 장치 온보딩](device-onboarding-vdi.md)
- [새로 온보딩된 엔드포인트 디바이스용 Microsoft Defender에서 검색 테스트 실행](/windows/security/threat-protection/microsoft-defender-atp/run-detection-test)
- [Microsoft Defender Advanced Threat Protection 온보딩 문제 해결](/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding)