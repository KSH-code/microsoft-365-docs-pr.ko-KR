---
title: 모바일 장치 관리 도구를 사용 하는 온보드 Windows 10 장치
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
description: 모바일 장치 관리 도구를 사용 하 여 장치에 구성 패키지를 배포 하 여 서비스에 등록 되도록 합니다.
ms.openlocfilehash: 1480c918589a1f00e00ceb1233e9a62887ccff32
ms.sourcegitcommit: 6647055154002c7d3b8f7ce25ad53c9636bc8066
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2020
ms.locfileid: "48769483"
---
# <a name="onboard-windows-10-devices-using-mobile-device-management-tools"></a>모바일 장치 관리 도구를 사용 하는 온보드 Windows 10 장치

**적용 대상:**

- [Microsoft 365 Endpoint data 손실 방지 (DLP)](/microsoft-365/compliance/endpoint-dlp-learn-about)

MDM (모바일 장치 관리) 솔루션을 사용 하 여 장치를 구성할 수 있습니다. Microsoft 365 Endpoint data 손실 방지는 장치를 관리 하기 위한 정책을 만들기 위해 OMA-URIs 제공 하 여 MDMs를 지원 합니다.


## <a name="before-you-begin"></a>시작하기 전에
Microsoft Intune을 사용 하는 경우에는 장치 MDM이 등록 되어 있어야 합니다. 그렇지 않으면 설정이 제대로 적용 되지 않습니다. 

Microsoft Intune에서 MDM을 사용 하도록 설정 하는 방법에 대 한 자세한 내용은 [Device 등록할 (Microsoft intune)](https://docs.microsoft.com/mem/intune/enrollment/device-enrollment)을 참조 하세요.

## <a name="onboard-devices-using-microsoft-intune"></a>Microsoft Intune을 사용 하는 온보드 장치

[Intune](https://docs.microsoft.com/intune/advanced-threat-protection)의 지침을 따릅니다.

> [!NOTE]
> - **등록 장치 정책에 대 한** 상태는 읽기 전용 속성을 사용 하며 수정할 수 없습니다.

## <a name="offboard-and-monitor-devices-using-mobile-device-management-tools"></a>모바일 장치 관리 도구를 사용 하는 offboard and monitor devices

보안상의 이유로, 보드 장치에 사용 된 패키지는 다운로드 한 날짜 로부터 30 일 후에 만료 됩니다. 만료 된 오프 보 딩 패키지가 장치로 전송 됩니다. 오프 보 딩 패키지를 다운로드할 때 패키지 만료 날짜에 대 한 알림을 받게 되며 패키지 이름에도 포함 됩니다.

> [!NOTE]
> 온 보 딩 및 오프 보 딩 정책은 동시에 같은 장치에 배포 해서는 안 되며 그렇지 않으면 예기치 않은 충돌이 발생 합니다.

1. [Microsoft 준수 센터](https://compliance.microsoft.com/)에서 오프 보 딩 패키지를 가져옵니다.

2. 탐색 창에서 **설정**  >  **장치 온 보** 딩을 선택  >  **Offboarding** 합니다.

3. **배포 방법** 필드에서 **모바일 장치 관리/Microsoft Intune** 을 선택 합니다.
    
4. **패키지 다운로드** 를 클릭 하 고 .zip 파일을 저장 합니다.

5. 패키지를 배포할 네트워크 관리자가 액세스할 수 있는 공유, 읽기 전용 위치에 .zip 파일의 내용을 추출 합니다. DeviceCompliance_valid_until_YYYY에는 *-yyyy-mm-dd* 라는 파일이 있어야 합니다.

6. Microsoft Intune 사용자 지정 구성 정책을 사용 하 여 지원 되는 다음 OMA URI 설정을 배포 합니다.

      OMA-URI:./Device/Vendor/MSFT/WindowsAdvancedThreatProtection/Offboarding      
      날짜 형식: 문자열      
      값: [DeviceCompliance_valid_until_YYYY-YYYY-MM-DD 파일의 내용에서 값을 복사 하 여 붙여 넣습니다.]

Microsoft Intune 정책 설정에 대 한 자세한 내용은 [Microsoft intune에서 Windows 10 정책 설정을](https://docs.microsoft.com/intune/deploy-use/windows-10-policy-settings-in-microsoft-intune)참조 하세요.

> [!NOTE]
> **Offboarded 장치 정책에 대 한** 상태는 읽기 전용 속성을 사용 하며 수정할 수 없습니다.

> [!IMPORTANT]
> 오프 보 딩은 장치에서 포털에 센서 데이터를 전송 하지 않고 장치에서 가져온 데이터에 대 한 참조를 포함 하 여 최대 6 개월 동안 보존 되도록 합니다.

## <a name="related-topics"></a>관련 항목
- [그룹 정책을 사용 하는 온보드 Windows 10 장치](dlp-configure-endpoints-gp.md)
- [Microsoft Endpoint Configuration Manager를 사용 하는 Windows 10 장치 온보드](dlp-configure-endpoints-sccm.md)
- [로컬 스크립트를 사용 하는 온보드 Windows 10 장치](dlp-configure-endpoints-script.md)
- [온보드 VDI (가상 데스크톱 인프라) 장치 (비영구)](dlp-configure-endpoints-vdi.md)
- [Microsoft Defender Advanced Threat Protection 온 보 딩 문제 해결](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding)
