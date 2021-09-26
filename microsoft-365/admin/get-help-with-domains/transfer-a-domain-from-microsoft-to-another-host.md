---
title: Microsoft에서 다른 호스트로 도메인 전송
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_O365_Setup
ms.custom:
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
description: 'Microsoft에서 다른 등록 기관으로 도메인을 전송하는 단계는 여기에서 찾아야 합니다. '
ms.openlocfilehash: f36203326f3b6cdd6a1b1bcfc52bfcee01ad1a80
ms.sourcegitcommit: aebcdbef52e42f37492a7f780b8b9b2bc0998d5c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2021
ms.locfileid: "59774439"
---
# <a name="transfer-a-domain-from-microsoft-to-another-host"></a>Microsoft에서 다른 호스트로 도메인 전송

Microsoft에서 도메인을 구입한 후 60일 동안 Microsoft 365 다른 등록 기관으로 이전할 수 없습니다.

> [!NOTE]
> _Whois_ 쿼리는 Microsoft에서 구입한   도메인 등록 기관을 와일드 서부 도메인 LLC로 보여줍니다. 그러나 구입한 도메인과 관련하여 Microsoft만 Microsoft 365 합니다.

다음 단계에 따라 Microsoft 365 코드를 확인한 다음 다른 도메인 등록 기관 웹 사이트로 이동하여 새 등록 기관으로 도메인 이름 전송을 설정하세요.

## <a name="transfer-a-domain"></a>도메인 전송

1. 관리 센터에서 도메인   **설정**   >  **로 이동하세요.**

2. 도메인 **페이지에서** 다른 도메인 Microsoft 365 전송할 도메인을 선택하고 상태 확인 을 **선택합니다.**

3. At the top of the page, select **Transfer domain**.

4. 도메인을 **전송할** 위치 선택 페이지에서 다른 등록 **기관을** 선택하고 다음 을 **클릭합니다.**

5. 도메인 전송 **잠금 해제 페이지에서** 도메인에 대한 <잠금 해제를 **_선택하고_ >** 다음 을 **선택합니다.**

6. 도메인 전송 연락처 정보를 확인한 후 다음 을 **선택합니다.**

7. 다음 단계를 진행하기 전에 등록 탭에서 인증 코드를 복사하고 도메인 전송  상태가 잠금 해제로 변경될 때까지 약 30분 정도 기다립니다. 

8. 앞으로 도메인 이름을 관리하려는 도메인 등록 기관의 웹 사이트로 이동하세요. 도메인 전송에 대한 지침을 따르기(웹 사이트에서 도움말 검색). 이는 일반적으로 전송 요금을 지불하고 새 등록 기관에 Authcode를 제공하여 전송을 시작할 수 있도록 하는 것입니다. Microsoft는 전송 요청을 수신한지 확인하기 위해 전자 메일을 보내며 도메인은 5일 이내에 전송됩니다.

    권한 부여 코드  등록 탭은  **** 도메인 페이지의 Microsoft 365.
    
    > [!TIP]
    > .uk 도메인에는 다른 절차가 필요합니다. Microsoft 지원에 문의하고 **IPS** 태그 변경을 요청하여 도메인을 관리할 등록 기관과 일치하게 합니다. 태그가 변경된 후 도메인은 새 등록 기관으로 즉시 전송됩니다. 그런 다음 새 등록 기관과 함께 전송을 완료해야 합니다. 전송 요금을 지불하고 새 등록 기관을 통해 계정에 전송된 도메인을 추가해야 합니다.

9. 전송이 완료되면 새 도메인 등록 기관에서 도메인을 갱신합니다.

10. 프로세스를 완료하려면 관리 센터의 **도메인** 페이지로 돌아가 도메인 전송   **완료를 선택합니다.** 그러면 도메인이 더 이상 Microsoft 365 것으로 표시하고 도메인 구독을 사용하지 않도록 설정됩니다. 테넌트에서 도메인을 제거하지는 못하며 도메인의 기존 사용자 및 사서함에는 영향을 주지 않습니다.

> [!NOTE]
> Microsoft 365 도메인은 조직 간에 이름 서비스 변경 또는 도메인 전송을 Microsoft 365 없습니다. 이러한 등록이 필요한 경우 도메인 등록을 다른 등록 기관으로 전송해야 합니다.
