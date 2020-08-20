---
title: Microsoft 365에 도메인 추가
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
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 6383f56d-3d09-4dcb-9b41-b5f5a5efd611
description: DNS 호스트에서 DNS 레코드를 추가하여 Microsoft 365 관리 센터에서 Microsoft 365에 도메인을 추가합니다. 설정 마법사가 프로세스를 안내합니다.
ms.openlocfilehash: 0adf8b4dcd5d7bd31038b74a574f449f32bfb037
ms.sourcegitcommit: 167c05cc6a776f62f0a0c2de5f3ffeb68c4a27ac
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/19/2020
ms.locfileid: "46814435"
---
# <a name="add-a-domain-to-microsoft-365"></a>Microsoft 365에 도메인 추가

::: moniker range="o365-21vianet"

> [!NOTE]
> 관리 센터가 변경되고 있습니다. 사용자의 환경이 여기에 설명된 세부 정보와 맞지 않는 경우에는 [새 Microsoft 365 관리 센터 정보](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet)를 참조하세요.

::: moniker-end

 원하는 정보를 찾지 못한 경우 **[도메인 FAQ를 확인](domains-faq.md)** 하세요. 
  
 *도메인을 추가, 수정 또는 제거하려면 **비즈니스** **또는 엔터프라이즈** 계획의 [전역 관리자입니다.](https://products.office.com/business/office) 이러한 변경 내용은 전체 테넌트, 사용자 *지정된 관리자 또는* *일반* 사용자에 영향을 주지 않습니다.*  

 이러한 단계에 따라 도메인을 추가하거나 설정하거나 계속합니다. 

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
    
2. 설정 도메인 **페이지로**  >  **이동합니다.** 

3. 도메인 **추가를 선택합니다.**
    
4. 추가할 도메인의 이름을 입력한 후 다음을 **선택합니다.**
    
5. 도메인을 소유하고 있는지 확인하는 방법을 선택합니다.
    
    1. 도메인이 GoDaddy 또는 1 1 1에 등록되어 있는 &amp; 경우 **다음 로그인을**  >  **선택하면** [Microsoft에서 레코드를 자동으로 설정합니다.](../get-help-with-domains/domain-connect.md)
    
    2. 도메인에 대해 등록된 연락처로 확인 코드가 포함된 전자 메일을 받을 수 있습니다. 인식되지 않거나 기록된 전자 메일에 액세스할 수 없는 경우 세 번째 옵션을 사용할 수 있습니다.
    
    3. TXT 레코드를 사용하여 도메인을 확인할 수 있습니다. Select this and select **Next** to see instructions for how to add this DNS record to your registrar's website. 레코드를 추가한 후 확인하는 데 최대 30분이 걸릴 수 있습니다. 
    
6. Office에서 도메인을 사용하려면 필요한 DNS 변경 방법을 선택합니다.
    
    1. Office에서 **DNS를 자동으로 구성하도록** 하려면 하려면 내 DNS 레코드 추가를 선택합니다. 
    
  
    2. 특정 Microsoft 365 **서비스만 도메인에 연결하거나** 지금은 이 단계를 건너뛰고 나중에 수행하려는 경우 DNS 레코드를 자신에게 추가하세요. **무엇을 할지 정확히 아는 경우에만 이 옵션을 선택하세요.**
    
7. DNS 레코드를  *자체적으로 추가하도록 선택한*  경우 다음을 선택하면 **다음을** 선택한 다음 도메인을 설정하기 위해 등록 기관 웹 사이트에 추가해야 하는 모든 레코드가 포함된 페이지가 표시됩니다. 
    
  
  
    포털에서 등록 기관을 인식하지 못하는 경우에는 [이러한 일반 지침을 따르면](../get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md) 됩니다.
    
    호스트를 찾으려면 [호스트 별 지침](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/set-up-your-domain-host-specific-instructions) 목록을 확인하고 다음 단계에 따라 필요한 모든 레코드를 추가합니다. 
    
    사용 중인 도메인의 DNS 호스팅 공급자 또는 도메인 등록 기관을 모르는 경우 [도메인 등록자 또는 DNS 호스팅 공급자 찾기](../get-help-with-domains/find-your-domain-registrar.md)를 참조하세요.
    
    나중에 기다리려면 맨 아래로 스크롤하고 이 단계건 **건너뜁니다.**
    
8. **마침** - 모두 마침을 선택하면 완료되었습니다! 

## <a name="add-or-edit-custom-dns-records"></a>사용자 지정 DNS 레코드 추가 또는 편집

아래 단계에 따라 웹 사이트 또는 타사 서비스에 대한 사용자 지정 레코드를 추가합니다.

1. Microsoft 관리 센터에 <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> 로그인합니다.

2. 설정 도메인 **페이지로**   >  **이동합니다.**

3. **도메인** 페이지에서 도메인을 선택합니다. 
    
4. **DNS 설정 아래에서**사용자 **지정 레코드 선택** 그런 다음 새 **사용자 지정 레코드를 선택합니다.**

5. 추가할 DNS 레코드 유형을 선택하고 새 레코드의 정보를 입력합니다.
    
6. **저장**을 선택합니다.

## <a name="registrars-with-domain-connect"></a>도메인 연결 등록자

[도메인 연결을](https://www.domainconnect.org/) 활성화한 등록자를 사용하면 3단계를 통해 몇 분만 에온 3단계 프로세스에서 Microsoft 365에 도메인을 추가할 수 있습니다. 
  
마법사에서 사용자가 도메인을 소유하고 있다는 사후 자동으로 도메인의 레코드를 설정하므로 Microsoft 365 및 기타 Microsoft 365 서비스(예: Teams)가 사용자의 도메인으로 작동합니다.
  
> [!NOTE]
> 설정 마법사를 시작하기 전에 브라우저의 팝업 차단 기능을 해제하세요.
  
### <a name="domain-connect-registrars-integrating-with-microsoft-365"></a>Microsoft 365에 도메인 연결 등록 등록 기관 통합

- [1 &amp; 1 IONOS](https://www.1and1.com/)
- [123Reg](https://www.123-reg.co.uk/)
- [Cloudflare](https://www.cloudflare.com/)
- [GoDaddy](https://www.godaddy.com/)
- [WordPress](https://wordpress.com/)
- [Plesk](https://www.plesk.com/)
- [MediaTemple](https://mediatemple.net/)
- SecureServer 또는 WildWestDomains(SecureServer DNS 호스팅을 사용하는 GoDaddy 재판매인)
    - [MadDog 도메인](https://www.maddogdomains.com/)
    - [CheapNames](https://www.cheapnames.com)

### <a name="what-happens-to-my-email-and-website"></a>내 전자 메일 및 웹 사이트는 어떻게 되나요?

설정이 완료되면 도메인의 MX 레코드가 Microsoft 365를 가리키도록 업데이트되고 도메인의 모든 전자 메일이 Microsoft 365로 추가됩니다. 해당 도메인에서 전자 메일을 받는 모든 사용자에 대해 Microsoft 365에서 사용자를 추가하고 사서함을 설정해야 합니다.
  
업무에 사용하는 웹 사이트가 있는 경우 어디에 있든 작동이 유지됩니다. 도메인 연결 설정 단계는 사용자 웹 사이트에 영향을 주지 않습니다.

## <a name="related-articles"></a>관련 문서

[도메인 FAQ](domains-faq.md)

[도메인이 무엇인가요?](../get-help-with-domains/what-is-a-domain.md)

[Microsoft 365에서 도메인 이름 구입하기](../get-help-with-domains/buy-a-domain-name.md)

[도메인 설정(호스트별 지침)](../get-help-with-domains/set-up-your-domain-host-specific-instructions.md)
