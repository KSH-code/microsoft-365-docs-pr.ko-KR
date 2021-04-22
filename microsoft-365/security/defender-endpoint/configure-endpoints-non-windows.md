---
title: 끝점용 Microsoft Defender 서비스에 비 Windows 장치 온보딩
description: 끝점용 Microsoft Defender 서비스로 센서 데이터를 보낼 수 있도록 비 Windows 장치를 구성합니다.
keywords: 비 Windows 장치, macos, linux, 장치 관리, 끝점 장치에 대한 Microsoft Defender 구성
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
ms.openlocfilehash: 1c10576b72793ab3833f2e9027e3814a449334ee
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/21/2021
ms.locfileid: "51933928"
---
# <a name="onboard-non-windows-devices"></a>Windows가 아닌 장치 온보딩

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**적용 대상:**
- [엔드포인트용 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

**플랫폼**
- macOS
- Linux

>Endpoint용 Defender를 경험하고 싶나요? [무료 평가판에 등록합니다.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-nonwindows-abovefoldlink) 

Endpoint용 Defender는 Windows가 아닌 플랫폼뿐만 아니라 Windows에 대한 중앙 집중식 보안 운영 환경을 제공합니다. Microsoft Defender 보안 센터에서 지원되는 다양한 OS(운영 체제)에서 경고를 보고 조직의 네트워크를 보다 잘 보호할 수 있습니다. 

통합을 위해 Endpoint용 Defender와 호환되는 정확한 Linux 배포판 및 macOS 버전을 알아야 합니다. 자세한 내용은 다음을 참조하세요.
- [Linux 시스템 요구 사항의 끝점용 Microsoft Defender](microsoft-defender-endpoint-linux.md#system-requirements)  
- [MacOS 시스템 요구 사항의 끝점용 Microsoft Defender](microsoft-defender-endpoint-mac.md#system-requirements)

## <a name="onboarding-non-windows-devices"></a>비 Windows 장치 온보드
비 Windows 장치를 온보드하려면 다음 단계를 따라야 합니다.
1. 기본 온보더링 방법을 선택합니다.

   - macOS 장치의 경우 끝점용 Microsoft Defender를 통해 또는 타사 솔루션을 통해 온보딩할 수 있습니다. 자세한 내용은 [Mac의 끝점용 Microsoft Defender를 참조하세요.](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/microsoft-defender-endpoint-mac)

   - 다른 비 Windows 장치의 경우 타사 통합을 통해 비 Windows 장치 **온보드를 선택하십시오.**   
    1. 탐색 창에서 상호 교환 파트너 **를**  >  **선택합니다.** 타사 솔루션이 나열되어 있는지 확인
    2. 파트너 **응용 프로그램 탭에서** 비 Windows 장치를 지원하는 파트너를 선택합니다.
    3. 파트너 **페이지 열기 를** 선택하여 파트너 페이지를 열 수 있습니다. 페이지에 제공된 지침을 따릅니다.
    4. 계정을 만들거나 파트너 솔루션을 신청한 후 조직의 테넌트 전역 관리자에게 파트너 응용 프로그램의 사용 권한 요청을 수락할지 묻는 단계가 표시됩니다. 사용 권한 요청을 신중하게 읽어 필요한 서비스에 맞춰지십시오. 

        
2. 타사 솔루션의 지침에 따라 검색 테스트를 실행합니다.

## <a name="offboard-non-windows-devices"></a>비 Windows 장치 온보드

1. 타사의 설명서에 따라 끝점용 Microsoft Defender에서 타사 솔루션 연결을 끊습니다.

2. Azure AD 테넌트에서 타사 솔루션에 대한 사용 권한을 제거합니다.
   1. [Azure 포털](https://portal.azure.com)에 로그인합니다.
   2. **Azure Active Directory > 엔터프라이즈 응용 프로그램을 선택합니다.**
   3. 오프보드할 응용 프로그램을 선택합니다.
   4. 삭제 **단추를** 선택합니다.


## <a name="related-topics"></a>관련 항목
- [그룹 정책을 통한 Windows 10 장치 온보딩](configure-endpoints.md)
- [서버 온보드](configure-server-endpoints.md)
- [프록시 및 인터넷 연결 설정 구성](configure-proxy-internet.md)
- [끝점 온보딩 문제에 대한 Microsoft Defender 문제 해결](troubleshoot-onboarding.md)
