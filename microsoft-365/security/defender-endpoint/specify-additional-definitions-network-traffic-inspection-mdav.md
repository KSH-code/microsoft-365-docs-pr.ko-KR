---
title: 네트워크 트래픽 검사에 대한 추가 정의 집합을 Microsoft Defender 바이러스 백신
description: 네트워크 트래픽 검사에 대한 추가 정의 집합을 Microsoft Defender 바이러스 백신.
keywords: Microsoft Defender 바이러스 백신, 맬웨어 방지, 보안, defender, 네트워크 트래픽 검사
search.product: eADQiWindows 10XVcnh
ms.pagetype: security
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.date: 05/07/2021
ms.reviewer: ''
manager: dansimp
ms.custom: nextgen
ms.technology: mde
ms.topic: article
ms.collection: M365-security-compliance
ms.openlocfilehash: 60f2b4b83e46e33769c5e2e3382058354fcd6972
ms.sourcegitcommit: 584445b62cb82218597b62495fb76fcb5b12af9d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2021
ms.locfileid: "59498367"
---
# <a name="specify-additional-definition-sets-for-network-traffic-inspection"></a>네트워크 트래픽 검사에 대한 추가 정의 집합 지정

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**적용 대상:**

- [엔드포인트용 Microsoft Defender](/microsoft-365/security/defender-endpoint/)

그룹 정책을 사용하여 네트워크 트래픽 검사에 대한 추가 정의 집합을 지정할 수 있습니다.

## <a name="use-group-policy-to-specify-additional-definition-sets-for-network-traffic-inspection"></a>그룹 정책을 사용하여 네트워크 트래픽 검사에 대한 추가 정의 집합 지정

1. 그룹 정책 관리 끝점에서 그룹 정책 관리 [콘솔 을 니다.](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))

2. 네트워크 **검사 Windows 구성** \> **Microsoft Defender 바이러스 백신** \> **로 이동하십시오.**

3. 네트워크 트래픽 검사에 대한 추가 정의 **집합 지정을 선택합니다.** 기본적으로 이 정책은 **구성되지 않습니다.로 설정됩니다.**

4. 정책을 편집하려면 정책 설정 **편집 링크를** 선택합니다.

5. 사용 **을** 선택한 다음 옵션 **섹션에서** **표시...를 선택합니다.**

6. 목록에 항목을 추가한 다음 확인 을 **선택합니다.**

   각 항목은 이름-값 쌍으로 나열되어야 합니다. 여기서 이름은 정의 집합 GUID의 문자열 표현입니다. 예를 들어 테스트 보안 인텔리전스를 사용하도록 설정하는 정의 집합 GUID는 으로 `{b54b6ac9-a737-498e-9120-6616ad3bf590}` 정의됩니다. 값은 사용되지 않습니다. 따라서 으로 설정하는 것이 `0` 좋습니다.

7. **확인을** 선택한 다음 업데이트된 그룹 정책 개체를 배포합니다. 그룹 [정책 관리 콘솔을 참조합니다.](/windows/win32/srvnodes/group-policy)

> [!TIP]
> 그룹 정책 개체를 사용하는지 여부 클라우드에서 번역하는 방법을 참조합니다. 미리 보기에서 그룹 정책 분석을 사용하여 Microsoft Endpoint Manager 그룹 정책 개체를 [분석합니다.](/mem/intune/configuration/group-policy-analytics)

## <a name="related-articles"></a>관련 문서

- [Windows 10의 Microsoft Defender 바이러스 백신](microsoft-defender-antivirus-in-windows-10.md)
- [클라우드 제공 보호 사용](enable-cloud-protection-microsoft-defender-antivirus.md)
- [맬웨어 방지 정책을 만들고 배포하는 방법: 클라우드 보호 서비스](/configmgr/protect/deploy-use/endpoint-antimalware-policies#cloud-protection-service)