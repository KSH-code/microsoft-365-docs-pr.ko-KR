---
title: 피싱 전자 메일 공격의 예
description: 피싱 공격의 예제 분석을 진행합니다.
keywords: 인시던트, 경고, 조사, 상관 관계, 공격, 컴퓨터, 장치, 사용자, IDs, ID, 사서함, 전자 메일, 365, microsoft, m365
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: c675486652e25e832685218caefe869739681e25
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2021
ms.locfileid: "60196756"
---
# <a name="example-of-a-phishing-email-attack"></a>피싱 전자 메일 공격의 예

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**적용 대상:**
- Microsoft 365 Defender

Microsoft 365 Defender 전자 메일을 통해 배달된 악의적인 첨부 파일을 감지하는 데 도움이 될 수 있습니다. Office 365 및 규정 준수 [센터는](https://protection.office.com/) Microsoft 365 Defender 통합되어 보안 분석가가 전자 메일 첨부 파일과 같은 보안 Office 365 위협을 볼 수 있습니다.

예를 들어 분석가에게 다단계 인시던트가 할당된 경우를 예로 들 수 있습니다.
 
:::image type="content" source="../../media/first-incident-path-phishing/first-incident-phishing-incident.png" alt-text="다단계 인시던트의 예"::: 

**인시던트의 경고** 탭에 경고 및 이벤트에 대한 Office 365 Microsoft Cloud App Security 표시됩니다. 분석가가 전자 메일 메시지 경고를 선택하여 Office 365 대한 Defender로 드릴다운할 수 있습니다. 경고의 세부 정보는 왼쪽 창에 표시됩니다.

:::image type="content" source="../../media/first-incident-path-phishing/first-incident-phishing-alerts.png" alt-text="전자 메일 경고의 예":::
 
아래로 스크롤하면 추가 정보가 표시되어 영향을 미치게 된 악성 파일과 사용자를 표시합니다.

:::image type="content" source="../../media/first-incident-path-phishing/first-incident-phishing-impact.png" alt-text="전자 메일 경고의 사용자 및 파일에 미치는 영향의 예":::
  
경고 **열기 페이지를 선택하면** 링크를 선택하여 다양한 정보를 보다 자세히 볼 수 있는 특정 경고로 이동됩니다. 탐색기에서 패널 아래쪽에 있는  메시지 보기를 선택하여 실제 전자 메일 메시지를 볼 수 있습니다.
 
:::image type="content" source="../../media/first-incident-path-phishing/first-incident-phishing-event-explorer.png" alt-text="경고 세부 정보의 예입니다."::: 

이 경우 분석가가 전자 메일 제목, 받는 사람, 보낸 사람 및 기타 정보가 표시되는 위협 관리 페이지로 이동합니다. 특수 작업 **아래에 있는** **ZAP는** 분석가에게 제로 아워 자동 제거 기능이 구현되었다고 알 수 있습니다. ZAP는 조직 전체의 사서함에서 악성 및 스팸 메시지를 자동으로 감지하고 제거합니다. 자세한 내용은 에서 [제로 아워 ZAP(자동 제거)를 Exchange Online.](../office-365-security/zero-hour-auto-purge.md)

작업을 선택하여 특정 메시지에 대해 다른 작업을 수행할 **수 있습니다.** 
 
:::image type="content" source="../../media/first-incident-path-phishing/first-incident-phishing-actions.png" alt-text="다른 작업의 예는 전자 메일 메시지에 대해 수행할 수 있습니다."::: 

## <a name="next-step"></a>다음 단계

ID 기반 [공격 조사 경로를](first-incident-path-identity.md) 참조합니다.

## <a name="see-also"></a>참고 항목

- [사고 개요](incidents-overview.md)
- [사고 조사](investigate-incidents.md)
- [인시던트 관리](manage-incidents.md)
