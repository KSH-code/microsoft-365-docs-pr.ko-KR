---
title: 모바일 장치 관리 도구를 사용하여 Windows 10 장치 온보딩
description: 모바일 장치 관리 도구를 사용하여 장치에 구성 패키지를 배포하여 서비스에 온보드합니다.
keywords: mdm을 사용하여 장치 온보딩, 장치 관리, Windows ATP 장치 온보딩, 끝점 장치용 Microsoft Defender 온보딩, mdm
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 85dd6b50280f54b9d39bbb134e466171fc6268ff
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2021
ms.locfileid: "51166152"
---
# <a name="onboard-windows-10-devices-using-mobile-device-management-tools"></a>모바일 장치 관리 도구를 사용하여 Windows 10 장치 온보딩

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**적용 대상:**
- [엔드포인트용 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>Endpoint용 Defender를 경험하고 싶나요? [무료 평가판에 등록합니다.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-configureendpointsmdm-abovefoldlink)

MDM(모바일 장치 관리) 솔루션을 사용하여 장치를 구성할 수 있습니다. Endpoint용 Defender는 장치 관리 정책을 만들 수 있는 OMA-URIs MDM을 지원합니다.

Endpoint CSP용 Defender 사용에 대한 자세한 내용은 [WindowsAdvancedThreatProtection CSP](https://msdn.microsoft.com/library/windows/hardware/mt723296(v=vs.85).aspx) 및 [WindowsAdvancedThreatProtection DDF 파일](https://msdn.microsoft.com/library/windows/hardware/mt723297(v=vs.85).aspx)을 참조하세요.

## <a name="before-you-begin"></a>시작하기 전에
Microsoft Intune을 사용하는 경우 디바이스 MDM이 등록되어야 합니다. 그렇지 않으면 설정이 적용되지 않습니다. 

Microsoft Intune에서 MDM을 사용하도록 설정하는 데 대한 자세한 내용은 [장치 등록(Microsoft Intune)을 참조하세요.](https://docs.microsoft.com/mem/intune/enrollment/device-enrollment)

## <a name="onboard-devices-using-microsoft-intune"></a>Microsoft Intune을 사용하여 장치 온보드

[![Microsoft Intune을 사용하여 끝점용 Defender에 장치 온보딩을 표시하는 PDF 이미지 ](images/onboard-intune.png)](images/onboard-intune-big.png#lightbox)

[PDF](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.pdf) 또는 [Visio를](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.vsdx) 확인하여 끝점용 Defender 배포에서 다양한 경로를 확인할 수 있습니다. 

[Intune의](https://docs.microsoft.com/intune/advanced-threat-protection)지침을 따릅니다.

Endpoint CSP용 Defender 사용에 대한 자세한 내용은 [WindowsAdvancedThreatProtection CSP](https://msdn.microsoft.com/library/windows/hardware/mt723296(v=vs.85).aspx) 및 [WindowsAdvancedThreatProtection DDF 파일](https://msdn.microsoft.com/library/windows/hardware/mt723297(v=vs.85).aspx)을 참조하세요.


> [!NOTE]
> - 등록된 장치의 **상태** 정책은 읽기 전용 속성을 사용하며 수정될 수 없습니다.
> - 진단 데이터 보고 빈도 구성은 Windows 10 버전 1703의 디바이스에서만 사용할 수 있습니다.


>[!TIP]
> 장치를 온보드한 후 검색 테스트를 실행하여 장치가 서비스에 제대로 온보드되었는지 확인할 수 있습니다. 자세한 내용은 새로 온보딩된 끝점 디바이스용 Microsoft Defender에서 검색 테스트 [실행을 참조하세요.](run-detection-test.md)


[PDF](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.pdf) 또는 [Visio를](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/security/defender-endpoint/downloads/mdatp-deployment-strategy.vsdx) 확인하여 Microsoft Defender ATP 배포에서 다양한 경로를 확인할 수 있습니다. 

## <a name="offboard-and-monitor-devices-using-mobile-device-management-tools"></a>모바일 장치 관리 도구를 사용하여 장치 오프보드 및 모니터링
보안상의 이유로, 오프보드 장치에 사용된 패키지는 다운로드한 날짜 30일 후에 만료됩니다. 장치에 전송된 만료된 오프보더 패키지는 거부됩니다. 오프보더 패키지를 다운로드할 때 패키지 만료 날짜에 대한 알림을 하게 되고 패키지 이름에도 포함됩니다.

> [!NOTE]
> 온보드 및 오프보더 정책을 동일한 장치에 동시에 배포하면 안 됩니다. 그렇지 않으면 예측할 수 없는 충돌이 발생할 수 있습니다.

1. Microsoft Defender 보안 센터에서 오프보딩 [패키지를 다운로드합니다.](https://securitycenter.windows.com/)

   1. 탐색 창에서 설정 **오프보링**  >  **을 선택합니다.**

   1. 운영 체제로 Windows 10을 선택합니다.

   1. 배포 **방법 필드에서** 모바일 장치 관리 **/ Microsoft Intune 을 선택합니다.**
    
   1. 패키지 **다운로드를** 클릭하고 .zip 파일을 저장합니다.

2. 패키지를 배포할 네트워크 관리자가 액세스할 수 있는 공유 읽기 전용 위치에 .zip 파일의 내용을 추출합니다. 이름이 *WindowsDefenderATP_valid_until_YYYY-MM-DD.offboarding 입니다.*

3. Microsoft Intune 사용자 지정 구성 정책을 사용하여 지원되는 다음 OMA-URI 설정을 배포합니다.

      OMA-URI: ./Device/Vendor/MSFT/WindowsAdvancedThreatProtection/Offboarding<br/>
      날짜 형식: 문자열<br/>
      값: [WindowsDefenderATP_valid_until_YYYY-MM-DD.offboarding 파일의 콘텐츠에서 값을 복사하여 붙여넣기]

Microsoft Intune 정책 설정에 대한 자세한 내용은 [Microsoft Intune의 Windows 10 정책 설정을 참조하세요.](https://docs.microsoft.com/intune/deploy-use/windows-10-policy-settings-in-microsoft-intune)


> [!NOTE]
> 등록 **해제된 장치의 상태 정책은** 읽기 전용 속성을 사용하며 수정될 수 없습니다.

> [!IMPORTANT]
> 오프보더링을 통해 디바이스가 포털에 센서 데이터 전송을 중지하지만, 디바이스에서 전송한 모든 경고에 대한 참조를 포함하여 장치의 데이터는 최대 6개월 동안 보존됩니다.

## <a name="related-topics"></a>관련 항목
- [그룹 정책을 사용하여 Windows 10 장치 온보드](configure-endpoints-gp.md)
- [Microsoft Endpoint Configuration Manager를 사용하여 Windows 10 장치 온보드](configure-endpoints-sccm.md)
- [로컬 스크립트를 사용하여 Windows 10 장치 온보딩](configure-endpoints-script.md)
- [비영구 가상 데스크톱 인프라(VDI) 장치 온보딩](configure-endpoints-vdi.md)
- [새로 온보딩된 엔드포인트 디바이스용 Microsoft Defender에서 검색 테스트 실행](run-detection-test.md)
- [끝점 온보딩 문제에 대한 Microsoft Defender 문제 해결](troubleshoot-onboarding.md)
