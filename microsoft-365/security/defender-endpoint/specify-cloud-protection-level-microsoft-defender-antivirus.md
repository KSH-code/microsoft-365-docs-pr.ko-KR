---
title: 클라우드 보호의 클라우드 보호 수준을 Microsoft Defender 바이러스 백신
description: 사용자에 대한 클라우드 보호 수준을 Microsoft Defender 바이러스 백신.
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
ms.date: 08/26/2021
ms.reviewer: mkaminska
manager: dansimp
ms.custom: nextgen
ms.technology: mde
ms.openlocfilehash: a7b8214165e80347d6200c755db477b81e430630
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2021
ms.locfileid: "59187403"
---
# <a name="specify-the-cloud-protection-level"></a>클라우드 보호 수준 지정

**적용 대상:**

- [엔드포인트용 Microsoft Defender](/microsoft-365/security/defender-endpoint/)
- Windows Defender 바이러스 백신

클라우드 보호는 기존 Microsoft Defender 바이러스 백신 인텔리전스 업데이트를 통해보다 훨씬 빠르게 끝점에 보호 기능을 제공할 수 있도록 합니다. 그룹 정책(권장) 또는 그룹 정책을 사용하여 클라우드 보호 Microsoft Endpoint Manager 구성할 수 있습니다.

> [!NOTE]
> **높음,** **높음 + 또는** 허용 오차를 선택하면 일부 합법적인 파일이 검색될 수 있습니다.  이 경우 검색된 파일 차단을 해제하거나 검색된 파일에서 해당 검색을 분쟁할 Microsoft 365 Defender 있습니다.

## <a name="use-microsoft-endpoint-manager-to-specify-the-level-of-cloud-protection"></a>클라우드 Microsoft Endpoint Manager 사용하여 클라우드 보호 수준 지정

1. Microsoft Endpoint Manager 관리 센터()로 이동하여 [https://endpoint.microsoft.com](https://endpoint.microsoft.com) 로그인합니다.

2. 끝점 **보안 바이러스 백신**  >  **을 선택 합니다.**

3. 바이러스 백신 프로필을 선택합니다. (아직 프로필이 없는 경우 또는 새 프로필을 만들하려는 경우 에서 장치 제한 설정 [구성을 Microsoft Intune.](/intune/device-restrictions-configure)

4. 속성을 **선택합니다.** 그런 다음 구성 설정 **옆에 있는** 편집 을 **선택합니다.**

5. 클라우드 **보호를 확장하고**  클라우드 제공 보호 수준 목록에서 다음 중 하나를 선택합니다.

    - **높음:** 강력한 수준의 검색을 적용합니다.
    - **High plus:** **높음** 수준을 사용하며 추가 보호 조치를 적용합니다(클라이언트 성능에 영향을 줄 수 있습니다).
    - **허용 오차** 없음: 알 수 없는 모든 실행을 차단합니다.

6. 검토 **+ 저장 을** 선택한 다음 저장 을 **선택 합니다.** 

> [!TIP]
> 도움이 필요하세요? 다음 리소스를 참조하십시오.
> - [구성 Endpoint Protection](/mem/configmgr/protect/deploy-use/endpoint-protection-configure)
> - [Intune에서 끝점 보호 설정 추가](/mem/intune/protect/endpoint-protection-configure)
  

## <a name="use-group-policy-to-specify-the-level-of-cloud-protection"></a>그룹 정책을 사용하여 클라우드 보호 수준 지정

1.  그룹 정책 관리 컴퓨터의 그룹 정책 관리 [콘솔 을 열 수 있습니다.](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))

2. 구성할 그룹 정책 개체를 마우스 오른쪽 단추로 클릭한 다음 편집 **을 선택합니다.**

3.  그룹 정책 **관리 편집기에서** 컴퓨터 구성 **관리**  >  **템플릿으로 이동하십시오.**

4.  트리를   >    >  **MpEngine** Windows 구성 Microsoft Defender 바이러스 백신 확장합니다.

5.  클라우드 보호 수준 **선택 설정을 두 번 클릭하고** 사용으로 **설정합니다.** 보호 수준을 선택합니다.

    - **기본 차단 수준은** 합법적인 파일을 검색할 위험을 늘리지 않고 강력한 검색을 제공합니다.
    - **보통 차단 수준은** 높은 신뢰도 검색을 위한 보통만 제공합니다.
    - **높은 차단 수준은** 클라이언트 성능을 최적화하는 동안 강력한 수준의 검색을 적용하지만 가음성의 가능성이 더 커질 수도 있습니다.
    - **높은 + 차단 수준은** 추가 보호 조치를 적용합니다(클라이언트 성능에 영향을 미치고 가음성의 가능성이 높아질 수 있습니다).
    - **허용 오차 차단 수준이 0이면** 알 수 없는 모든 실행이 차단됩니다.

6. **확인** 을 선택합니다.

7. 업데이트된 그룹 정책 개체를 배포합니다. 그룹 [정책 관리 콘솔 참조](/windows/win32/srvnodes/group-policy)

> [!TIP]
> 그룹 정책 개체를 사용하는지 여부 클라우드에서 번역하는 방법을 참조합니다. 미리 보기에서 그룹 정책 분석을 사용하여 Microsoft Endpoint Manager 그룹 정책 개체를 [분석합니다.](/mem/intune/configuration/group-policy-analytics) 
  
## <a name="see-also"></a>참고 항목

[클라우드 보호를 사용하도록 설정해야 하는 Microsoft Defender 바이러스 백신](why-cloud-protection-should-be-on-mdav.md)
