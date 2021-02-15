---
title: 모바일 장치 관리 도구를 사용하여 Windows 10 장치 온보딩
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
description: 모바일 장치 관리 도구를 사용하여 장치에 구성 패키지를 배포하여 서비스에 온보드됩니다.
ms.openlocfilehash: 1480c918589a1f00e00ceb1233e9a62887ccff32
ms.sourcegitcommit: 6647055154002c7d3b8f7ce25ad53c9636bc8066
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2020
ms.locfileid: "48769483"
---
# <a name="onboard-windows-10-devices-using-mobile-device-management-tools"></a>모바일 장치 관리 도구를 사용하여 Windows 10 장치 온보딩

**적용 대상:**

- [Microsoft 365 끝점 DLP(데이터 손실 방지)](/microsoft-365/compliance/endpoint-dlp-learn-about)

MDM(모바일 장치 관리) 솔루션을 사용하여 장치를 구성할 수 있습니다. Microsoft 365 끝점 데이터 손실 방지는 장치 관리 정책을 OMA-URIs 수 있는 정책을 제공하여 MDM을 지원합니다.


## <a name="before-you-begin"></a>시작하기 전에
Microsoft Intune을 사용하는 경우 MDM 등록 장치가 있어야 합니다. 그렇지 않으면 설정이 성공적으로 적용되지 않습니다. 

Microsoft Intune에서 MDM을 사용하도록 설정하는 데 대한 자세한 내용은 [장치 등록(Microsoft Intune)을 참조하세요.](https://docs.microsoft.com/mem/intune/enrollment/device-enrollment)

## <a name="onboard-devices-using-microsoft-intune"></a>Microsoft Intune을 사용하여 디바이스 온보드

[Intune의](https://docs.microsoft.com/intune/advanced-threat-protection)지침을 따릅니다.

> [!NOTE]
> - 등록된 **디바이스의 상태** 정책은 읽기 전용 속성을 사용하며 업데이트할 수 없습니다.

## <a name="offboard-and-monitor-devices-using-mobile-device-management-tools"></a>모바일 장치 관리 도구를 사용하여 디바이스 오프보드 및 모니터링

보안상의 이유로 장치의 오프보드에 사용된 패키지는 다운로드한 날짜 30일 후에 만료됩니다. 장치에 전송된 만료된 오프보더 패키지는 거부됩니다. 오프보더 패키지를 다운로드할 때 패키지 만료 날짜에 대한 알림을 하게 되고 패키지 이름에도 포함됩니다.

> [!NOTE]
> 온보드 및 오프보더 정책은 동일한 장치에 동시에 배포하면 안 됩니다. 그렇지 않으면 예측할 수 없는 충돌이 발생할 수 있습니다.

1. Microsoft 준수 센터에서 [오프보더 패키지를 다운로드합니다.](https://compliance.microsoft.com/)

2. 탐색 창에서 설정 장치  >  **온보더링 오프보더를**  >  **선택합니다.**

3. 배포 방법 **필드에서** 모바일 장치 **관리/Microsoft Intune을 선택합니다.**
    
4. 패키지 **다운로드를** 클릭하고 .zip 파일을 저장합니다.

5. 패키지를 배포할 네트워크 관리자가 액세스할 수 있는 공유 읽기 전용 위치에 .zip 파일의 내용을 추출합니다. 이름이 *DeviceCompliance_valid_until_YYYY-MM-DD.offboarding입니다.*

6. Microsoft Intune 사용자 지정 구성 정책을 사용하여 지원되는 다음 OMA-URI 설정을 배포합니다.

      OMA-URI: ./Device/Vendor/MSFT/WindowsAdvancedThreatProtection/Offboarding      
      날짜 유형: 문자열      
      값: [copy and paste the value from the content of the DeviceCompliance_valid_until_YYYY-MM-DD.offboarding file]

Microsoft Intune 정책 설정에 대한 자세한 내용은 [Microsoft Intune의 Windows 10 정책 설정을 참조하세요.](https://docs.microsoft.com/intune/deploy-use/windows-10-policy-settings-in-microsoft-intune)

> [!NOTE]
> 등록 **해제된 장치의 상태** 정책은 읽기 전용 속성을 사용하며 수정될 수 없습니다.

> [!IMPORTANT]
> 오프보더를 통해 디바이스가 포털로 센서 데이터 전송을 중지하지만, 디바이스의 모든 경고에 대한 참조를 포함하여 장치의 데이터는 최대 6개월 동안 보존됩니다.

## <a name="related-topics"></a>관련 항목
- [그룹 정책을 사용하여 Windows 10 장치 온보드](dlp-configure-endpoints-gp.md)
- [Microsoft Endpoint Configuration Manager를 사용하여 Windows 10 장치 온보드](dlp-configure-endpoints-sccm.md)
- [로컬 스크립트를 사용하여 Windows 10 장치 온보딩](dlp-configure-endpoints-script.md)
- [비영구 가상 데스크톱 인프라(VDI) 장치 온보딩](dlp-configure-endpoints-vdi.md)
- [Microsoft Defender Advanced Threat Protection 온보딩 문제 해결](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding)
