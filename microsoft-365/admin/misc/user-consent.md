---
title: 앱에서 앱에 대한 사용자 동의 Microsoft 365
f1.keywords:
- CSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
ms.custom:
- AdminSurgePortfolio
- AdminTemplateSet
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 7e453a40-66df-44ab-92a1-96786cb7fb34
description: 앱에 대한 사용자 동의와 타사 앱이 사용자의 앱 정보에 액세스할 수 있도록 앱을 설정하는 Microsoft 365 대해 자세히 알아보습니다.
ms.openlocfilehash: 629e64494c6d72a13c3b155370a8f47505e9fa20
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2021
ms.locfileid: "59186947"
---
# <a name="managing-user-consent-to-apps-in-microsoft-365"></a>앱에서 앱에 대한 사용자 동의 Microsoft 365

이 설정은 사용자가 로그인에 대해 OpenID 커넥트 및 OAuth 2.0을 사용하는 앱에 대해 해당 동의를 부여할 수 있는지 여부와 데이터에 대한 액세스 요청을 허용할지 여부를 제어합니다. 앱은 조직 내에서 만들거나 다른 조직이나 타사에서 Office 365 수 있습니다.

이 설정을 켜면 해당 앱은 사용자에게 조직의 데이터에 액세스할 수 있는 권한을 요청하며 사용자가 이를 허용할지 여부를 선택할 수 있습니다. 이 설정을 끄면 관리자가 해당 앱에 동의해야 사용자가 앱을 사용할 수 있습니다. 이 경우 사용자가 차단된 앱을 사용하기 위한 관리자 승인 요청을 보낼 수 있도록 Azure Portal에서 관리자 동의 워크플로를 설정하는 것이 좋습니다.

사용자는 자신이 소유한 앱이 자신의 Office 365 정보에 액세스하는 경우에만 액세스 권한을 부여할 수 있습니다. 다른 사용자의 정보에 대한 액세스 권한은 부여할 수 없습니다.

## <a name="turning-user-consent-on-or-off"></a>사용자 동의 설정 또는 해제

다음은 앱에 대한 사용자 동의를 설정하거나 해제하는 방법입니다.

1. 관리 센터에서 설정  설정 서비스 페이지로 이동한 다음 앱에 대한 사용자 \>   >  [](https://go.microsoft.com/fwlink/p/?linkid=2053743) **동의를 선택합니다.**

2. 앱에 대한 사용자 동의 **페이지에서** 사용자 동의를 설정하거나 해제하는 옵션을 선택합니다.

## <a name="related-content"></a>관련 콘텐츠 

[관리자 동의 워크플로](/azure/active-directory/manage-apps/configure-admin-consent-workflow) 구성(문서)\
[응용 프로그램에 대한 동의 관리 및 동의](/azure/active-directory/manage-apps/manage-consent-requests) 요청 평가(문서)