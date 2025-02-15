---
title: 모바일 장치 관리 도구를 사용한 Windows 장치 온보딩
description: 모바일 장치 관리 도구를 사용하여 끝점용 Defender 서비스에 온보딩할 수 있도록 장치에 구성 패키지를 배포합니다.
keywords: mdm을 사용하여 장치 온보딩, 장치 관리, Endpoint 장치용 Microsoft Defender 온보딩, mdm
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
ms.custom: admindeeplinkDEFENDER
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 1d0bfb7070f06b94aeaea69f0563e4f5e5d1ca67
ms.sourcegitcommit: 542e6b5d12a8d400c3b9be44d849676845609c5f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/15/2021
ms.locfileid: "60963086"
---
# <a name="onboard-windows-devices-using-mobile-device-management-tools"></a>모바일 장치 관리 도구를 사용한 Windows 장치 온보딩

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**적용 대상:**
- [엔드포인트용 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Endpoint용 Defender를 경험하고 싶나요? [무료 평가판을 신청하세요.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-configureendpointsmdm-abovefoldlink)

MDM(모바일 장치 관리) 솔루션을 사용하여 모바일 장치를 구성할 Windows 10 있습니다. Endpoint용 Defender는 장치 관리 정책을 만들 수 있는 OMA-URIs MDM을 지원합니다.


Endpoint CSP용 Defender 사용에 대한 자세한 내용은 [WindowsAdvancedThreatProtection CSP](https://msdn.microsoft.com/library/windows/hardware/mt723296(v=vs.85).aspx) 및 [WindowsAdvancedThreatProtection DDF 파일](https://msdn.microsoft.com/library/windows/hardware/mt723297(v=vs.85).aspx)을 참조하세요.

## <a name="before-you-begin"></a>시작하기 전에

디바이스를 사용하는 Microsoft Intune MDM이 등록되어 있어야 합니다. 그렇지 않으면 설정이 적용되지 않습니다.

MDM과 함께 MDM을 사용하도록 설정하는 Microsoft Intune 장치 [등록(Microsoft Intune)을 참조하세요.](/mem/intune/enrollment/device-enrollment)

## <a name="onboard-devices-using-microsoft-intune"></a>디바이스를 사용하여 장치 온보 Microsoft Intune

[PDF](https://download.microsoft.com/download/5/6/0/5609001f-b8ae-412f-89eb-643976f6b79c/mde-deployment-strategy.pdf) 또는 Visio [](https://download.microsoft.com/download/5/6/0/5609001f-b8ae-412f-89eb-643976f6b79c/mde-deployment-strategy.vsdx) 끝점용 Defender 배포에서 다양한 경로를 확인할 수 있습니다.

[Intune의](/intune/advanced-threat-protection)지침을 따릅니다.

Endpoint CSP용 Defender 사용에 대한 자세한 내용은 [WindowsAdvancedThreatProtection CSP](https://msdn.microsoft.com/library/windows/hardware/mt723296(v=vs.85).aspx) 및 [WindowsAdvancedThreatProtection DDF 파일](https://msdn.microsoft.com/library/windows/hardware/mt723297(v=vs.85).aspx)을 참조하세요.

> [!NOTE]
>
> - 등록된 장치의 **상태** 정책은 읽기 전용 속성을 사용하며 수정될 수 없습니다.
> - 진단 데이터 보고 빈도 구성은 버전 1703의 Windows 10 사용할 수 있습니다.


[PDF](https://download.microsoft.com/download/5/6/0/5609001f-b8ae-412f-89eb-643976f6b79c/mde-deployment-strategy.pdf) 또는 Visio [](https://download.microsoft.com/download/5/6/0/5609001f-b8ae-412f-89eb-643976f6b79c/mde-deployment-strategy.vsdx) Microsoft Defender for Endpoint 배포에서 다양한 경로를 확인할 수 있습니다.

## <a name="run-a-detection-test-to-verify-onboarding"></a>검색 테스트를 실행하여 온보더링 확인
장치를 온보드한 후 검색 테스트를 실행하여 장치가 서비스에 제대로 온보드되었는지 확인할 수 있습니다. 자세한 내용은 새로 온보딩된 끝점 디바이스용 Microsoft Defender에서 검색 테스트 [실행을 참조하세요.](run-detection-test.md)


## <a name="offboard-and-monitor-devices-using-mobile-device-management-tools"></a>모바일 장치 관리 도구를 사용하여 장치 오프보드 및 모니터링

보안상의 이유로, 오프보드 장치에 사용된 패키지는 다운로드한 날짜 30일 후에 만료됩니다. 장치에 전송된 만료된 오프보더 패키지는 거부됩니다. 오프보더 패키지를 다운로드할 때 패키지 만료 날짜에 대한 알림을 하게 되고 패키지 이름에도 포함됩니다.

> [!NOTE]
> 온보드 및 오프보더 정책을 동일한 장치에 동시에 배포하면 안 됩니다. 그렇지 않으면 예측할 수 없는 충돌이 발생할 수 있습니다.

1. 에서 오프보더 패키지를 Microsoft 365 Defender <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">포털</a>:

   1. 탐색 창에서 **끝점 설정** 관리 \>  \>  오프보링 \> **을 선택합니다.**

   1. 운영 Windows 10 Windows 11 선택하거나 선택합니다.

   1. 배포 **방법 필드에서** 모바일 장치 관리 **/를 Microsoft Intune.**

   1. 패키지 **다운로드를** 클릭하고 파일 .zip 저장합니다.

2. 패키지를 배포할 네트워크 관리자가 액세스할 수 있는 .zip 공유 읽기 전용 위치로 파일 파일의 내용을 추출합니다. 이름이 *WindowsDefenderATP_valid_until_YYYY-MM-DD.offboarding 입니다.*

3. 사용자 Microsoft Intune 정책을 사용하여 지원되는 다음 OMA-URI 설정을 배포합니다.
   - OMA-URI: ./Device/Vendor/MSFT/WindowsAdvancedThreatProtection/Offboarding
   - 날짜 형식: 문자열
   - 값: [WindowsDefenderATP_valid_until_YYYY-MM-DD.offboarding 파일의 콘텐츠에서 값을 복사하여 붙여넣기]

정책 설정에 대한 Microsoft Intune 자세한 내용은 Windows 10 정책 설정을 [Microsoft Intune.](/mem/intune/configuration/custom-settings-windows-10)

> [!NOTE]
> 등록 **해제된 장치의 상태 정책은** 읽기 전용 속성을 사용하며 수정될 수 없습니다.

> [!IMPORTANT]
> 오프보더링을 통해 디바이스가 포털에 센서 데이터 전송을 중지하지만, 디바이스에서 전송한 모든 경고에 대한 참조를 포함하여 장치의 데이터는 최대 6개월 동안 보존됩니다.

## <a name="related-topics"></a>관련 주제
- [그룹 정책을 사용하여 Windows 장치 온보딩](configure-endpoints-gp.md)
- [Microsoft Endpoint Configuration Manager를 사용하여 Windows 컴퓨터 온보딩](configure-endpoints-sccm.md)
- [로컬 스크립트를 사용하여 Windows 장치 온보딩](configure-endpoints-script.md)
- [비영구 VDI(가상 데스크톱 인프라) 장치 온보딩](configure-endpoints-vdi.md)
- [새로 온보딩된 엔드포인트 디바이스용 Microsoft Defender에서 검색 테스트 실행](run-detection-test.md)
- [끝점 온보딩 문제에 대한 Microsoft Defender 문제 해결](troubleshoot-onboarding.md)
