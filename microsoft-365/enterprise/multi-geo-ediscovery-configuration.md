---
title: Microsoft 365 Multi-Geo eDiscovery 구성
ms.reviewer: adwood
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: ITPro
ms.topic: article
ms.service: o365-solutions
f1.keywords:
- NOCSH
ms.custom: seo-marvel-apr2020
localization_priority: Normal
ms.collection: Strat_SP_gtc
description: Region 매개 변수를 사용하여 Multi-Geo의 위성 위치에서 사용하도록 eDiscovery를 Microsoft 365 방법을 학습합니다.
ms.openlocfilehash: 4d3481fe8b72bb970893ce065293a7a2cc717331
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2021
ms.locfileid: "59210675"
---
# <a name="microsoft-365-multi-geo-ediscovery-configuration"></a>Microsoft 365 Multi-Geo eDiscovery 구성

[Advanced eDiscovery](../compliance/overview-ediscovery-20.md) 기능을 사용하면 Multi-Geo eDiscovery 관리자가 "지역" 보안 필터를 활용하지 않고도 모든 지역을 검색할 수 있습니다. 데이터는 다중 위치 테넌트의 중앙 위치의 Azure 인스턴스로 내보낼 수 있습니다. 

고급 eDiscovery 기능이 없는 경우 다중 위치 테넌트의 eDiscovery 관리자 또는 관리자는 해당 테넌트의 중앙 위치에서만 eDiscovery를 수행 할 수 있습니다. 위성 위치에 대한 eDiscovery 수행 기능을 지원하기 위해 PowerShell을 통해 "Region"이라는 새로운 준수 보안 필터 매개 변수를 사용할 수 있습니다. 이 매개 변수는 중앙 위치가 북미, 유럽 또는 아시아 태평양에 있는 테넌트에서 사용할 수 있습니다. Advanced eDiscovery 중앙 위치가 북미, 유럽 또는 아시아 태평양에 있지 않은 테넌트와 위성 지리적 위치에서 eDiscovery를 수행해야 하는 테넌트에 권장됩니다. 

Microsoft 365 전역 관리자는 다른 사용자들이 eDiscovery를 수행할 수 있도록 하기 위해 eDiscovery 관리자 권한을 할당해야 하며, 해당 준수 보안 필터에서 “Region” 매개 변수를 할당하여 eDiscovery 수행 지역을 위성 위치로 지정해야 합니다. 그렇지 않으면 해당 위성 위치에 대해 eDiscovery가 수행되지 않습니다.

특정 위성 위치에 대해 eDiscovery 관리자(manager) 또는 관리자(administrator) 역할이 설정되면 해당 eDiscovery 관리자(manager) 또는 관리자(administrator)만 해당 위성 위치에 있는 SharePoint 사이트 및 OneDrive 사이트에 대해 eDiscovery 검색 작업을 수행할 수 있습니다. eDiscovery 관리자(manager) 또는 관리자(administrator)가 지정된 위성 위치 외부의 SharePoint 또는 OneDrive 사이트를 검색하려고 하면 결과가 반환되지 않습니다. 또한 지역에 대한 eDiscovery 관리자(manager) 또는 관리자(administrator)가 내보내기를 트리거할 경우 데이터가 해당 지역의 Azure 인스턴스로 내보내집니다. 이를 통해 제어 경계 너머로 콘텐츠가 내보내지지 않게 되므로 조직은 준수 상태를 유지할 수 있습니다.

> [!NOTE]
> eDiscovery 관리자가 여러 SharePoint 위성 위치에 걸쳐 검색해야 할 경우 OneDrive 또는 SharePoint 사이트가 있는 대체 위성 위치를 지정하는 eDiscovery 관리자에 대해 다른 사용자 계정을 만들어야 합니다.

[!INCLUDE [Microsoft 365 Multi-Geo locations](../includes/microsoft-365-multi-geo-locations.md)]

지역에 대한 준수 보안 필터를 설정하려면

1. [Microsoft 365 보안 및 준수 센터 PowerShell에 연결](/powershell/exchange/connect-to-scc-powershell)

2. 다음 구문을 사용합니다.

   ```powershell
   New-ComplianceSecurityFilter -Action All -FilterName <TheNameYouWantToAssign> -Region <RegionValue> -Users <UserPrincipalName>
   ```

   예시는 다음과 같습니다:

   ```powershell
   New-ComplianceSecurityFilter -Action All -FilterName "NAM eDiscovery Managers" -Region NAM -Users adwood@contoso.onmicrosoft.com
   ```

추가 매개 변수 및 구문에 대해서는 [New-ComplianceSecurityFilter](/powershell/module/exchange/new-compliancesecurityfilter) 문서를 참조하세요.