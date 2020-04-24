---
title: Office 365에 도메인 추가
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: mnirkhe
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365_Setup
- Adm_O365
- Adm_TOC
ms.custom:
- TopSMBIssues
- SaRA
- MSStore_Link
- okr_smb
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 6383f56d-3d09-4dcb-9b41-b5f5a5efd611
description: DNS 호스트에서 DNS 레코드를 추가 하 여 Microsoft 365 관리 센터에서 Office 365에 도메인을 추가 합니다. 설치 마법사가 프로세스를 안내 합니다.
ms.openlocfilehash: a77526efc526073e17b535612213202ad22d5657
ms.sourcegitcommit: 72e43b9bf85dbf8f5cf2040ea6a4750d6dc867c9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/24/2020
ms.locfileid: "43800026"
---
# <a name="add-a-domain-to-office-365"></a>Office 365에 도메인 추가

 원하는 정보를 찾지 못한 경우 **[도메인 FAQ를 확인](domains-faq.md)** 하세요. 
  
 *도메인을 추가, 수정 또는 제거 하려면 [비즈니스 또는 기업 계획](https://products.office.com/business/office)의 **전역 관리자** **여야 합니다** . 이러한 변경 내용은 전체 테 넌 트에 영향을 미치며 *사용자 지정 된 관리자* 또는 *일반 사용자* 는 이러한 변경 작업을 수행할 수 없습니다.*  

 도메인을 추가, 설정 또는 계속 하려면 다음 단계를 수행 합니다. 

::: moniker range="o365-worldwide"
  
::: moniker-end

::: moniker range="o365-germany"

> [!VIDEO https://www.microsoft.com/videoplayer/embed/dda6df6d-37b0-41ff-905b-089448355a31?autoplay=false]
  
::: moniker-end

::: moniker range="o365-worldwide"

1. <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> 의 관리 센터로 이동합니다.

::: moniker-end
::: moniker range="o365-germany"

1. <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">https://portal.office.de/adminportal</a> 의 관리 센터로 이동합니다.

::: moniker-end

::: moniker range="o365-21vianet"

1. <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">https://portal.partner.microsoftonline.cn</a> 의 관리 센터로 이동합니다.

::: moniker-end
    
2. **도메인** **설정** > 페이지로 이동 합니다. 

3. **도메인 추가**를 선택 합니다.
    
4. 추가 하려는 도메인의 이름을 입력 하 고 **다음**을 선택 합니다.
    
5. 도메인을 소유 하 고 있는지 확인 하는 방법을 선택 합니다.
    
    1. 도메인이 godaddy&amp;또는 1 1에 등록 되어 있으면**다음** **로그인** > 을 선택 하 고 Microsoft[에서 레코드를 자동으로 설정](../get-help-with-domains/domain-connect.md)합니다.
    
    2. 도메인에 대해 등록된 연락처로 확인 코드가 포함된 전자 메일을 받을 수 있습니다. 알 수 없거나 기록 된 전자 메일에 대 한 액세스 권한이 있는 경우 세 번째 옵션을 사용 하면 됩니다.
    
    3. TXT 레코드를 사용하여 도메인을 확인할 수 있습니다. 이를 선택 하 고 **다음** 을 선택 하 여 등록자의 웹 사이트에이 DNS 레코드를 추가 하는 방법에 대 한 지침을 확인 합니다. 이 작업은 레코드를 추가한 후 확인 하는 데 최대 30 분까지 걸릴 수 있습니다. 
    
6. Office에서 도메인을 사용 하는 데 필요한 DNS 변경 작업을 수행 하는 방법을 선택 합니다.
    
    1. Office에서 DNS를 자동으로 구성 하도록 하려면 **dns 레코드 추가** 를 선택 합니다. 
    
  
    2. 특정 Office 365 서비스만 도메인에 연결 하거나 지금 건너뛰고 나중에이 작업을 수행 하려는 경우에 **는 직접 DNS 레코드를 추가** 합니다 .를 선택 합니다. **무엇을 할지 정확히 아는 경우에만 이 옵션을 선택하세요.**
    
7. *DNS 레코드를 직접 추가* 하도록 선택한 경우에는 **다음** 을 선택 하 고 도메인을 설정 하기 위해 등록 기관 웹 사이트에 추가 해야 하는 모든 레코드가 포함 된 페이지를 볼 수 있습니다. 
    
  
  
    포털에서 등록 기관을 인식하지 못하는 경우에는 [이러한 일반 지침을 따르면](../get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md) 됩니다.
    
    호스트를 찾으려면 [호스트 별 지침](https://support.office.com/article/ae950c9e-e8d9-4108-b0cb-449156998580) 목록을 확인하고 다음 단계에 따라 필요한 모든 레코드를 추가합니다. 
    
    사용 중인 도메인의 DNS 호스팅 공급자 또는 도메인 등록 기관을 모르는 경우 [도메인 등록자 또는 DNS 호스팅 공급자 찾기](../get-help-with-domains/find-your-domain-registrar.md)를 참조하세요.
    
    나중에 기다리도록 하려면 맨 아래로 스크롤한 다음 **이 단계 건너뛰기를**선택 합니다.
    
8. **완료** 를 선택 합니다. 

## <a name="add-or-edit-custom-dns-records"></a>사용자 지정 DNS 레코드 추가 또는 편집

아래 단계에 따라 웹 사이트 또는 타사 서비스에 대 한 사용자 지정 레코드를 추가 합니다.

1. 에서 <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>Microsoft 관리 센터에 로그인 합니다.

2. **설정**  > **도메인** 페이지로 이동 합니다.

3. **도메인** 페이지에서 도메인을 선택합니다. 
    
4. **DNS 설정**에서 **사용자 지정 레코드**를 선택 합니다. 그런 다음 **새 사용자 지정 레코드**를 선택 합니다.

5. 추가할 DNS 레코드 유형을 선택 하 고 새 레코드에 대 한 정보를 입력 합니다.
    
6. **저장**을 선택합니다.

## <a name="registrars-with-domain-connect"></a>도메인 연결을 사용 하는 등록 기관

[도메인 연결](https://www.domainconnect.org/) 사용 등록 기관는 3 단계 프로세스에서 분 단위로 Microsoft 365에 도메인을 추가할 수 있도록 합니다. 
  
이 마법사에서는 도메인을 소유 하 고 있는지 확인 하 고, 사용자의 도메인 레코드를 자동으로 설정 하 여 전자 메일이 Microsoft 365 및 기타 Microsoft 365 서비스 (예를 들어, 사용자의 도메인으로 작업)를 제공 합니다.
  
> [!NOTE]
> 설정 마법사를 시작하기 전에 브라우저의 팝업 차단 기능을 해제하세요.
  
### <a name="domain-connect-registrars-integrating-with-microsoft-365"></a>도메인 연결 등록 기관 Microsoft 365 통합

- [1&amp;1GB 이상 os](https://www.1and1.com/)
- [123Reg](https://www.123-reg.co.uk/)
- [GoDaddy](https://www.godaddy.com/)
- [WordPress](https://wordpress.com/)
- [Plesk](https://www.plesk.com/)
- [MediaTemple](https://mediatemple.net/)
- SecureServer 또는 WildWestDomains (SecureServer DNS 호스팅을 사용 하는 GoDaddy 리셀러)
    - [MadDog 도메인](https://www.maddogdomains.com/)
    - [CheapNames](https://www.cheapnames.com)

### <a name="what-happens-to-my-email-and-website"></a>전자 메일 및 웹 사이트는 어떻게 되나요?

설치를 마친 후에는 도메인에 대 한 MX 레코드가 Microsoft 365를 가리키도록 업데이트 되 고 도메인의 모든 전자 메일이 Microsoft 365로 시작 됩니다. 해당 도메인에서 전자 메일을 받는 모든 사용자에 대해 Office 365에서 사용자를 추가하고 사서함을 설정했는지 확인합니다.
  
업무에 사용하는 웹 사이트가 있는 경우 어디에 있든 작동이 유지됩니다. 도메인 연결 설정 단계는 웹 사이트에 영향을 주지 않습니다.

## <a name="related-articles"></a>관련 문서

[도메인 FAQ](domains-faq.md)

[도메인이 무엇인가요?](../get-help-with-domains/what-is-a-domain.md)

[Office 365에서 도메인 이름 구입](../get-help-with-domains/buy-a-domain-name.md)

[도메인 설정(호스트별 지침)](../get-help-with-domains/set-up-your-domain-host-specific-instructions.md)

[도메인 도움말 보기](../get-help-with-domains/get-help-with-domains.md)
