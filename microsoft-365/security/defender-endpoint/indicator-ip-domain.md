---
title: IP 및 URL/도메인에 대한 지표 만들기
ms.reviewer: ''
description: 엔터티의 검색, 방지 및 제외를 정의하는 IP 및 URL/도메인에 대한 표시기를 만들 수 있습니다.
keywords: ip, url, domain, manage, allowed, blocked, clean, malicious, file hash, ip address, urls, domain
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
ms.openlocfilehash: e7dc11fe709a6d04b6309706df90f0ebbc177e25
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/08/2021
ms.locfileid: "52841069"
---
# <a name="create-indicators-for-ips-and-urlsdomains"></a>IP 및 URL/도메인에 대한 지표 만들기 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**적용 대상:**
- [엔드포인트용 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)



> [!TIP]
> Endpoint용 Defender를 경험하고 싶나요? [무료 평가판에 등록합니다.](https://www.microsoft.com/en-us/WindowsForBusiness/windows-atp?ocid=docs-wdatp-automationexclusionlist-abovefoldlink)


Endpoint용 Defender는 Microsoft 브라우저용 Windows Defender SmartScreen 및 Microsoft가 아닌 다른 브라우저 또는 브라우저 외부에서 걸린 통화에 대한 네트워크 보호를 통해 Microsoft가 악성 IP/URL로 생각되는 것을 차단할 수 있습니다.

이 위협 인텔리전스 데이터 집합은 Microsoft에서 관리합니다.

이제 자신의 위협 인텔리전스를 기반으로 하여 IPS, URL 또는 도메인을 허용하거나 차단할 수 있습니다. 특정 그룹이 다른 그룹보다 위험에 더 높거나 적은 것으로 생각되는 경우 설정 페이지 또는 컴퓨터 그룹을 통해 이 작업을 할 수 있습니다.

> [!NOTE]
> IP 주소에 Inter-Domain CIDR(Classless Inter-Domain Routing) 상용화는 지원되지 않습니다. 

### <a name="before-you-begin"></a>시작하기 전에
IPS, URL 또는 도메인에 대한 표시기를 만들기 전에 다음의 선행 구성 요소에 대해 이해하는 것이 중요합니다.
- URL/IP 허용 및 차단은 차단 모드에서 사용하도록 설정하기 위해 끝점 구성 요소 네트워크 보호에 대한 Defender를 사용합니다. 네트워크 보호 및 구성 지침에 대한 자세한 내용은 네트워크 보호 사용 [을 참조하세요.](enable-network-protection.md)
- 맬웨어 방지 클라이언트 버전은 4.18.1906.x 이상입니다. 
- 버전 1709 Windows 10 컴퓨터의 경우 지원됩니다. 
- 고급 **기능 에서** 사용자 지정 **네트워크 표시기가 Microsoft Defender 보안 센터 > 설정 > 확인합니다.** 자세한 내용은 고급 기능을 [참조하세요.](advanced-features.md)
- iOS의 지표 지원은 사용자 지정 표시기 [구성을 참조합니다.](/microsoft-365/security/defender-endpoint/ios-configure-features#configure-custom-indicators)


> [!IMPORTANT]
> 외부 IP만 표시기 목록에 추가할 수 있습니다. 내부 IP에 대한 표시기를 만들 수 없습니다.
> 웹 보호 시나리오의 경우 기본 제공 기능을 사용하는 것이 Microsoft Edge. Microsoft Edge [보호를](network-protection.md) 활용하여 네트워크 트래픽을 검사하고 TCP, HTTP 및 HTTPS(TLS)에 대한 블록을 허용합니다. 충돌하는 URL 표시기 정책이 있는 경우 더 긴 경로가 적용됩니다. 예를 들어 URL 표시기 정책이 URL 표시기 정책보다 `https:\\support.microsoft.com/en-us/office` `https:\\support.microsoft.com` 우선합니다.

> [!NOTE]
> 다른 모든 프로세스에서 웹 보호 시나리오는 검사 및 적용을 위해 네트워크 보호를 활용합니다. 
> - 세 가지 프로토콜 모두에 대해 IP가 지원됩니다.
> - 단일 IP 주소만 지원됩니다(CIDR 블록 또는 IP 범위 없음).
> - 암호화된 URL(전체 경로)은 첫 번째 브라우저에서만 차단할 수 있습니다(Internet Explorer, Edge).
> - 암호화된 URL(FQDN만 해당)은 자사 브라우저 외부에서 차단할 수 있습니다(Internet Explorer, Edge).
> - 전체 URL 경로 블록을 도메인 수준 및 암호화되지 않은 모든 URL에 적용할 수 있습니다.
 
> [!NOTE]
> 작업을 수행한 시간과 차단되는 URL 및 IP 사이에 최대 2시간의 대기 시간이 있을 수 있습니다(일반적으로 적음). 

### <a name="create-an-indicator-for-ips-urls-or-domains-from-the-settings-page"></a>설정 페이지에서 IPS, URL 또는 도메인에 대한 표시기 만들기

1. 탐색 창에서 **표시기 설정**  >  **선택합니다.**  

2. IP 주소 **또는 URL/도메인 탭을** 선택합니다.

3. 항목 **추가를 선택합니다.**

4. 다음 세부 정보를 지정합니다.
   - Indicator - 엔터티 세부 정보를 지정하고 표시기 만료를 정의합니다.
   - 작업 - 수행될 작업을 지정하고 설명을 입력합니다.
   - 범위 - 컴퓨터 그룹의 범위를 정의합니다.

5. 요약 탭에서 세부 정보를 검토한 다음 저장을 **클릭합니다.**

## <a name="related-topics"></a>관련 항목
- [지표 만들기](manage-indicators.md)
- [파일에 대한 지표 만들기](indicator-file.md)
- [인증서를 기반으로 표시기 만들기](indicator-certificates.md)
- [지표 관리](indicator-manage.md)
