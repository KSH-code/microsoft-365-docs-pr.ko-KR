---
title: 새 Microsoft Edge
description: ''
keywords: 브라우저, Microsoft Managed Desktop, Microsoft 365, 서비스, 설명서
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: f4bc5f85b21148c5a923ca1fc18879a193191c4b
ms.sourcegitcommit: 09a500a44d8723f8f2be87d9ad4ce7e453c5192b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/10/2020
ms.locfileid: "45094789"
---
# <a name="new-microsoft-edge-app"></a>새 Microsoft Edge 앱

새 [Microsoft Edge 브라우저](https://www.microsoft.com/edge) 를 사용 하는 경우에는 사용자의 개인 정보 보호, 생산성 향상, 그리고 탐색 중에는 값이 많을 수록 성능이 향상 되었습니다. Microsoft Managed Desktop은 사용자 환경에서 새에 지 브라우저의 배포에 대 한 공용 미리 보기를 제공 합니다.

## <a name="initial-deployment"></a>초기 배포

Microsoft Managed Desktop devices를 새 Microsoft Edge 브라우저로 마이그레이션하려면 Microsoft Managed Desktop Portal을 통해 IT 지원 티켓을 파일에 제공 해야 합니다. 티켓을 사용할 때에는에 지 안정적인 채널을 테스트 그룹에 배포 하 고 각 후속 배포 그룹에서 24 시간 마다이를 배포 합니다. 배포를 일시 중지 하려면 보류할 작업을 요청 하는 다른 티켓을 파일에 저장 합니다.

## <a name="updates-to-microsoft-edge"></a>Microsoft Edge 업데이트

Microsoft Managed Desktop은 6 주 마다 자동으로 업데이트 되는 Microsoft Edge의 [안정적인 채널](https://docs.microsoft.com/deployedge/microsoft-edge-channels#stable-channel) 을 배포 합니다. 고객에 게 가장 적합 한 환경을 보장 하기 위해 안정적인 채널의 업데이트가 Microsoft Edge 제품 그룹에 의해 [점진적](https://docs.microsoft.com/deployedge/microsoft-edge-update-progressive-rollout) 으로 롤오버 됩니다. Microsoft Edge 베타 채널을 현재 사용할 수 없습니다.

Microsoft Edge가 제대로 업데이트 되도록 하려면 Microsoft Edge [업데이트 정책을](https://docs.microsoft.com/deployedge/microsoft-edge-update-policies)수정 하지 마십시오.

## <a name="settings-managed-by-microsoft-managed-desktop"></a>Microsoft Managed Desktop에서 관리 하는 설정

Microsoft Managed Desktop이 브라우저 보안을 위해 Microsoft Edge에 대 한 기본 정책 집합을 만들었습니다. 기본 브라우저 설정은 다음과 같습니다.

### <a name="microsoft-edge-extensions"></a>Microsoft Edge 확장

Microsoft Managed Desktop devices의 Microsoft Edge에 대 한 보안 기준선은 모든 Chrome 확장을 사용 하지 않도록 설정 하 고 최종 사용자를 보호 하는 두 가지 정책을 지원 합니다. 사용자 환경에서 확장을 사용 하도록 설정 하 고 배포 하려면 관리 하는 설정을 참조 하세요. 

#### <a name="extension-installation-blocklist"></a>확장 설치 blocklist
**기본값:** 모든

Microsoft Managed Desktop은이 정책을 설정 하 여 Chrome 확장이 관리 되는 종점에 설치 되는 것을 방지 합니다. 데이터 손실 방지, 개인 정보 보호 및 장치를 손상 시킬 수 있는 기타 위험을 포함 하 여 Chromium extension 모델에 알려진 risksassociated가 있습니다. 

#### <a name="allow-user-level-native-messaging-hosts-installed-without-admin-permissions"></a>사용자 수준 기본 메시징 호스트 허용 (관리자 권한 없이 설치 됨)

**기본값:** 있지

이 정책을 사용 하지 않도록 설정 하면 Microsoft Edge에서는 시스템 수준에 설치 된 기본 메시징 호스트만 사용 합니다. 기본 메시징 호스트는 브라우저에서 사용자의 끝점에 대 한 다른 부분과 상호 작용 하 여 다양 한 보안 문제를 만들 수 있도록 하는 Chrome 확장의 일부입니다.  

### <a name="secure-sockets-layer-ssl"></a> SSL(Secure Sockets Layer) 

#### <a name="minimum-ssl-version"></a>최소 SSL 버전

**기본값:** 최소 TLS 1.2 지원 됨

덜 안전한 TLS 1.1을 사용 하려는 경우이를 요청할 수 있습니다.

#### <a name="allows-users-to-proceed-from-the-ssl-warning-page"></a>SSL 경고 페이지에서 사용자가 계속할 수 있도록 허용 합니다.

**기본값:** 있지

사용자가 SSL 오류가 있는 사이트를 방문할 수 있으므로이 설정을 사용 하지 않는 것이 좋습니다.

### <a name="microsoft-defender-smart-screen"></a>Microsoft Defender Smart 화면

#### <a name="configure-microsoft-defender-smartscreen"></a>Microsoft Defender SmartScreen 구성

**기본값:** 된

최종 사용자를 보호 하기 위해 기본적으로 사용 하도록 설정 됩니다.

#### <a name="microsoft-defender-smartscreen-prompts-for-sites"></a>사이트에 대 한 Microsoft Defender SmartScreen 음성 안내

**기본값:** 된

이 설정은 사용자가 경고를 무시 하 고 잠재적으로 악성 사이트로 이동할 수 있도록 하는 것 이므로이 설정을 사용 하지 않는 것이 좋습니다.

#### <a name="prevent-bypassing-of-microsoft-defender-smartscreen-warnings-about-downloads"></a>다운로드에 대 한 Microsoft Defender SmartScreen 경고 바이패스 방지

**기본값:** 된

이 설정은 사용자가 경고를 무시 하 고 확인 되지 않은 다운로드를 완료할 수 있도록 하는 것 이므로이 설정을 사용 하지 않는 것이 좋습니다.

### <a name="adobe-flash"></a>Adobe Flash

#### <a name="default-adobe-flash-setting"></a>기본 Adobe Flash 설정

**기본값:** 있지

연결 된 보안 위험으로 인해 Flash를 사용 하지 않는 것이 좋습니다. 여전히 Flash에 의존 하는 프로세스를 사용 하는 경우에는 **[PluginsAllowedForUrls](https://docs.microsoft.com/deployedge/microsoft-edge-policies#pluginsallowedforurls)** 정책을 설정 하 여 해당 프로세스가 필요한 사이트에서 flash를 활성화 합니다. Flash를 사용할 수 있도록 허용 된 사이트 목록을 유지 관리할 수 없는 경우에는 변경 요청을 수행 하 여 **클릭**하 여 재생 하도록 값을 변경 하면 사용자가 Flash를 실행 하는 것이 적절할 때를 선택할 수 있습니다.

### <a name="password-manager"></a>암호 관리자

#### <a name="enable-saving-passwords-to-the-password-manager"></a>암호 관리자에 게 암호 저장 사용

**기본값:** 있지

최종 사용자가 자신의 장치에 암호를 저장 하도록 허용 하지 않는 것이 좋습니다.

### <a name="other-settings"></a>기타 설정

#### <a name="enable-site-isolation-for-every-site"></a>모든 사이트에 대해 사이트 격리 사용

**기본값:** 된

이 정책을 사용 하도록 설정 하면 사용자가 각 사이트가 자체 프로세스에서 실행 되는 기본 동작을 거부할 수 없습니다.

#### <a name="supported-authentication-schemes"></a>지원 되는 인증 체계

**기본값:** NTLM, 협상

Microsoft Managed Desktop은 기본 또는 다이제스트 인증 체계를 지원 하지 않습니다.

#### <a name="automatically-import-another-browsers-data-and-settings-at-first-run"></a>처음 실행 시 다른 브라우저의 데이터 및 설정 자동 가져오기

**기본값:** 기본 브라우저에서 지원 되는 모든 데이터 형식 및 설정 자동 가져오기 

이 정책이 적용 된 경우 첫 번째 실행 환경에서는 가져오기 섹션을 건너뛰어 사용자 상호 작용이 최소화 됩니다. 이전 버전의 Microsoft Edge에서의 브라우저 데이터는이 설정에 관계 없이 항상 처음 실행할 때 자동으로 마이그레이션됩니다. 


## <a name="settings-you-manage"></a>관리 하는 설정

이전에 Microsoft Intune에서 관리 템플릿 프로필을 사용 하 여 설명한 것이 아니라 마이크로 Sft Edge 설정을 배포할 수 있습니다. 자세한 내용은 [Microsoft Intune을 사용 하 여 Microsoft Edge 정책 설정 구성을](https://docs.microsoft.com/deployedge/configure-edge-with-intune)참조 하십시오. Intune에서 Microsoft Edge 관리 템플릿에 현재 포함 되어 있지 않은 정책을 평가 하려는 경우 Intune에서 Windows 10 장치에 대 한 사용자 지정 설정을 사용할 수 있습니다.

### <a name="enabling-specific-chrome-extensions"></a>특정 크롬 확장 사용

관리 템플릿은 Microsoft Intune을 사용 하 여 특정 Chrome 확장을 배포 하는 설정을 제공 합니다. **> Microsoft Edge > Extensions를 사용 하 여 특정 확장명을 설치 하도록 허용 > 컴퓨터 구성**에서 찾을 수 있습니다.

### <a name="install-extensions-silently"></a>자동으로 내선 번호 설치

관리 템플릿을 사용 하 여 Microsoft Edge가 사용자에 게 경고를 표시 하지 않고 확장을 설치 하도록 설정할 수도 있습니다. **Microsoft Edge > extensions > 컴퓨터 구성에서 찾을 수 있으며, 자동으로 설치 되는 확장명을 제어할 >**.

### <a name="other-common-enterprise-policies"></a>기타 일반 엔터프라이즈 정책

Microsoft Edge에서는 매우 많은 추가 정책을 제공 합니다. 다음은 흔히 발생 하는 몇 가지 예입니다.
 
- [엔터프라이즈 사이트 목록 및 IE 모드에서 사이트 구성](https://docs.microsoft.com/deployedge/edge-ie-mode-sitelist)
- [시작, 홈 페이지 및 새 탭 페이지 설정 구성](https://docs.microsoft.com/deployedge/microsoft-edge-policies#startup-home-page-and-new-tab-page)
- [서피스 게임 설정 구성](https://docs.microsoft.com/deployedge/microsoft-edge-policies#allowsurfgame)
- [프록시 서버 설정 구성](https://docs.microsoft.com/deployedge/microsoft-edge-policies#proxy-server)

