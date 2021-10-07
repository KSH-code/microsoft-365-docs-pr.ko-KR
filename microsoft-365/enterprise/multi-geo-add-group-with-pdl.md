---
title: 특정 기본 Microsoft 365 위치로 Microsoft 365 그룹 만들기
ms.reviewer: adwood
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: ITPro
ms.topic: article
ms.service: o365-solutions
f1.keywords:
- NOCSH
ms.collection: Strat_SP_gtc
ms.localizationpriority: medium
description: Multi-geo 환경에서 Microsoft 365 기본 설정 데이터 위치를 사용하여 그룹 그룹을 만드는 방법을 학습합니다.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 05e910d82c44e37497b365a9d0757a80805c895a
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2021
ms.locfileid: "60201604"
---
# <a name="create-a-microsoft-365-group-with-a-specific-preferred-data-location"></a>특정 기본 Microsoft 365 위치로 Microsoft 365 그룹 만들기

다중 위치 환경의 사용자가 Microsoft 365 그룹을 만들면 그룹 기본 설정 데이터 위치(PDL)가 자동으로 사용자의 위치로 설정됩니다. 전역, SharePoint, Exchange 관리자는 선택하는 모든 영역에서 그룹을 만들 수 있습니다. 

특정 PDL로 그룹을 만들어야 할 경우 SharePoint 관리자 센터에서 만들거나 혹은 Exchange Online New-UnifiedGroup Microsoft PowerShell cmdlet을 사용하여 그룹을 만들 수 있습니다. 이 작업을 진행 시 그룹 사서함 및 그룹과 연결된 SharePoint 사이트가 지정된 PDL에서 프로비저닝됩니다.

지정한 PDL로 Microsoft 365 그룹을 만들하려면 그룹 사이트를 만들 지리적 위치의 SharePoint 관리 센터로 이동하십시오.

예시:

호주의 위치에서 그룹 사이트를 만드려는 경우 https://ContosoAUS-admin.sharepoint.com/_layouts/15/online/AdminHome.aspx#/siteManagement로 이동할 수 있습니다.

1. **+ 만들기** 를 선택합니다.
2. 프로세스를 따라 그룹 사이트를 만듭니다.

사이트 만들기 요청을 시작한 SharePoint 관리 센터에 해당하는 지리적 위치에서 그룹 사이트가 프로비저닝됩니다. 

Exchange PowerShell 사용하기 

Exchange Online PowerShell에 연결하고 *MailBoxRegion* 매개 변수를 지리적 위치 코드와 함께 전달합니다.

예: 

```PowerShell
New-UnifiedGroup -DisplayName MultiGeoEUR -Alias "MultiGeoEUR" -AccessType Public -MailboxRegion EUR 
```

![구문을 New-UnifiedGroup PowerShell cmdlet의 스크린샷입니다.](../media/multi-geo-new-group-with-pdl-powershell.png)

SharePoint 그룹 사이트 프로비전은 주문형입니다. 그룹 소유자 또는 구성원이 처음 액세스할 때 사이트가 프로비저닝됩니다.

## <a name="geo-location-codes"></a>지리적 위치 코드

[!INCLUDE [Microsoft 365 Multi-Geo locations](../includes/microsoft-365-multi-geo-locations.md)]

## <a name="related-topics"></a>관련 항목

[Exchange Online PowerShell에 연결](/powershell/exchange/connect-to-exchange-online-powershell)
