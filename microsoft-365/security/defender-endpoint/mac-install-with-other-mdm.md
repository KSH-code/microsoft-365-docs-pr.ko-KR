---
title: Mac의 끝점용 Microsoft Defender에 대해 다른 MDM(모바일 장치 관리) 시스템을 사용하여 배포
description: 다른 관리 솔루션에 Mac에 끝점용 Microsoft Defender를 설치합니다.
keywords: microsoft, defender, Endpoint용 Microsoft Defender, mac, 설치, 배포, macos, 카탈로니아, mojave, high sierra
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: mavel
author: maximvelichko
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 2e133c9f924b614c8cc34c9a943895736526e6e7
ms.sourcegitcommit: bf3965b46487f6f8cf900dd9a3af8b213a405989
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/02/2021
ms.locfileid: "60668027"
---
# <a name="deployment-with-a-different-mobile-device-management-mdm-system-for-microsoft-defender-for-endpoint-on-macos"></a>macOS의 끝점용 Microsoft Defender에 대해 다른 MDM(모바일 장치 관리) 시스템을 사용하여 배포

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**적용 대상:**
- [엔드포인트용 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Endpoint용 Defender를 경험하고 싶나요? [무료 평가판을 신청하세요.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-investigateip-abovefoldlink)
 
## <a name="prerequisites-and-system-requirements"></a>선행 조건 및 시스템 요구 사항

시작하기 전에 [MacOS의 주 Microsoft Defender for Endpoint](microsoft-defender-endpoint-mac.md) 페이지에서 현재 소프트웨어 버전에 대한 선행 조건 및 시스템 요구 사항에 대한 설명을 참조하세요.


## <a name="approach"></a>방법

> [!CAUTION]

> 현재 Microsoft는 MacOS에서 끝점용 Microsoft Defender의 배포 및 관리를 위해 Intune 및 JAMF만 공식적으로 지원하고 있습니다. Microsoft는 아래 제공된 정보에 대해 표현적 또는 암시적 보증을하지 않습니다.

조직에서 공식적으로 지원되지 않는 MDM(모바일 장치 관리) 솔루션을 사용하는 경우 macOS에서 끝점용 Microsoft Defender를 배포하거나 실행할 수 없습니다.

MacOS의 끝점용 Microsoft Defender는 공급업체별 기능에 의존하지 않습니다. 이 기능은 다음 기능을 지원하는 모든 MDM 솔루션에서 사용할 수 있습니다.

- 관리되는 장치에 macOS .pkg를 배포합니다.
- 관리되는 장치에 macOS 시스템 구성 프로필을 배포합니다.
- 관리되는 장치에서 임의로 관리자가 구성한 도구/스크립트를 실행합니다.

대부분의 최신 MDM 솔루션에는 이러한 기능이 포함되어 있습니다. 그러나 이러한 기능을 다르게 호출할 수도 있습니다.

그러나 앞의 목록에서 마지막 요구 사항 없이 Endpoint용 Defender를 배포할 수 있습니다.

- 중앙 집중식 방식으로 상태를 수집할 수 없습니다.
- Endpoint용 Defender를 제거하기로 결정한 경우 로컬에서 관리자로 클라이언트 장치에 로그온해야 합니다.

## <a name="deployment"></a>배포

대부분의 MDM 솔루션은 비슷한 용어를 사용하여 macOS 장치를 관리하는 데 동일한 모델을 사용 합니다. [JAMF 기반 배포를](mac-install-with-jamf.md) 템플릿으로 사용

### <a name="package"></a>패키지

포털 에서 [](mac-install-with-jamf.md)다운로드한 설치 패키지(wdav.pkg)를 Microsoft 365 Defender [배포를 구성합니다.](mac-install-with-jamf.md)

엔터프라이즈에 패키지를 배포하기 위해 MDM 솔루션과 관련된 지침을 사용하세요.

### <a name="license-settings"></a>라이선스 설정

시스템 [구성 프로필을 설정합니다.](mac-install-with-jamf.md) 

MacOS의 끝점용 Microsoft Defender는 macOS의 일부가 아니기 때문에 MDM 솔루션에서 "사용자 지정 설정 프로필"처럼 호출할 수 있습니다.

Microsoft 365 Defender 포털에서 다운로드한 등록 패키지에서 추출할 수 있는 속성 목록 jamf/WindowsDefenderATPOnboarding.plist를 [사용하세요.](mac-install-with-jamf.md)
시스템에서 임의의 속성 목록을 XML 형식으로 지원할 수 있습니다. jamf/WindowsDefenderATPOnboarding.plist 파일을 현재 있는 것으로 업로드할 수 있습니다.
또는 먼저 속성 목록을 다른 형식으로 변환해야 할 수 있습니다.

일반적으로 사용자 지정 프로필에는 ID, 이름 또는 도메인 특성이 있습니다. 이 값은 정확히 "com.microsoft.wdav.atp"를 사용해야 합니다.
MDM은 이 파일을 사용하여 클라이언트 장치의 **/Library/Managed Preferences/com.microsoft.wdav.atp.plist에** 설정 파일을 배포하고 Defender for Endpoint는 이 파일을 사용하여 온보딩 정보를 로드합니다.

### <a name="kernel-extension-policy"></a>커널 확장 정책

KEXT 또는 커널 확장 정책을 설정합니다. 팀 식별자 **UBF8T346G9를** 사용하여 Microsoft에서 제공하는 커널 확장을 허용합니다.

> [!CAUTION]
> 작업 환경이 Apple 실리콘(M1) 장치로 구성된 경우 이러한 컴퓨터는 KEXT 정책을 사용하여 구성 프로필을 수신하지 않습니다.
> Apple은 이러한 컴퓨터의 KEXT를 지원하지 않습니다. 이러한 프로필의 배포는 M1 컴퓨터에서 실패합니다.

### <a name="system-extension-policy"></a>시스템 확장 정책

시스템 확장 정책을 설정합니다. 팀 식별자 **UBF8T346G9를** 사용하여 다음 번들 식별자를 승인합니다.

- com.microsoft.wdav.epsext
- com.microsoft.wdav.netext

### <a name="full-disk-access-policy"></a>전체 디스크 액세스 정책

다음 구성 요소에 대한 전체 디스크 액세스 권한을 부여합니다.

- 엔드포인트용 Microsoft Defender
    - 식별자: `com.microsoft.wdav`
    - 식별자 유형: 번들 ID
    - 코드 요구 사항: `identifier "com.microsoft.wdav" and anchor apple generic and certificate 1[field.1.2.840.113635.100.6.2.6] /* exists */ and certificate leaf[field.1.2.840.113635.100.6.1.13] /* exists */ and certificate leaf[subject.OU] = UBF8T346G9`

- 끝점 보안 확장용 Microsoft Defender
    - 식별자: `com.microsoft.wdav.epsext`
    - 식별자 유형: 번들 ID
    - 코드 요구 사항: `identifier "com.microsoft.wdav.epsext" and anchor apple generic and certificate 1[field.1.2.840.113635.100.6.2.6] /* exists */ and certificate leaf[field.1.2.840.113635.100.6.1.13] /* exists */ and certificate leaf[subject.OU] = UBF8T346G9`

### <a name="network-extension-policy"></a>네트워크 확장 정책

끝점 검색 및 응답 기능의 일부로 macOS의 끝점용 Microsoft Defender는 소켓 트래픽을 검사하고 이 정보를 Microsoft 365 Defender 포털에 보고합니다. 다음 정책은 네트워크 확장에서 이 기능을 수행할 수 있습니다.

- 필터 유형: 플러그 인
- 플러그 인 번들 식별자: `com.microsoft.wdav`
- 필터 데이터 공급자 번들 식별자: `com.microsoft.wdav.netext`
- 데이터 공급자가 지정한 요구 사항을 필터링합니다. `identifier "com.microsoft.wdav.tunnelext" and anchor apple generic and certificate 1[field.1.2.840.113635.100.6.2.6] /* exists */ and certificate leaf[field.1.2.840.113635.100.6.1.13] /* exists */ and certificate leaf[subject.OU] = UBF8T346G9`
- 필터 소켓: `true`

## <a name="check-installation-status"></a>설치 상태 확인

클라이언트 [장치에서 끝점용 Microsoft Defender를](mac-install-with-jamf.md) 실행하여 온보딩 상태를 확인합니다.
