---
title: Microsoft Defender for Endpoint Windows 비보안 장치 온보딩
description: 끝점 Windows Microsoft Defender로 센서 데이터를 보낼 수 있도록 비보안 장치를 구성합니다.
keywords: 비구성 Windows, macos, linux, 장치 관리, 끝점 장치용 Microsoft Defender 구성
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
ms.technology: mde
ms.openlocfilehash: 775db5f94cacbca08993b0cb9aac67019515174a
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2021
ms.locfileid: "60210032"
---
# <a name="onboard-non-windows-devices"></a>Windows가 아닌 장치 온보딩

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**적용 대상:**
- [엔드포인트용 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

**플랫폼**
- macOS
- Linux

> Endpoint용 Defender를 경험하고 싶나요? [무료 평가판을 신청하세요.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-nonwindows-abovefoldlink)

Endpoint용 Defender는 비영리 플랫폼 및 비영리 Windows 중앙 집중식 Windows 환경을 제공합니다. 조직에서 지원되는 다양한 OS(운영 체제)에서 경고를 Microsoft 365 Defender 조직의 네트워크를 보다 잘 보호할 수 있습니다.

통합을 위해 Endpoint용 Defender와 호환되는 정확한 Linux 배포판 및 macOS 버전을 알아야 합니다. 자세한 내용은 다음을 참조하세요.

- [Linux 시스템 요구 사항의 끝점용 Microsoft Defender](microsoft-defender-endpoint-linux.md#system-requirements)
- [MacOS 시스템 요구 사항의 끝점용 Microsoft Defender](microsoft-defender-endpoint-mac.md#system-requirements)

## <a name="onboarding-non-windows-devices"></a>비보안 Windows 온보드

비보안 장치를 온보드하려면 다음 단계를 Windows 합니다.

1. 기본 온보더링 방법을 선택합니다.

   - macOS 장치의 경우 끝점용 Microsoft Defender를 통해 또는 타사 솔루션을 통해 온보딩할 수 있습니다. 자세한 내용은 [Mac의 끝점용 Microsoft Defender를 참조하세요.](/microsoft-365/security/defender-endpoint/microsoft-defender-endpoint-mac)

   - 비영리 Windows 타사 Windows 장치를 **온보드합니다.**
    1. 탐색 창에서 파트너 및 API 파트너 **응용** \> **프로그램을 선택합니다.** 타사 솔루션이 나열되어 있는지 확인
    2. 파트너 **응용 프로그램 페이지에서** 비프로그램 디바이스를 지원하는 Windows 선택합니다.
    3. **보기를** 클릭하여 파트너의 페이지를 열 수 있습니다. 페이지에 제공된 지침을 따릅니다.
    4. 계정을 만들거나 파트너 솔루션을 신청한 후 조직의 테넌트 전역 관리자에게 파트너 응용 프로그램의 사용 권한 요청을 수락할지 묻는 단계가 표시됩니다. 사용 권한 요청을 신중하게 읽어 필요한 서비스에 맞게 조정해야 합니다.

2. 타사 솔루션의 지침에 따라 검색 테스트를 실행합니다.

## <a name="offboard-non-windows-devices"></a>비보안 Windows 오프보드

macOS 및 Linux 장치의 경우 끝점용 Microsoft Defender를 통해 오프보딩할 수 있습니다. 탐색 창에서 **오프보드** 설정 선택을 선택하여 오프보링 프로세스를 \>  \> **시작합니다.**

타사 통합을 Windows 비보안 장치를 오프보드할 수 있습니다. 타사 솔루션을 통합하여 Windows 플랫폼을 실행하는 장치에 대해 적용 [범위를 사용하도록 설정](https://securitycenter.windows.com/interoperability/partners) 

## <a name="related-topics"></a>관련 항목

- [장치 Windows 온보드](configure-endpoints.md)
- [서버 온보드](configure-server-endpoints.md)
- [프록시 및 인터넷 연결 설정 구성](configure-proxy-internet.md)
- [끝점 온보딩 문제에 대한 Microsoft Defender 문제 해결](troubleshoot-onboarding.md)
