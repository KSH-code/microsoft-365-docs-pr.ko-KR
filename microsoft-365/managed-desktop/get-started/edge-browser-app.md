---
title: 새 Microsoft Edge
description: 새 에지 브라우저를 배포하고 업데이트하는 방법을 설명
keywords: 브라우저, Microsoft Managed Desktop, Microsoft 365, 서비스, 설명서
ms.service: m365-md
author: jaimeo
ms.author: jaimeo
manager: laurawi
audience: ITpro
ms.topic: article
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
ms.openlocfilehash: 2534319ad890fbac20fa106216740f49eb5a3572
ms.sourcegitcommit: dc26169e485c3a31e1af9a5f495be9db75c49760
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60756678"
---
# <a name="new-microsoft-edge-app"></a>새 Microsoft Edge 앱

새로운 Microsoft Edge [브라우저는](https://www.microsoft.com/edge) 검색하는 동안 더 많은 개인 정보, 생산성 및 더 많은 가치를 제공하는 세계적 수준의 성능을 제공합니다. Microsoft Managed Desktop 환경의 새 에지 브라우저 배포에 대한 공개 미리 보기를 제공합니다.

## <a name="initial-deployment"></a>초기 배포

사용자 Microsoft Managed Desktop 새 Microsoft Edge 브라우저로 마이그레이션하려면 Microsoft Managed Desktop 포털을 통해 IT 지원 티켓을 Microsoft Managed Desktop 합니다. 티켓을 제출할 때 Edge 안정 채널을 테스트 그룹에 배포한 다음 24시간마다 각 후속 배포 그룹에 배포합니다. 배포를 일시 중지하기 위해 Operations에 보류를 요청하는 다른 티켓을 제출합니다.

조직 [내에서](/deployedge/microsoft-edge-channels#beta-channel) 대표 유효성 검사를 요청하면 베타 채널을 사용할 수도 있습니다. Microsoft Managed Desktop 모든 사용자가 안정 채널 외에 베타 채널을 사용할 수 있도록 테스트 및 첫 번째 그룹에 필요한 경우 응용 프로그램을 배포합니다. 베타 채널에 액세스해야 하는 다른 사용자의 경우 최신 작업 공간 **- Edge 베타** 사용자 그룹에 추가하고 베타 채널에서 설치하도록 회사 포털

## <a name="updates-to-microsoft-edge"></a>업데이트 Microsoft Edge

Microsoft Managed Desktop 6주마다 [](/deployedge/microsoft-edge-channels#stable-channel) 자동으로 업데이트되는 Microsoft Edge 채널을 배포합니다. 안정 채널의 업데이트는 고객에게 [](/deployedge/microsoft-edge-update-progressive-rollout) 최상의 환경을 보장하기 위해 Microsoft Edge 제품 그룹에 의해 점진적으로 배포됩니다. 

베타 [채널은](/deployedge/microsoft-edge-channels#beta-channel) 조직 내의 대표적인 유효성 검사를 위해 테스트 및 첫 번째 그룹의 장치에 배포됩니다. 이 채널은 완전히 지원하며 약 6주마다 새로운 기능으로 자동 업데이트됩니다.

업데이트가 Microsoft Edge 확인하려면 업데이트 정책을 Microsoft Edge [않습니다.](/deployedge/microsoft-edge-update-policies)



## <a name="settings-managed-by-microsoft-managed-desktop"></a>설정 관리되는 Microsoft Managed Desktop

Microsoft Managed Desktop 브라우저를 보호하는 데 사용할 Microsoft Edge 정책 집합이 만들어졌습니다. 기본 브라우저 설정은 다음과 같습니다.

### <a name="microsoft-edge-extensions"></a>Microsoft Edge 확장

Microsoft Edge 디바이스의 Microsoft Managed Desktop 보안 기준은 모든 Chrome 확장 및 보안 사용자를 사용하지 않도록 설정하는 두 가지 정책을 설정합니다. 환경에서 확장을 사용하도록 설정하고 배포하려면 관리 설정 참조합니다. 

#### <a name="extension-installation-blocklist"></a>확장 설치 차단 목록
**기본값:** 모두

Microsoft Managed Desktop 끝점에 Chrome 확장이 설치되지 않도록 이 정책을 설정하는 것이 좋습니다. 데이터 손실 방지, 개인 정보 보호 및 장치를 손상시킬 수 있는 기타 위험을 포함하여 Chromium 확장 모델과 관련된 알려진 위험이 있습니다. 

#### <a name="allow-user-level-native-messaging-hosts-installed-without-admin-permissions"></a>사용자 수준 네이티브 메시징 호스트 허용(관리자 권한 없이 설치)

**기본값:** 사용 안 하게

이 정책을 사용하지 Microsoft Edge 수준에 설치된 네이티브 메시징 호스트만 사용할 수 있습니다. 기본 메시징 호스트는 Chrome 확장의 일부로, 브라우저가 사용자의 끝점의 다른 부분과 상호 작용할 수 있도록 하여 다양한 보안 관련 우려를 만들 수 있습니다.  

### <a name="secure-sockets-layer-tlsssl"></a>Secure Sockets Layer(TLS/SSL)

#### <a name="minimum-tls-version"></a>최소 TLS 버전

**기본값:** 최소 TLS 1.2 지원

보안이 낮은 TLS 1.1을 사용하려는 경우 요청을 제출하면 됩니다.

#### <a name="allows-users-to-proceed-from-the-ssl-warning-page"></a>사용자가 SSL 경고 페이지에서 계속할 수 있도록 허용

**기본값:** 사용 안 하게

사용자가 TSL 오류가 있는 사이트를 방문할 수 있으므로 이 설정을 사용하도록 설정하지 않는 것이 좋습니다.

### <a name="microsoft-defender-smartscreen"></a>Microsoft Defender SmartScreen

#### <a name="configure-windows-defender-smartscreen"></a>SmartScreen Windows Defender 구성

**기본값:** 사용

사용자를 보호하는 데 기본적으로 사용됩니다.

#### <a name="windows-defender-smartscreen-prompts-for-sites"></a>Windows Defender 사이트에 대한 SmartScreen 프롬프트

**기본값:** 사용

사용자가 경고를 무시하고 잠재적으로 악의적인 사이트를 계속 사용할 수 있도록 허용하기 때문에 이 설정을 사용 하지 않는 것이 좋습니다.

#### <a name="prevent-bypassing-of-windows-defender-smartscreen-warnings-about-downloads"></a>다운로드에 대한 Windows Defender SmartScreen 경고 무시 방지

**기본값:** 사용

사용자가 경고를 무시하고 미확인 다운로드를 완료할 수 있도록 허용하기 때문에 이 설정을 사용 안 하도록 설정하지 않는 것이 좋습니다.

### <a name="adobe-flash"></a>Adobe Flash

#### <a name="default-adobe-flash-setting"></a>기본 Adobe Flash 설정

**기본값:** 사용 안 하게

관련된 보안 위험 때문에 Flash를 사용하지 않는 것이 좋습니다. 여전히 Flash를 사용하는 프로세스가 있는 경우 **[PluginsAllowedForUrls](/deployedge/microsoft-edge-policies#pluginsallowedforurls)** 정책을 설정하여 필요한 사이트에 대해 Flash를 사용하도록 설정하십시오. Flash를 사용할 수 있는 허용된 사이트 목록을 유지할 수 없는 경우 사용자가 Flash를 실행할 적절한 경우 선택할 수 있도록 값을 **클릭하여** 재생으로 변경하는 변경 요청을 제출합니다.

### <a name="password-manager"></a>암호 관리자

#### <a name="enable-saving-passwords-to-the-password-manager"></a>암호 관리자에 암호 저장 사용

**기본값:** 사용 안 하게

암호 관리자는 기본적으로 사용하지 않도록 설정되어 있습니다. 이 기능을 사용하도록 설정하려면 지원 요청을 제출하고 서비스 엔지니어가 사용자 환경에서 설정을 사용하도록 설정할 수 있습니다.

### <a name="internet-explorer-mode-in-microsoft-edge"></a>Internet Explorer 모드 Microsoft Edge

Microsoft Edge의 IE 모드를 사용하면 조직에서 필요로 하는 모든 사이트를 단일 브라우저에서 간편하게 사용할 수 있습니다. Chromium 렌더링 엔진과 호환되는 사이트에는 통합 Chromium 엔진을 사용하며 IE 기능에 종속되지 않은 사이트에는 IE11(Internet Explorer 11)의 Trident MSHTML 엔진을 사용하게 됩니다. [자세한 정보](/DeployEdge/edge-ie-mode)

Microsoft Managed Desktop 기본적으로 Internet Explorer 모드로 설정됩니다.

#### <a name="internet-explorer-mode-integration"></a>Internet Explorer 모드 통합

**기본값:** Internet Explorer 모드

기본적으로 장치는 Internet Explorer 모드로 설정되지만 독립 실행형 11 창에서 Internet Explorer 열리게 설정할 수 있습니다. 이 동작을 변경하기 위해 지원 요청을 제출합니다.

#### <a name="add-sites-to-the-enterprise-mode-site-list"></a>Enterprise 사이트 목록에 사이트 추가

사이트가 Internet Explorer 모드로 열리기 위해 사이트 목록 에 [Enterprise 합니다.](/DeployEdge/edge-ie-mode-sitelist) 사이트 목록의 Enterprise 유지 관리하고 배포하는 것은 귀하의 책임입니다. 자세한 내용은 [Configure using the Configure Enterprise Mode Site List policy을 참조하세요.](/DeployEdge/edge-ie-mode-policies#configure-using-the-configure-the-enterprise-mode-site-list-policy)

### <a name="other-settings"></a>기타 설정

#### <a name="enable-site-isolation-for-every-site"></a>모든 사이트에 대해 사이트 고리 사용

**기본값:** 사용

해당 정책을 사용하도록 설정하면 사용자는 각 사이트가 자체 프로세스에서 실행되는 기본 동작을 옵트아웃(opt out)할 수 없습니다.

#### <a name="supported-authentication-schemes"></a>지원되는 인증 체계

**기본값:** NTLM, 협상

Microsoft Managed Desktop 또는 다이제스트 인증 체계를 지원하지 않습니다.

#### <a name="automatically-import-another-browsers-data-and-settings-at-first-run"></a>처음 실행 시 다른 브라우저의 데이터 및 설정 자동 가져오기

**기본값:** 기본 브라우저에서 지원되는 모든 데이터타입 및 설정을 자동으로 가져오기 

이 정책을 적용하면 첫 실행 환경은 가져오기 섹션을 건너뛰고 사용자 조작을 최소화합니다. 이전 버전의 Microsoft Edge 브라우저 데이터는 이 설정에 관계없이 항상 첫 실행 시 자동으로 마이그레이션됩니다. 


## <a name="settings-you-manage"></a>설정 관리

이전에 설명하지 않은 모든 Microsoft Edge 관리 템플릿 프로필을 사용하여 배포할 수 Microsoft Intune. 자세한 내용은 [Configure Microsoft Edge policy settings with Microsoft Intune.](/deployedge/configure-edge-with-intune) Intune의 Microsoft Edge 관리 템플릿에 현재 포함되지 않은 정책을 평가하려면 Intune에서 Windows 10 사용자 지정 설정을 사용할 수 있습니다.

### <a name="enabling-specific-chrome-extensions"></a>특정 Chrome 확장 사용

관리 템플릿은 사용자와 함께 특정 Chrome 확장을 배포하는 Microsoft Intune. 특정 확장 설치 허용의 컴퓨터 구성 > Microsoft Edge > **확장에서 > 수 있습니다.**

### <a name="install-extensions-silently"></a>자동으로 확장 설치

관리 템플릿을 사용하여 사용자에게 알리지 않고 Microsoft Edge 설치하도록 설정할 수도 있습니다. 컴퓨터 구성 및 확장 > Microsoft Edge > 자동으로 > 컨트롤에서 찾을 **수 있습니다.**

### <a name="microsoft-edge-update-policies"></a>Microsoft Edge 업데이트 정책
업데이트가 Microsoft Edge 확인하려면 업데이트 정책을 Microsoft Edge [않습니다.](/deployedge/microsoft-edge-update-policies)

### <a name="other-common-enterprise-policies"></a>기타 일반적인 엔터프라이즈 정책

Microsoft Edge 많은 다른 정책을 제공합니다. 다음은 더 일반적인 몇 가지 사항입니다.
 
- [사이트 목록 Enterprise IE 모드에서 사이트 구성](/deployedge/edge-ie-mode-sitelist)
- [시작, 홈페이지 및 새 탭 페이지 설정 구성](/deployedge/microsoft-edge-policies#startup-home-page-and-new-tab-page)
- [검색 게임 설정 구성](/deployedge/microsoft-edge-policies#allowsurfgame)
- [프록시 서버 설정 구성](/deployedge/microsoft-edge-policies#proxy-server)
