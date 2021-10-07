---
title: 웹에서 Outlook에서 사서함을 찾을 수 없는 오류 발생
f1.keywords:
- CSH
ms.author: pebaum
author: pebaum
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: high
ms.collection:
- M365-subscription-management
ms.custom:
- AdminTemplateSet
- admindeeplinkMAC
ROBOTS: NOINDEX, NOFOLLOW
search.appverid:
- MET150
ms.assetid: 7e453a40-66df-44ab-92a1-96786cb7fb34
description: '**사서함을 찾을 수 없음** 오류는 웹에서 Outlook에 연결하는 데 사용한 계정에 Exchange Online 라이선스가 없음을 의미합니다.'
ms.openlocfilehash: a83219dbd22446d210d59b2c8613915129ecc1cb
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2021
ms.locfileid: "60167981"
---
# <a name="getting-a-mailbox-not-found-error-in-outlook-on-the-web"></a>웹용 Outlook에서 사서함을 찾을 수 없음 오류가 발생하나요?

웹용 Outlook을 사용 중이고 **사서함을 찾을 수 없음** 오류가 표시되는 경우 웹용 Outlook에 연결하는 데 사용한 계정에 Exchange Online 라이선스가 없으므로 , 계정과 연결된 사서함이 없는 것입니다. 

## <a name="assign-a-license-to-your-account"></a>계정에 라이선스 할당

관리자는 다음 단계에 따라 계정에 라이선스를 할당할 수 있습니다.

1. [Microsoft 365 관리 센터](https://admin.microsoft.com/adminportal/home#/homepage)를 열고 **사용자** 섹션 아래의 **활성 사용자** 로 이동하여 오류가 표시되는 사용자를 선택합니다.
1. 열리는 사용자 페이지에서 **라이선스 및 앱** 섹션으로 이동하여 적절한 **위치** 값을 선택하고 Exchange Online이 포함된 라이선스를 할당합니다(세부 정보를 보려면 라이선스를 확장). 
1. 작업을 마쳤으면 **변경 내용 저장** 을 클릭합니다.

## <a name="related-content"></a>관련 콘텐츠

[사용자의 다른 전자 메일 별칭 추가](../email/add-another-email-alias-for-a-user.md)(문서)\
[Microsoft 365에서 전자 메일 전달 구성](../email/configure-email-forwarding.md)(문서)\
[공유 사서함 만들기](../email/create-a-shared-mailbox.md)(문서)