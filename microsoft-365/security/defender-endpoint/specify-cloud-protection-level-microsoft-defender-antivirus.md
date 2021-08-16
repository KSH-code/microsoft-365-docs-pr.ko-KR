---
title: 클라우드 제공 보호 수준을 Microsoft Defender 바이러스 백신
description: 사용자에 대한 클라우드 제공 보호 수준을 Microsoft Defender 바이러스 백신.
keywords: Microsoft Defender 바이러스 백신, 맬웨어 방지, 보안, Defender, 클라우드, 적극성, 보호 수준
search.product: eADQiWindows 10XVcnh
ms.pagetype: security
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: normal
ms.topic: article
author: denisebmsft
ms.author: deniseb
ms.date: 10/26/2020
ms.reviewer: ''
manager: dansimp
ms.custom: nextgen
ms.technology: mde
ms.openlocfilehash: 6b7ef857e09e01a1a9ba550dc679708c88dfce1751cd2644156ce38d1b8f42c6
ms.sourcegitcommit: a1b66e1e80c25d14d67a9b46c79ec7245d88e045
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "53863490"
---
# <a name="specify-the-cloud-delivered-protection-level"></a>클라우드 제공 보호 수준 지정

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**적용 대상:**

- [엔드포인트용 Microsoft Defender](/microsoft-365/security/defender-endpoint/)

사용자 지정(권장) 또는 그룹 정책을 사용하여 Microsoft Defender 바이러스 백신 클라우드 제공 보호 수준을 Microsoft Endpoint Manager 수 있습니다.

> [!TIP]
> 클라우드 보호는 단순히 클라우드에 저장된 파일에 대한 보호가 아니며, Microsoft Defender 바이러스 백신 클라우드 서비스는 네트워크 및 장치(끝점이라고도 하는)에 업데이트된 보호를 제공하는 메커니즘입니다. 사용자 Microsoft Defender 바이러스 백신 클라우드 보호는 분산된 리소스와 기계 학습을 사용하여 기존 보안 인텔리전스 업데이트보다 훨씬 빠른 속도로 끝점에 보호 기능을 제공합니다. Microsoft Intune Microsoft Endpoint Manager 의 [일부로](/mem/endpoint-manager-overview)Microsoft Endpoint Manager. 


## <a name="use-microsoft-endpoint-manager-to-specify-the-level-of-cloud-delivered-protection"></a>이 Microsoft Endpoint Manager 사용하여 클라우드 제공 보호 수준 지정

1. Microsoft Endpoint Manager 관리 센터()로 이동하여 [https://endpoint.microsoft.com](https://endpoint.microsoft.com) 로그인합니다.

2. 끝점 **보안 바이러스 백신**  >  **을 선택 합니다.**

3. 바이러스 백신 프로필을 선택합니다. (아직 프로필이 없는 경우 또는 새 프로필을 만들하려는 경우 에서 장치 제한 설정 [구성을 Microsoft Intune.](/intune/device-restrictions-configure)

4. 속성을 **선택합니다.** 그런 다음 구성 설정 **옆에 있는** 편집 을 **선택합니다.**

5. 클라우드 **보호를 확장하고**  클라우드 제공 보호 수준 목록에서 다음 중 하나를 선택합니다.

    1. **높음:** 강력한 수준의 검색을 적용합니다.
    2. **High plus:** **높음** 수준을 사용하며 추가 보호 조치를 적용합니다(클라이언트 성능에 영향을 줄 수 있습니다).
    3. **허용 오차** 없음: 알 수 없는 모든 실행을 차단합니다.

6. 검토 **+ 저장 을** 선택한 다음 저장 을 **선택 합니다.** 

> [!TIP]
> 도움이 필요하세요? 다음 리소스를 참조하십시오.
> - [구성 Endpoint Protection](/mem/configmgr/protect/deploy-use/endpoint-protection-configure)
> - [Intune에서 끝점 보호 설정 추가](/mem/intune/protect/endpoint-protection-configure)
  

## <a name="use-group-policy-to-specify-the-level-of-cloud-delivered-protection"></a>그룹 정책을 사용하여 클라우드 제공 보호 수준 지정

1.  그룹 정책 관리 컴퓨터의 그룹 정책 관리 [콘솔 을 열 수 있습니다.](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))

2. 구성할 그룹 정책 개체를 마우스 오른쪽 단추로 클릭한 다음 편집 을 **클릭합니다.**

3.  그룹 정책 **관리 편집기에서** 컴퓨터 구성 **관리**  >  **템플릿으로 이동하십시오.**

4.  트리를   >    >  **MpEngine** Windows 구성 Microsoft Defender 바이러스 백신 확장합니다.

5.  클라우드 보호 수준 **선택 설정을 두 번 클릭하고** 사용으로 **설정합니다.** 보호 수준을 선택합니다.
    - **기본 차단 수준은** 합법적인 파일을 검색할 위험을 늘리지 않고 강력한 검색을 제공합니다.
    - **보통 차단 수준은** 높은 신뢰도 검색을 위한 보통만 제공합니다.
    - **높은 차단 수준은** 클라이언트 성능을 최적화하는 동안 강력한 수준의 검색을 적용하지만 가음성의 가능성이 더 커질 수도 있습니다.
    - **높은 + 차단 수준은** 추가 보호 조치를 적용합니다(클라이언트 성능에 영향을 미치고 가음성의 가능성이 높아질 수 있습니다).
    - **허용 오차 차단 수준이 0이면** 알 수 없는 모든 실행이 차단됩니다.
    
    > [!WARNING]
    > 가능성은 낮지만 이 스위치를 **높음** 또는 **높음 +로** 설정하면 일부 합법적인 파일이 검색될 수 있습니다(해당 검색을 차단 해제하거나 분쟁할 수 있는 옵션이 있는 경우).

6. **확인** 을 클릭합니다.

7. 업데이트된 그룹 정책 개체를 배포합니다. 그룹 [정책 관리 콘솔 참조](/windows/win32/srvnodes/group-policy)

> [!TIP]
> 그룹 정책 개체를 사용하는지 여부 클라우드에서 번역하는 방법을 참조합니다. 미리 보기에서 그룹 정책 분석을 사용하여 Microsoft Endpoint Manager 그룹 정책 개체를 [분석합니다.](/mem/intune/configuration/group-policy-analytics) 
  
## <a name="related-articles"></a>관련 문서

- [Windows 10의 Microsoft Defender 바이러스 백신](microsoft-defender-antivirus-in-windows-10.md)
- [클라우드 제공 보호 사용](enable-cloud-protection-microsoft-defender-antivirus.md)
- [맬웨어 방지 정책을 만들고 배포하는 방법: 클라우드 보호 서비스](/configmgr/protect/deploy-use/endpoint-antimalware-policies#cloud-protection-service)