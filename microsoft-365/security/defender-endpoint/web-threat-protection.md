---
title: 웹 위협으로부터 조직 보호
description: 끝점용 Microsoft Defender의 웹 보호와 조직을 보호하는 방법에 대해 자세히 알아보습니다.
keywords: 웹 보호, 웹 위협 방지, 웹 검색, 보안, 피싱, 맬웨어, 악용, 웹 사이트, 네트워크 보호, Edge, Internet Explorer, Chrome, Firefox, 웹 브라우저
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 90775af14d78092159d2b92736abce56a961416e
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2021
ms.locfileid: "60159177"
---
# <a name="protect-your-organization-against-web-threats"></a>웹 위협으로부터 조직 보호

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**적용 대상:**
- [엔드포인트용 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> 엔드포인트용 Microsoft Defender를 경험하고 싶으신가요? [무료 평가판을 신청하세요.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-main-abovefoldlink&rtc=1)

웹 위협 방지는 [](web-protection-overview.md) 끝점용 Defender의 웹 보호의 일부입니다. 네트워크 [보호를 사용하여](network-protection.md) 웹 위협으로부터 장치를 보호합니다. Chrome 및 firefox와 같은 Microsoft Edge 및 인기 있는 타사 브라우저와 통합하여 웹 위협 방지는 웹 프록시 없이 웹 위협을 중지하고 부재 중이나 사내에서 장치를 보호할 수 있습니다. 웹 위협 방지는 사용자 지정 표시기 목록에서 차단한 사이트뿐만 아니라 피싱 사이트, 맬웨어 벡터, 악용 사이트, 신뢰하지 못하거나 낮은 신뢰도의 사이트에 대한 액세스를 [중지합니다.](manage-indicators.md)

> [!NOTE]
> 디바이스에서 새 사용자 지정 표시기를 받는 데 최대 1시간이 걸릴 수 있습니다.

## <a name="prerequisites"></a>전제 조건

웹 보호는 네트워크 보호를 사용하여 Microsoft Edge 및 타사 웹 브라우저에서 웹 검색 보안을 제공합니다.

디바이스에서 네트워크 보호를 켜는 경우:

- Web & Network **Protection에서** 끝점용 Defender 보안 기준을 편집하여 네트워크 보호를 사용하도록 설정한 후 배포하거나 다시 배포합니다. [엔드포인트 보안 기준에 대한 Defender 검토 및 할당에 대해 자세히 알아보시고](configure-machines-security-baseline.md#review-and-assign-the-microsoft-defender-for-endpoint-security-baseline)
- Intune 장치 구성, SCCM, 그룹 정책 또는 MDM 솔루션을 사용하여 네트워크 보호를 켜십시오. [네트워크 보호 사용에 대한 자세한 정보](enable-network-protection.md)

> [!NOTE]
> 네트워크 보호를 감사 전용으로 설정하면 차단을 사용할 수 없습니다. 또한 사용자 계정에서만 악성 및 원치 않는 웹 사이트에 액세스하려는 시도를 감지하고 Microsoft Edge 있습니다.

## <a name="configure-web-threat-protection"></a>웹 위협 방지 구성

다음 절차에서는 Microsoft Endpoint Manager 관리 센터를 사용하여 웹 위협 방지를 구성하는 방법을 설명합니다.

1. Microsoft Endpoint Manager 관리 센터()로 이동하여 [https://endpoint.microsoft.com](https://endpoint.microsoft.com) 로그인합니다.
 
2. 끝점 **보안 공격** \> **표면 감소를 선택한** 다음 + 정책 만들기 **를 선택 합니다.**

3. 플랫폼(예: Windows 10 **이상)을** 선택하고  웹 보호 프로필을 선택한 다음 만들기를 **선택합니다.** 

4. 기본 **탭에서** 이름과 설명을 지정하고 다음 을 **선택합니다.**

5. 구성 **설정 탭에서** 웹 **보호를** 확장하고 설정을 지정한 후 다음 을 **선택합니다.**

   - 웹 **보호가** **켜져 있도록** 네트워크 보호 사용으로 설정합니다. 또는 네트워크 보호를 감사  모드로 설정하여 해당 환경에서 네트워크 보호가 어떻게 작동할지 볼 수 있습니다. 감사 모드에서 네트워크 보호는 사용자가 사이트 또는 도메인을 방문하는 것을 차단하지는 않지만 검색을 이벤트로 추적합니다. 
   - 잠재적인 피싱 사기 및 악성 소프트웨어로부터 사용자를 보호하려면 다음에 대해 **SmartScreen 필요를 예로 Microsoft Edge 레거시** **로 전환합니다.**
   - 사용자가 잠재적으로 악의적인 사이트에 대한 경고를  무시하지 못하게 방지하기 위해 악성 사이트 액세스 차단을 **예로 설정하세요.**
   - 사용자가 경고를 무시하고 미확인 파일을 다운로드하지 못하게 방지하려면 미확인 파일 다운로드 차단 **tl** 예 를 **설정하십시오.** 

6. 범위 **태그 탭에서** 조직에서 범위 태그를 사용하는 경우 **+** 범위 태그 선택을 선택하고 다음 을 **선택합니다.** 범위 태그를 사용하지 않는 경우 **다음을** 선택 합니다. 범위 태그에 대한 자세한 내용은 [분산 IT에 RBAC(역할](/mem/intune/fundamentals/scope-tags)기반 액세스 제어) 및 범위 태그 사용을 참조합니다.

7. 할당 **탭에서** 웹 보호 정책을 받을 사용자 및 장치를 지정하고 다음 을 **선택합니다.**

8. 검토 **+ 만들기 탭에서** 정책 설정을 검토한 다음 만들기 를 **선택합니다.**

## <a name="related-topics"></a>관련 항목

- [웹 보호 개요](web-protection-overview.md)
- [웹 위협 방지](web-threat-protection.md)
- [웹 보안 모니터링](web-protection-monitoring.md)
- [웹 위협에 대응](web-protection-response.md)
- [네트워크 보호](network-protection.md)
