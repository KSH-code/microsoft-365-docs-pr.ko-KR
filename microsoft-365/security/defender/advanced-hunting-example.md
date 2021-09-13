---
title: Microsoft Defender for Office 365
description: 고급 헌팅을 사용하여 전자 메일 위협 검색 시작
keywords: 고급 헌팅, 위협 헌팅, 사이버 위협 헌팅, Microsoft 365 Defender, microsoft 365, m365, 검색, 쿼리, 원격 분석, 사용자 지정 감지, schema, kusto
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: d3ac49b4afde0951e7a034c5c11114afbc52c293
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2021
ms.locfileid: "59185707"
---
# <a name="advanced-hunting-example-for-microsoft-defender-for-office-365"></a>Microsoft Defender for Office 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**적용 대상:**
- Microsoft 365 Defender

고급 검색을 사용하여 전자 메일 위협 검색을 시작하고 싶으세요? 다음 방법을 사용해 보세요.

[Office 365용 Microsoft Defender](/microsoft-365/security/office-365-security/defender-for-office-365#getting-started) 문서의 [시작](/microsoft-365/security/office-365-security/defender-for-office-365) 섹션에는 다음과 같은 논리적 초기 구성 덩어리가 있습니다.

1. 이름에 'Anti'가 있는 모든 것을 구성합니다.
   - 맬웨어 방지
   - 피싱 방지
   - 스팸 방지
2. 이름에 '금고'로 모든 것을 설정합니다.
   - 안전한 링크
   - 안전한 첨부 파일
3. 작업을 방어할 때 (예: SharePoint 온라인, OneDrive 및 Teams).
4. 제로 아워 자동 제거로 보호합니다.

[링크](../office-365-security/protect-against-threats.md)를 통해 바로 시작하여 첫날에 구성을 시작하세요.

**시작** 의 마지막 단계는 ZAP라고도 하는 **제로 아워 자동 제거** 를 사용해 사용자를 보호하는 것입니다. 배달 후에 의심스러운 메일이나 악의적인 메일에 대한 제로 아워 자동 제거가 성공적이었는지 알아보는 것은 매우 중요할 수 있습니다.

Kusto 쿼리 언어로 빠르게 검색하여 문제를 검색할 수 있다는 점은 이러한 두 보안 센터의 수렴한 이점입니다. 보안 팀은 헌팅 고급 헌팅에서 다음  단계를 수행하여 ZAP 누락을 [](https://security.microsoft.com/advanced-hunting) \> **모니터링할 수 있습니다.**

1. 고급 헌팅 페이지에서 쿼리를 **클릭합니다.**
1. 다음 쿼리를 쿼리 창에 복사합니다.
1. **쿼리 실행** 을 선택합니다.

```kusto
EmailPostDeliveryEvents 
| where Timestamp > ago(7d)
//List malicious emails that were not zapped successfullyconverge-2-endpoints-new.png
| where ActionType has "ZAP" and ActionResult == "Error"
| project ZapTime = Timestamp, ActionType, NetworkMessageId , RecipientEmailAddress 
//Get logon activity of recipients using RecipientEmailAddress and AccountUpn
| join kind=inner IdentityLogonEvents on $left.RecipientEmailAddress == $right.AccountUpn
| where Timestamp between ((ZapTime-24h) .. (ZapTime+24h))
//Show only pertinent info, such as account name, the app or service, protocol, the target device, and type of logon
| project ZapTime, ActionType, NetworkMessageId , RecipientEmailAddress, AccountUpn, 
LogonTime = Timestamp, AccountDisplayName, Application, Protocol, DeviceName, LogonType
```

:::image type="content" source="../../media/converge-13-advanced-hunt-an-email-zap-new.png" alt-text="쿼리 패널 맨 위에 선택된 쿼리가 있는 고급 헌팅 페이지(헌팅 아래)를 표시하고 Kusto 쿼리를 실행하여 지난 7일 동안의 ZAP 작업을 캡처합니다.":::

이 쿼리의 데이터는 쿼리 자체 아래에 있는 결과 패널에 나타납니다. 결과에는 사용자 지정 가능한 결과 집합의 'DeviceName', 'AccountDisplayName', 'ZapTime' 같은 정보가 포함됩니다. 레코드에 대한 결과를 내보낼 수도 있습니다. 쿼리가 다시 필요하면 **저장** > **다른 이름으로 저장** 을 선택하고 쿼리 목록, 공유 또는 커뮤니티 쿼리에 쿼리를 추가합니다.

## <a name="related-information"></a>관련 정보
- [고급 헌팅 모범 사례](advanced-hunting-best-practices.md)
- [개요 - 고급 헌팅](advanced-hunting-overview.md)
