---
title: 2013에서 SharePoint 업그레이드
ms.author: serdars
author: serdarsoysal
manager: serdars
ms.date: 11/10/2021
audience: ITPro
ms.topic: conceptual
ms.prod: sharepoint-server-itpro
ms.collection:
- Ent_O365
search.appverid:
- MET150
f1.keywords:
- NOCSH
description: SharePoint Server 2013 및 SharePoint Foundation 2013에서 업그레이드할 정보 및 리소스를 찾아보는 것이 좋습니다. 두 가지 모두에 대한 지원은 2023년 4월 11일까지입니다.
ms.openlocfilehash: 05f545b67d60d6bcc45587049e49a5f5c1f6d654
ms.sourcegitcommit: 16e3a6e6df253de1153e46d058941cd9a2bbf2b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/10/2021
ms.locfileid: "60889926"
---
# <a name="upgrading-from-sharepoint-2013"></a>2013에서 SharePoint 업그레이드

Microsoft SharePoint Server 2013 및 SharePoint Foundation 2013은 **2023년 4월 11일 지원이 종료될 예정입니다.** 이 문서에서는 기존 SharePoint Server 데이터를 SharePoint Online으로 마이그레이션하거나 Microsoft 365 2013 환경의 SharePoint 업그레이드하는 데 도움이 되는 리소스를 제공합니다. 이 문서의 나머지부분에서는 SharePoint 2013을 사용하여 SharePoint Server 2013 및 SharePoint Foundation 2013을 참조합니다.

## <a name="what-is-end-of-support"></a>지원이 *종료된 것은 무엇입니까?*

대부분의 Microsoft 제품에는 새로운 기능, 버그 수정, 보안 수정 등 지원 수명 주기가 있습니다. 지원 종료 날짜가 지난 후 제품 작동이 중지되지 않지만 Microsoft는 더 이상 다음을 제공하지 않습니다.

- 발생할 수 있는 문제에 대한 기술 지원

- 서버의 안정성과 사용 가능성에 영향을 줄 수 있는 문제에 대한 버그 수정

- 서버가 보안 위반에 취약해질 수 있는 취약점에 대한 보안 수정

- 표준 시간대 업데이트.

즉, 제품에 대한 추가 업데이트, 패치 또는 수정이 없습니다(보안 패치/수정 포함). Microsoft 지원은 지원 노력을 최신 버전으로 완전히 전환할 것입니다.

