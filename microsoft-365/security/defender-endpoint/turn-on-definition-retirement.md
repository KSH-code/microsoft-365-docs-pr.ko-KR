---
title: 에 대한 정의 사용 중지 Microsoft Defender 바이러스 백신
description: 에 대한 정의 사용 중지를 Microsoft Defender 바이러스 백신.
keywords: Microsoft Defender 바이러스 백신, 맬웨어 방지, 보안, defender, 정의 사용 중지
search.product: eADQiWindows 10XVcnh
ms.pagetype: security
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.date: 06/10/2021
ms.reviewer: ''
manager: dansimp
ms.custom: nextgen
ms.technology: mde
ms.topic: article
ms.collection: m365-security-compliance
ms.openlocfilehash: 07248f2945e817dc7bdca6240d1de30830abd1e4
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2021
ms.locfileid: "60207742"
---
# <a name="turn-on-definition-retirement"></a>정의 사용 중지 켜기

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**적용 대상:**

- [엔드포인트용 Microsoft Defender](/microsoft-365/security/defender-endpoint/)

그룹 정책을 사용하여 정의 사용 중지를 구성할 수 있습니다. 정의 사용 중지는 컴퓨터에 특정 취약점으로부터 보호하는 데 필요한 보안 업데이트가 있는지 확인합니다. 시스템이 정의에 의해 검색된 악용에 취약하지 않은 경우 해당 정의는 "사용 중지"됩니다. 특정 프로토콜에 대한 모든 보안 인텔리전스가 사용 중지된 경우 해당 프로토콜은 더 이상 구문 분석하지 않습니다. 이 기능을 사용하도록 설정하면 성능을 개선하는 데 도움이 됩니다. 모든 최신 보안 업데이트가 있는 최신 컴퓨터에서 네트워크 보호는 네트워크 성능에 영향을 끼치지 않습니다.

## <a name="use-group-policy-to-configure-definition-retirement"></a>그룹 정책을 사용하여 정의 사용 중지 구성

1. 그룹 정책 관리 끝점에서 그룹 정책 관리 [콘솔 을 니다.](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))

2. 컴퓨터 구성 **관리** 템플릿 Windows 네트워크 Microsoft Defender 바이러스 백신 \>  \>  \>  \> **시스템으로 이동하십시오.**

3. 정의 **사용 중지 켜기 를 선택합니다.** 기본적으로 이 정책은 사용하도록 설정됩니다. 구성되지 **않은 것으로 설정된 경우** 정의 사용 중지가 사용하도록 설정됩니다.

4. 정책을 편집하려면 정책 설정 **편집 링크를** 선택합니다.

5. 사용 **을** 선택한 다음 확인 을 **선택합니다.**

6. 업데이트된 그룹 정책 개체를 배포합니다. 그룹 [정책 관리 콘솔을 참조합니다.](/windows/win32/srvnodes/group-policy)

> [!TIP]
> 그룹 정책 개체를 사용하는지 여부 클라우드에서 번역하는 방법을 참조합니다. 미리 보기에서 그룹 정책 분석을 사용하여 Microsoft Endpoint Manager 그룹 정책 개체를 [분석합니다.](/mem/intune/configuration/group-policy-analytics)
