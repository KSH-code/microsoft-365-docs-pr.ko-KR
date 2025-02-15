---
title: OneDrive 및 SharePoint Online의 Multi-Geo 기능
ms.reviewer: adwood
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: ITPro
ms.topic: article
ms.service: o365-solutions
f1.keywords:
- NOCSH
ms.custom: ''
ms.collection:
- Strat_SP_gtc
- SPO_Content
- m365solution-scenario
- m365solution-spintranet
ms.localizationpriority: medium
ms.assetid: 094e86f2-9ff0-40ac-af31-28fcaba00c1d
description: OneDrive Online의 Multi-Geo 기능으로 여러 지리적 지역으로 Microsoft 365 범위를 확장합니다.
ms.openlocfilehash: 52bdbeddec29879e5f985dd1dff64db0d04b8072
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2021
ms.locfileid: "60189036"
---
# <a name="multi-geo-capabilities-in-onedrive-and-sharepoint-online"></a>OneDrive 및 SharePoint Online의 Multi-Geo 기능

OneDrive 및 SharePoint Online의 Multi-Geo 기능을 사용하면 SharePoint 팀 사이트 및 Microsoft 365 저장되어 있는 그룹 사서함과 같은 공유 리소스를 제어할 수 있습니다.

각 사용자, 그룹 사서함 및 SharePoint 사이트에는 관련 데이터가 저장되는 지리적 위치를 나타내는 기본 설정 데이터 위치(PDL)가 있습니다. 사용자의 개인 데이터(Exchange 사서함 및 OneDrive)는 물론 생성한 Microsoft 365 그룹 또는 SharePoint 사이트가 데이터 상주 요건 충족을 위해 특정 지리적 위치에 저장될 수 있습니다. [각 지리적 위치에 대해 다른 관리자를 지정](add-a-sharepoint-geo-admin.md)할 수 있습니다.

사용자는 Office 응용 프로그램, OneDrive 및 검색을 포함한 Microsoft 365 서비스를 사용할 때 원활한 환경을 이용합니다. 자세한 내용은 [Multi-Geo 환경의 사용자 작업 환경](multi-geo-user-experience.md)을 참조하세요.

## <a name="onedrive"></a>OneDrive

각 사용자의 OneDrive는 사용자의 PDL에 따라 위성 위치로 프로비저닝 또는 [관리자 이동](move-onedrive-between-geo-locations.md)이 가능합니다. 개인 파일은 해당 지리적 위치에 보관됩니다. 단, 다른 지리적 위치의 사용자와 공유할 수 있습니다.

## <a name="sharepoint-sites-and-groups"></a>SharePoint 사이트 및 그룹

SharePoint Online 관리 센터에서 Multi-Geo 기능 관리를 이용할 수 있습니다. 자세한 내용은 [해당 블로그 게시물](https://techcommunity.microsoft.com/t5/Office-365-Blog/Now-available-Multi-Geo-in-SharePoint-and-Office-365-Groups/ba-p/263302)을 참조하세요.

사용자가 다중 지역 환경에서 SharePoint 그룹 연결 사이트를 생성할 때 사용자의 PDL은 사이트 및 관련 그룹 사서함이 생성되는 지리적 위치를 결정하는 데 사용됩니다. (사용자의 PDL 값이 설정되지 않았거나 위성 위치로 구성되지 않은 지리적 위치로 설정된 경우 사이트 및 사서함은 중앙 위치에 생성됩니다.)

Microsoft 365, Exchange, OneDrive, SharePoint 및 Teams 서비스는 Multi-Geo가 아닌 서비스입니다. 그러나 이러한 Microsoft 365 만든 그룹은 생성자의 PDL 및 해당 Exchange 그룹 사서함으로 구성됩니다SharePoint 사이트는 해당 지역으로 프로비전됩니다. 

## <a name="managing-the-multi-geo-environment"></a>다중 지역 환경 관리

다중 지역 환경 설정 및 관리는 SharePoint 관리 센터를 통해 이루어집니다. 

![SharePoint 관리 센터의 지리적 위치 SharePoint 스크린샷.](../media/sharepoint-multi-geo-admin-center.png)

(SharePoint 사이트 또는 OneDrive 사이트 이동과 같은 일부 작업은 Microsoft PowerShell을 필요로 합니다.)

## <a name="see-also"></a>참고 항목

[SharePoint 및 Microsoft 365 그룹의 다중 Multi-Geo](https://techcommunity.microsoft.com/t5/Office-365-Blog/Now-available-Multi-Geo-in-SharePoint-and-Office-365-Groups/ba-p/263302)

[다중 지역 환경 관리](administering-a-multi-geo-environment.md)

[다중 지역 환경에서 SharePoint 저장소 할당량](sharepoint-multi-geo-storage-quota.md)

[Multi-Geo 환경에서 Exchange Online 사서함 관리](administering-exchange-online-multi-geo.md)