> [!NOTE]
> 소프트웨어 수명 주기는 일반적으로 초기 릴리스부터 5년 동안의 일반 지원 기간 동안 지속됩니다. 최대 5년의 추가 지원을 추가로 지원할 수 있습니다. [Microsoft 솔루션 공급자를](https://go.microsoft.com/fwlink/?linkid=841249) 사용하면 다음 버전의 소프트웨어로 업그레이드하거나 소프트웨어 또는 소프트웨어로 Microsoft 365 수 있습니다. 중요한 기술에 대한 지원 종료 날짜를 알고 있는지, 특히 Microsoft SQL Server 사용중인 기술에 대한 지원 종료 날짜를 알고 SharePoint. 자세한 내용은 [고정 수명 주기 정책을 참조하세요.](https://support.microsoft.com/help/14085)

## <a name="plan-ahead"></a>미리 계획

SharePoint [Server 2013](/lifecycle/products/sharepoint-server-2013) 및 SharePoint Foundation [2013의](/lifecycle/products/sharepoint-foundation-2013)제품 수명 주기 사이트에서 지원이 종료되는 날짜를 확인 합니다. 이러한 날짜를 염두에 두어 업그레이드 또는 마이그레이션을 계획합니다. 제품이 나열된 날짜에 *작동을* 중지하지 않습니다. 그러나 해당 날짜 이후에는 설치가 더 이상 패치되지 않습니다. 따라서 제품의 다음 버전으로의 매끄러운 전환을 계획할 수 있습니다. 아래 표에는 사용 가능한 옵션이 나열됩니다.

|지원 제품 종료|좋음|더 나은|가장 적합한|
|---|---|---|---|
|SharePoint Server 2013<BR>SharePoint Foundation 2013|SharePoint Server 2016 또는 2019로 업그레이드|SharePoint Server 구독 버전 업그레이드|마이그레이션을 SharePoint Microsoft 365

## <a name="whats-next"></a>다음 작업

마이그레이션을 통해 SharePoint Microsoft 365 최신 공동 작업, 인텔리전스 및 보안 솔루션을 활용하는 것이 Microsoft 365. 2016의 최신 환경 Microsoft 365 능동적이고, 유연하며, 능동적으로 디자인되었습니다.

프레미스 SharePoint 배포를 유지 관리해야 하는 경우 하이브리드 배포를 통해 마이그레이션할 수 있는 SharePoint 기능의 양을 SharePoint Microsoft 365. 하이브리드 SharePoint 대해 [알아보고](/sharepoint/hybrid/hybrid) 계획하기 위해 하이브리드를 참조합니다.

### <a name="migrate-to-sharepoint-in-microsoft-365"></a>마이그레이션을 SharePoint Microsoft 365

SPMT(SharePoint 마이그레이션 도구)를 사용하여 사이트 및 콘텐츠를 SharePoint 마이그레이션할 Microsoft 365. 미리 계획하고, 마이그레이션을 수행하고, 발생될 수 있는 문제를 해결하는 데 도움이 될 수 있는 광범위한 콘텐츠 라이브러리가 있습니다. [마이그레이션 SharePoint 개요를](/sharepointmigration/introducing-the-sharepoint-migration-tool) 시작하는 것이 좋습니다.

### <a name="upgrade-to-sharepoint-server-subscription-edition"></a>SharePoint Server 구독 버전 업그레이드

SharePoint 2013에서 Subscription Edition으로 업그레이드하는 직접 경로가 없는 경우에도 여전히 두 번째 최상의 옵션입니다. 주된 이유는 SharePoint Server Subscription Edition에는 새로운 주 버전의 SharePoint 릴리스할 필요가 없어진 지속적인 업데이트 모델이 도입되고 있습니다.

Subscription Edition으로 업그레이드하려면 Server 2016 또는 2019에서 SharePoint 실행해야 합니다. 또한 SharePoint 2013에서 2019까지 직접 경로가 아니기 때문에 2016으로 먼저 업그레이드한 다음 Subscription Edition으로 업그레이드하는 것이 가장 좋습니다. Subscription Edition으로의 업그레이드에 대한 자세한 내용을 알아보고 계획하려면 아래 링크를 참조하세요.

- [SharePoint Server 2016으로 업그레이드](/sharepoint/upgrade-and-update/upgrade-to-sharepoint-server-2016)
- [SharePoint Server 구독 버전 업그레이드](/sharepoint/upgrade-and-update/upgrade-to-sharepoint-server-subscription-edition)

SharePoint 배포를 유지 관리해야 하는 경우에도 사이트 또는 콘텐츠의 일부를 Microsoft 365 하이브리드 구현으로 마이그레이션하여 SharePoint [](/sharepoint/hybrid/hybrid) 최신 공동 작업 환경, 보안 및 규정 준수 기능을 Microsoft 365.  

### <a name="upgrade-to-sharepoint-server-2016-or-2019"></a>SharePoint Server 2016 또는 2019로 업그레이드

2013에 대한 지원이 종료된 후 SharePoint 배포를 유지 관리하는 경우 SharePoint Server 2016 및 2019가 모두 지원되는 플랫폼입니다. 그러나 두 **버전 모두 2026년 7월 14일** 지원이 종료됩니다. 즉, 2013에 대한 지원 날짜가 종료된 후 3년 이내에 다른 업그레이드를 계획해야 합니다. 다음은 두 제품에 대한 지원 수명 주기 페이지입니다.

- [SharePoint Server 2016 지원 수명 주기 날짜](/lifecycle/products/sharepoint-server-2016)
- [SharePoint Server 2019 지원 기간 날짜](/lifecycle/products/sharepoint-server-2019)

자세한 내용을 알아보고 업그레이드를 계획하려면 다음 문서를 참조합니다.

- [SharePoint Server 2016으로 업그레이드](/sharepoint/upgrade-and-update/upgrade-to-sharepoint-server-2016)
- [SharePoint Server 2019로 업그레이드](/sharepoint/upgrade-and-update/upgrade-to-sharepoint-server-2019)

SharePoint 배포를 유지 관리해야 하는 경우에도 사이트 또는 콘텐츠의 일부를 Microsoft 365 하이브리드 구현으로 마이그레이션하여 SharePoint [](/sharepoint/hybrid/hybrid) 최신 공동 작업 환경, 보안 및 규정 준수 기능을 Microsoft 365.  
