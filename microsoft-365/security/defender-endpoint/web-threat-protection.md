---
title: 웹 위협으로부터 조직 보호
description: Microsoft Defender ATP의 웹 보호와 조직을 보호하는 방법에 대해 자세히 알아보습니다.
keywords: 웹 보호, 웹 위협 방지, 웹 검색, 보안, 피싱, 맬웨어, 악용, 웹 사이트, 네트워크 보호, Edge, Internet Explorer, Chrome, Firefox, 웹 브라우저
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: ellevin
author: levinec
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 3376308988213b84bc7badb96ebacdf706d1ca5f
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51071671"
---
# <a name="protect-your-organization-against-web-threats"></a>웹 위협으로부터 조직 보호

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**적용 대상:**
- [엔드포인트용 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>끝점용 Microsoft Defender를 경험하고 싶나요? [무료 평가판에 등록합니다.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-main-abovefoldlink&rtc=1)

웹 위협 방지는 [](web-protection-overview.md) 끝점용 Defender의 웹 보호의 일부입니다. 네트워크 [보호를 사용하여](network-protection.md) 웹 위협으로부터 장치를 보호합니다. 웹 위협 방지는 Microsoft Edge 및 Chrome 및 Firefox와 같은 인기 있는 타사 브라우저와 통합하여 웹 프록시 없이 웹 위협을 중지하고 부재 중이나 사내에서 장치를 보호할 수 있습니다. 웹 위협 방지는 사용자 지정 표시기 목록에서 차단한 사이트뿐만 아니라 피싱 사이트, 맬웨어 벡터, 악용 사이트, 신뢰하지 못하거나 낮은 신뢰도의 사이트에 대한 액세스를 [중지합니다.](manage-indicators.md)

>[!Note]
>장치가 새 고객 표시기를 받는 데 최대 1시간이 걸릴 수 있습니다.

## <a name="prerequisites"></a>필수 구성 요소
웹 보호는 네트워크 보호를 사용하여 Microsoft Edge 및 타사 웹 브라우저에서 웹 검색 보안을 제공합니다.

디바이스에서 네트워크 보호를 켜는 경우:
- Web & Network **Protection에서** 끝점용 Defender 보안 기준을 편집하여 네트워크 보호를 사용하도록 설정한 후 배포하거나 다시 배포합니다. [엔드포인트 보안 기준에 대한 Defender 검토 및 할당에 대해 자세히 알아보시고](configure-machines-security-baseline.md#review-and-assign-the-microsoft-defender-for-endpoint-security-baseline)
- Intune 장치 구성, SCCM, 그룹 정책 또는 MDM 솔루션을 사용하여 네트워크 보호를 켜십시오. [네트워크 보호 사용에 대한 자세한 정보](enable-network-protection.md)  

>[!Note]
>네트워크 보호를 감사 전용으로 설정하면 차단을 사용할 수 없습니다. 또한 Microsoft Edge에서만 악성 및 원치 않는 웹 사이트에 액세스하려는 시도를 감지하고 기록할 수 있습니다.

## <a name="related-topics"></a>관련 항목

- [웹 보호 개요](web-protection-overview.md)
- [웹 위협 방지](web-threat-protection.md)
- [웹 보안 모니터링](web-protection-monitoring.md)
- [웹 위협에 대응](web-protection-response.md)
- [네트워크 보호](network-protection.md)
