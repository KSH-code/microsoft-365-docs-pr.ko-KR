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
- Adm_TOC
- Adm_O365_Setup
ms.custom:
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
description: '여기에 있는 단계를 찾아 Microsoft에서 다른 등록 기관으로 도메인을 전송합니다. '
ms.openlocfilehash: f34e9733ab53c8bdc6f4432c96e6232ecc26ee06
ms.sourcegitcommit: eac5d9f759f290d3c51cafaf335a1a1c43ded927
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "50126350"
---
# <a name="transfer-a-domain-from-microsoft-to-another-host"></a>Microsoft에서 다른 호스트로 도메인 전송

Microsoft에서 도메인을 구입한 후 60일 동안 Microsoft 365 도메인을 다른 등록 기관으로 이전할 수 없습니다.

> [!NOTE]
> _Whois 쿼리는_ Microsoft에서 구입한   도메인 등록 기관을 와일드 서부 도메인 LLC로 보여줍니다. 그러나 Microsoft 365 구입 도메인과 관련하여 Microsoft에만 문의해야 합니다.

다음 단계에 따라 Microsoft 365에서 코드를 다운로드한 다음 다른 도메인 등록 기관 웹 사이트로 이동하여 새 등록 기관으로 도메인 이름 전송을 설정하세요.

## <a name="transfer-a-domain"></a>도메인 전송

1. 관리 센터에서 설정   ****   >  **도메인으로 이동합니다.**

2. 도메인 **페이지에서** 다른 도메인 등록 기관으로 전송할 Microsoft 365 도메인을 선택한 다음 상태 **확인을 선택합니다.**

3. At the top of the page, select **Transfer domain**.

4. 도메인 전송 **위치** 선택 페이지에서 다른 등록 **기관을** 선택하고 다음을 **클릭합니다.**

5. 도메인 전송 **잠금 해제** 페이지에서 도메인에 대한 <잠금 **_해제를_ >** 선택하고 다음을 **선택합니다.**

6. 도메인 전송 연락처 정보를 확인한 후 다음을 **선택합니다.**

7. 다음 단계를 진행하기 전에 인증 코드를 복사하고 도메인 전송  상태가 등록 탭에서 전송될 수 있도록 잠금 해제로 변경될 때까지 약 30분 정도 기다립니다. 

8. 앞으로 도메인 이름을 관리하려는 도메인 등록 기관의 웹 사이트로 이동하세요. 도메인 전송에 대한 지침을 따르기(웹 사이트에서 도움말 검색). 이는 일반적으로 전송 요금을 지불하고 새 등록 기관에 Authcode를 제공하여 전송을 시작할 수 있도록 하는 것입니다. Microsoft는 전송 요청을 수신한지 확인하기 위해 전자 메일을 보내며 도메인은 5일 이내에 전송됩니다.

    Microsoft 365의 도메인  **** 페이지에서 인증 코드 등록 탭을 찾을 수 있습니다. 
    
    > [!TIP]
    > .uk 도메인에는 다른 절차가 필요합니다. Microsoft 지원에 문의하여 도메인을 관리할 등록 기관과 일치하게 **IPS** 태그 변경을 요청합니다. 태그가 변경된 후 도메인은 즉시 새 등록 기관으로 전송됩니다. 그런 다음 새 등록 기관과 함께 전송을 완료해야 합니다. 전송 요금을 지불하고 새 등록 기관을 통해 전송된 도메인을 계정에 추가합니다.

9. 전송이 완료되면 새 도메인 등록 기관에서 도메인을 갱신합니다.

10. 프로세스를 완료하려면 관리 센터의 **도메인** 페이지로 돌아가 도메인 전송   **완료를 선택합니다.** 이렇게 하면 도메인이 Microsoft 365에서 더 이상 구입되지 않았다고 표시하고 도메인 구독을 사용하지 않도록 설정됩니다. 테넌트에서 도메인이 제거되지는 않을 뿐만 아니라 도메인의 기존 사용자 및 사서함에 영향을 주지 않습니다.

> [!NOTE]
> 구입한 Microsoft 365 도메인은 이름 서비스 변경 또는 Microsoft 365 조직 간에 도메인을 전송할 수 없습니다. 이러한 등록 중 하나만 필요한 경우 도메인 등록을 다른 등록 기관으로 전송해야 합니다.
