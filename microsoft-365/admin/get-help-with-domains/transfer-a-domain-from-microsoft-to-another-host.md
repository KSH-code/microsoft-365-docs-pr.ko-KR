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
- okr_smb
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
description: 'Microsoft에서 다른 등록자에 게 도메인을 전송 하는 단계를 확인 하세요. '
ms.openlocfilehash: 1fb1fa50bd919bddb620a39d9edb46abb6710ba4
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/21/2020
ms.locfileid: "48645278"
---
# <a name="transfer-a-domain-from-microsoft-to-another-host"></a>Microsoft에서 다른 호스트로 도메인 전송

Microsoft에서 도메인을 구매한 후 60에는 Microsoft 365 도메인을 다른 등록 기관으로 전송할 수 없습니다.

> [!NOTE]
> _Whois_   쿼리는 Microsoft의 구매한 도메인 등록 기관을 와일드 서 LLC에 표시 합니다. 그러나 Microsoft 365 구매한 도메인에 대해서만 Microsoft에 연락 해야 합니다.

다음 단계에 따라 Microsoft 365에서 코드를 가져온 다음 다른 도메인 등록 웹 사이트로 이동 하 여 새 등록자에 게 도메인 이름을 전송 하도록 설정 합니다.

## <a name="transfer-a-domain"></a>도메인 전송

1. 관리 센터에서  **설정**   >  **도메인**으로 이동 합니다.

2. **도메인** 페이지에서 다른 도메인 등록자에 게 전송할 Microsoft 365 도메인을 선택한 다음 **상태 확인**을 선택 합니다.

3. 페이지 맨 위에서 **도메인 전송을**선택 합니다.

4. 도메인을 **전송할 위치 선택** 페이지에서 **다른 등록자**를 선택한 후 **다음**을 클릭 합니다.

5. **도메인 잠금 해제** 페이지에서 ** _도메인_ > <에 대 한 전송 잠금 해제**를 선택한 후 **다음**을 선택 합니다.

6. 도메인 전송 연락처 정보를 확인 하 고 **다음**을 선택 합니다.

7. 인증 코드를 복사 하 고 다음 단계를 진행 하기 전에 **등록** 탭에서 도메인 전송 상태를 **전송 잠금 해제** 로 변경할 때까지 30 분 정도 기다립니다.

8. 도메인 이름을 관리 하려는 도메인 등록 기관 웹 사이트로 이동 합니다. 도메인을 전송 하기 위한 지침을 따르세요 (웹 사이트에서 도움말 검색). 이는 일반적으로 요금 양도 비용을 지불 하 고 새 등록 기관에 Authcode를 제공 하 여 전송을 시작할 수 있도록 하는 것을 의미 합니다. Microsoft는 전송 요청을 받았으며 도메인이 5 일 이내에 전송 되는 것을 전자 메일로 받게 됩니다.

    권한 코드 **등록** 탭은 Microsoft 365의  **도메인** 페이지에서 찾을 수 있습니다.
    
    > [!TIP]
    > uk 도메인은 다른 절차를 수행 해야 합니다. Microsoft 지원에 문의 하 여 도메인을 관리 하려는 등록자와 일치 하도록 **Ip 태그 변경** 요청을 전달 합니다. 태그가 변경 되 면 도메인은 즉시 새 등록자에 게 전송 됩니다. 그런 다음 새 등록자와 함께 작업 하 여 전송을 완료 하 고, 전송 요금을 지불 하 고, 새 등록자를 사용 하 여 계정에 전송 된 도메인을 추가할 수 있습니다.

9. 전송이 완료 되 면 새 도메인 등록 기관에서 도메인을 갱신 합니다.

10. 프로세스를 완료 하려면 관리 센터의 **도메인** 페이지로 돌아간 다음  **전체 도메인 전송을**선택 합니다. 이렇게 하면 해당 도메인은 Microsoft 365에서 더 이상 구매한 것으로 표시 되지 않으며 도메인 구독을 사용 하지 않도록 설정 됩니다. 테 넌 트에서 도메인을 제거 하지 않으며, 도메인의 기존 사용자 및 사서함에 영향을 주지 않습니다.

> [!NOTE]
> Microsoft 365 구매한 도메인은 서버 이름 변경 또는 Microsoft 365 조 직 간에 도메인을 전송 하는 데 적합 하지 않습니다. 이러한 두 가지 중 하나가 필요한 경우 도메인 등록을 다른 등록자에 게 전송 해야 합니다.
