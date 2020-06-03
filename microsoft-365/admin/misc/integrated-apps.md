---
title: Microsoft 365에서 앱에 대 한 사용자 동의 관리
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
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 7e453a40-66df-44ab-92a1-96786cb7fb34
description: 앱에 대 한 사용자 동의 및 타사 앱이 사용자의 Microsoft 365 정보에 액세스할 수 있도록 설정 하는 방법에 대해 알아봅니다.
ms.openlocfilehash: 955ae9e58c14dbb8012a440ef6c336f44b0760a4
ms.sourcegitcommit: 7bb3d8a93a85246172e2499d6c58c390e46f5bb9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/02/2020
ms.locfileid: "44498320"
---
# <a name="managing-user-consent-to-apps-in-microsoft-365"></a>Microsoft 365에서 앱에 대 한 사용자 동의 관리

이 설정은 사용자가 로그인 하 고 데이터 액세스를 요청 하기 위해 OpenID Connect 및 OAuth 2.0을 사용 하는 앱에 대 한 동의를 제공할 수 있는지 여부를 제어 합니다. 앱은 사용자의 조직 내에서 만들거나 다른 Office 365 조직이 나 타사에서 제공 될 수 있습니다.

이 설정을 켜면 이러한 앱은 사용자에 게 조직의 데이터에 대 한 액세스 권한을 요청 하 고 사용자가 허용할 것인지 선택할 수 있습니다. 이 설정을 해제 한 경우 관리자가 해당 앱에 동의 해야만 사용자가 사용할 수 있습니다. 이 경우 사용자가 차단 된 앱을 사용 하기 위해 관리자 승인 요청을 보낼 수 있도록 Azure 포털에서 관리자 승인 워크플로를 설정 하는 것이 좋습니다.

사용자는 자신이 소유한 앱이 자신의 Office 365 정보에 액세스하는 경우에만 액세스 권한을 부여할 수 있습니다. 다른 사용자의 정보에 대한 액세스 권한은 부여할 수 없습니다.

## <a name="turning-user-consent-on-or-off"></a>사용자 동의 설정 또는 해제
<a name="__toc379982114"> </a>

앱에 대 한 사용자 동의를 설정 하거나 해제 하는 방법은 다음과 같습니다.

1. 관리 센터에서 **Settings** \> **조직 설정**  >  [서비스](https://go.microsoft.com/fwlink/p/?linkid=2053743) 설정 페이지로 이동한 다음 **앱에 대 한 사용자 동의**를 선택 합니다.

2. **앱에 대 한 사용자 동의** 페이지에서 사용자 동의를 설정 하거나 해제 하는 옵션을 선택 합니다.

## <a name="more-info"></a>추가 정보
<a name="__toc379982114"> </a>

Azure active directory에서 승인 설정을 구성 하는 방법에 대 한 자세한 내용을 보려면 [관리자 동의 워크플로 구성을](https://docs.microsoft.com/azure/active-directory/manage-apps/configure-admin-consent-workflow)참조 하세요.

앱에 대 한 사용자 동의를 관리 하는 방법에 대 한 자세한 내용은 [응용 프로그램에 대 한 승인 및 승인 요청 평가](https://docs.microsoft.com/azure/active-directory/manage-apps/manage-consent-requests)를 참조 하세요