---
title: Mac의 끝점용 Microsoft Defender
ms.reviewer: ''
description: Mac에서 끝점용 Microsoft Defender를 설치, 구성, 업데이트 및 사용하는 방법을 학습합니다.
keywords: microsoft, defender, Endpoint용 Microsoft Defender, mac, 설치, 배포, 제거, intune, jamf, macos, big sur, catalina, mojave, mac용 mde
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: ab3405022dac71843ecd4e8b630d3738fe69fcaa
ms.sourcegitcommit: e5de03d4bd669945fec0d25a3f5eae56f86c9dcc
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/01/2021
ms.locfileid: "60043086"
---
# <a name="microsoft-defender-for-endpoint-on-mac"></a>Mac의 끝점용 Microsoft Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**적용 대상:**
- [엔드포인트용 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> 엔드포인트용 Microsoft Defender를 경험하고 싶으신가요? [무료 평가판을 신청하세요.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

이 항목에서는 Mac에서 끝점용 Defender를 설치, 구성, 업데이트 및 사용하는 방법을 설명합니다.

> [!CAUTION]
> Mac에서 끝점용 Microsoft Defender와 함께 다른 타사 끝점 보호 제품을 실행하면 성능 문제와 예측할 수 없는 부작용이 발생할 수 있습니다. 사용자 환경에서 비 Microsoft 끝점 보호가 절대적인 요구 사항이면 수동 모드에서 실행될 바이러스 백신 기능을 구성한 후에도 Mac용 끝점용 Defender를 EDR 기능을 안전하게 활용할 [수 있습니다.](mac-preferences.md#enable--disable-passive-mode)

## <a name="whats-new-in-the-latest-release"></a>최신 릴리스의 새로운 소식

[엔드포인트용 Microsoft Defender의 새로운 기능](whats-new-in-microsoft-defender-atp.md)

[Mac의 끝점용 Microsoft Defender의 새로운](mac-whatsnew.md)

> [!TIP]
> 공유하고자 하는 피드백이 있는 경우 장치의 Mac에서 끝점용 Microsoft Defender를 열고 피드백  보내기 도움말로 를 확인하여 \> **제출합니다.**

미리 보기 기능(예: Mac 장치에 대한 끝점 감지 및 응답)을 비롯한 최신 기능을 얻기 위해 끝점용 Microsoft Defender를 실행하는 macOS 장치를 "Insider" 장치로 구성합니다.

## <a name="how-to-install-microsoft-defender-for-endpoint-on-mac"></a>Mac에 끝점용 Microsoft Defender를 설치하는 방법

### <a name="prerequisites"></a>필수 구성 요소

- 끝점용 Defender 구독 및 Microsoft 365 Defender 포털 액세스
- macOS 및 BASH 스크립팅의 초보자 수준 환경
- 디바이스의 관리 권한(수동 배포의 경우)

### <a name="installation-instructions"></a>설치 지침

Mac에서 끝점용 Defender를 설치하고 구성하는 데 사용할 수 있는 몇 가지 방법 및 배포 도구가 있습니다.

- 타사 관리 도구:
    - [Microsoft Intune 기반 배포](mac-install-with-intune.md)
    - [JAMF 기반 배포](mac-install-with-jamf.md)
    - [기타 MDM 제품](mac-install-with-other-mdm.md)

- 명령줄 도구:
    - [수동 배포](mac-install-manually.md)

### <a name="system-requirements"></a>시스템 요구 사항

macOS의 가장 최근 주요 릴리스 3개가 지원됩니다.

> [!IMPORTANT]
> macOS 11(Big Sur)에서는 끝점용 Microsoft Defender에 추가 구성 프로필이 필요합니다. 이전 버전의 macOS에서 업그레이드하는 기존 고객인 경우 MacOS 카탈로리나 및 최신 [버전의 macOS용](mac-sysext-policies.md)새 구성 프로필에 나열된 추가 구성 프로필을 배포해야 합니다.

> [!IMPORTANT]
> MacOS 10.13(High Sierra)에 대한 지원은 2021년 2월 15일부터 중단됩니다.

- 11(빅 수르), 10.15(카탈리나), 10.14(모자베)
- 디스크 공간: 1GB

MacOS의 베타 버전은 지원되지 않습니다.

M1 칩 기반 프로세서가 있는 macOS 장치에 대한 지원은 에이전트 버전 101.40.84 이후 공식적으로 지원되었습니다.

서비스를 사용하도록 설정한 후 네트워크 또는 방화벽에서 해당 서비스 및 끝점 간의 아웃바운드 연결을 허용하도록 구성해야 할 수 있습니다.

### <a name="licensing-requirements"></a>라이선스 요구사항

Mac의 끝점용 Microsoft Defender에는 다음 Microsoft 볼륨 라이선싱 제품 중 하나가 필요합니다.

- Microsoft 365 E5(M365 E5)
- Microsoft 365 E5 Security
- Microsoft 365 A5(M365 A5)
- Windows 10 Enterprise E5
- 끝점용 Microsoft Defender

> [!NOTE]
> 적격 라이선스 사용자는 최대 5개의 동시 장치에서 끝점용 Microsoft Defender를 사용할 수 있습니다.
> Microsoft Defender for Endpoint는 CSP(Microsoft Defender for Endpoint)에서 클라우드 솔루션 공급자 사용할 수 있습니다. CSP를 통해 구매한 경우 나열된 Microsoft 볼륨 라이선스 제품은 필요하지 않습니다.

### <a name="network-connections"></a>네트워크 연결

다음 다운로드 가능한 스프레드시트에는 네트워크에서 연결할 수 있어야 하는 서비스 및 관련 URL이 나열됩니다. 이러한 URL에 대한 액세스를 거부하는 방화벽 또는 네트워크 필터링 규칙이 없는지 또는 해당 URL에 대한 허용 규칙을 만들어야 할 수도 있습니다. 

|도메인 목록의 스프레드시트|설명|
|---|---|
|![끝점 URL 스프레드시트용 Microsoft Defender의 축소판 이미지입니다.](images/mdatp-urls.png)|서비스 위치, 지리적 위치 및 OS에 대한 특정 DNS 레코드의 스프레드시트입니다. <p> 여기에서 스프레드시트를 [다운로드합니다.mdatp-urls.xlsx. ](https://download.microsoft.com/download/8/a/5/8a51eee5-cd02-431c-9d78-a58b7f77c070/mde-urls.xlsx)

끝점용 Microsoft Defender는 다음 검색 방법을 사용하여 프록시 서버를 검색할 수 있습니다.

- PAC(프록시 자동 구성)
- WPAD(웹 프록시 자동 검색 프로토콜)
- 수동 정적 프록시 구성

프록시 또는 방화벽에서 익명 트래픽을 차단하는 경우 이전에 나열된 URL에서 익명 트래픽이 허용되어 있는지 확인

> [!WARNING]
> 인증된 proxies는 지원되지 않습니다. PAC, WPAD 또는 정적 프록시만 사용 중이지 않습니다.
>
> 보안상의 이유로 SSL 검사 및 가로채기 Proxies도 지원되지 않습니다. MacOS용 끝점용 Microsoft Defender의 데이터를 가로채지 않고 관련 URL로 직접 전달하도록 SSL 검사 및 프록시 서버에 대한 예외를 구성합니다. 전역 저장소에 가로채기 인증서를 추가하면 가로채는 것을 허용하지 않습니다.

연결이 차단되지 않는지 테스트하기 위해 브라우저에서 <https://x.cp.wd.microsoft.com/api/report> <https://cdn.x.cp.wd.microsoft.com/ping> 열립니다.

명령줄을 원하는 경우 터미널에서 다음 명령을 실행하여 연결을 확인할 수도 있습니다.

```bash
curl -w ' %{url_effective}\n' 'https://x.cp.wd.microsoft.com/api/report' 'https://cdn.x.cp.wd.microsoft.com/ping'
```

이 명령의 출력은 다음과 유사해야 합니다.

 `OK https://x.cp.wd.microsoft.com/api/report`

 `OK https://cdn.x.cp.wd.microsoft.com/ping`

> [!CAUTION]
> 클라이언트 장치에서 SIP(시스템 무결성 [보호)를](https://support.apple.com/HT204899) 사용하도록 설정하는 것이 좋습니다. SIP는 OS에 대한 낮은 수준의 변조를 방지하는 기본 제공 macOS 보안 기능으로, 기본적으로 사용하도록 설정됩니다.

Endpoint용 Microsoft Defender가 설치되면 터미널에서 다음 명령을 실행하여 연결의 유효성을 검사할 수 있습니다.

```bash
mdatp connectivity test
```

## <a name="how-to-update-microsoft-defender-for-endpoint-on-mac"></a>Mac에서 끝점용 Microsoft Defender를 업데이트하는 방법

Microsoft는 성능, 보안을 개선하고 새로운 기능을 제공하기 위해 소프트웨어 업데이트를 정기적으로 게시합니다. Mac에서 끝점용 Microsoft Defender를 업데이트하기 위해 MAU(Microsoft 자동 업데이트)라는 프로그램이 사용됩니다. 자세한 내용은 Mac에서 [끝점용 Microsoft Defender 업데이트 배포를 참조하세요.](mac-updates.md)

## <a name="how-to-configure-microsoft-defender-for-endpoint-on-mac"></a>Mac에서 끝점용 Microsoft Defender를 구성하는 방법

엔터프라이즈 환경에서 제품을 구성하는 방법에 대한 지침은 [Mac의 끝점용 Microsoft Defender](mac-preferences.md)기본 설정에서 사용할 수 있습니다.

## <a name="macos-kernel-and-system-extensions"></a>macOS 커널 및 시스템 확장

MacOS의 진화에 맞춰 커널 확장 대신 시스템 확장을 활용하는 Mac에서 끝점용 Microsoft Defender 업데이트를 준비하고 있습니다. 관련 세부 정보는 [Mac의 끝점용 Microsoft Defender의 새로운 내용을 참조합니다.](mac-whatsnew.md)

## <a name="resources"></a>리소스

- 로깅, 지우기 또는 기타 항목에 대한 자세한 내용은 [Mac의 끝점용 Microsoft Defender 리소스를 참조하세요.](mac-resources.md)
- [Mac의 끝점용 Microsoft Defender에 대한 개인 정보 .](mac-privacy.md)
