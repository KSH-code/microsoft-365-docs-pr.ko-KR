---
title: 도메인 FAQ
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
- Adm_O365
- Adm_TOC
ms.custom:
- AdminSurgePortfolio
- okr_smb
search.appverid:
- BCS160
- MET150
- MOE150
- BEA160
- GEA150
ms.assetid: 1272bad0-4bd4-4796-8005-67d6fb3afc5a
description: 도메인에 대 한 자세한 내용은 질문과 대답을 확인 하세요.
ms.openlocfilehash: fe602c45059be1b273b7ebe3a11cd91adf89a479
ms.sourcegitcommit: 260bbb93bbda62db9e88c021ccccfa75ac39a32e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/21/2020
ms.locfileid: "46845847"
---
# <a name="domains-faq"></a>도메인 FAQ

::: moniker range="o365-21vianet"

> [!NOTE]
> 관리 센터가 변경되고 있습니다. 사용자의 환경이 여기에 설명된 세부 정보와 맞지 않는 경우에는 [새 Microsoft 365 관리 센터 정보](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet)를 참조하세요.

::: moniker-end

이 문서에는 Microsoft 365의 도메인에 대 한 질문과 대답이 포함 되어 있습니다.

질문에 대한 대답을 찾을 수 없는 경우 저희에게 메모를 남겨 알려주시면 목록에 추가해 드리겠습니다.

이 문서의 내용

- [MX 우선 순위란?](#what-is-mx-priority)
- [내 도메인에 대 한 SPF 레코드를 확인 하려면 어떻게 하나요?](#how-can-i-validate-spf-records-for-my-domain)
- [도메인 이름 이란?](#what-is-a-domain-name)
- [DNS 공급자가 특정 레코드 종류를 지원 하지 않으면 어떻게 되나요?](#what-happens-if-my-dns-provider-doesnt-support-certain-record-types)
- [Microsoft 365에서 기본 도메인을 설정 하거나 변경 하려면 어떻게 하나요?](#how-do-i-set-or-change-the-default-domain-in-microsoft-365)
- [사용자 지정 하위 도메인 또는 여러 도메인을 Microsoft 365에 추가할 수 있나요?](#can-i-add-custom-subdomains-or-multiple-domains-to-microsoft-365)
- [도메인을 Microsoft 365에서 다른 호스트로 어떻게 전송 하나요?](#how-do-i-transfer-a-domain-from-microsoft-365-to-another-host)
- ["Onmicrosoft.com" 도메인을 보유 하는 이유는 무엇 인가요?](#why-do-i-have-an-onmicrosoftcom-domain)
- ["Onmicrosoft.de" 도메인을 보유 하는 이유는 무엇 인가요?](#why-do-i-have-an-onmicrosoftde-domain)
- [비영리 또는 학력 상태를 확인 하려면 어떻게 해야 하나요?](#how-do-i-verify-my-nonprofit-or-education-status)
    
## <a name="what-is-mx-priority"></a>MX 우선 순위란?

메일은 가장 낮은 기본 설정 번호 (가장 높은 우선 순위)를 사용 하 여 메일 교환 서버로 배달 되므로 메일 라우팅에 사용 하는 MX 레코드는 가장 낮은 기본 설정 번호 (일반적으로 0 또는  *높은*  우선 순위)를 가져야 합니다. 
  
- MX 레코드를 만들 때 대부분의 DNS 호스팅 공급자가 기본 설정 번호를 설정 해야 합니다.
    
- 일부 레이블은 box  *기본 설정*  및 일부 레이블의  *우선 순위*  입니다. 
    
- 일부 필요한 경우에는  *낮음*  ,  *중간*  또는  *높음을*  선택 하 라는 것이 좋습니다. 
    
- MX 레코드가 하나인 경우에는 우선 순위 또는 기본 설정에 적절 한 값을 사용할 수 있습니다.
    
- 두 개 이상 있는 경우 메일 라우팅에 대 한 MX 레코드의 우선 순위가 도메인을 소유 하 고 있는지 확인 하는 데 사용 되는 것 보다 높은 지 확인 합니다.
    
## <a name="how-can-i-validate-spf-records-for-my-domain"></a>내 도메인에 대 한 SPF 레코드를 확인 하려면 어떻게 하나요?

**SPF에 대해서는 TXT 레코드를**하나만 만들거나 만들어야 합니다. SPF 레코드가 이미 있는 경우 새 Microsoft 365 값을 만드는 대신 새 사용자에 게 해당 레코드를 추가 해야 합니다. Microsoft 전자 메일에 대 한 SPF 레코드를 추가 하거나 업데이트 한 후 다음 도구 중 하나를 사용 하 여 구문이 올바른지 확인 해야 합니다. 
  
- [SPF 레코드 테스트 도구](http://www.kitterman.com/spf/validate.html)
    
- [SPF Surveyor](https://dmarcian.com/spf-survey/)
    
- [웹 인터페이스](http://digwebinterface.com/)

## <a name="what-is-a-domain-name"></a>도메인 이름 이란?

도메인은 전자 메일 주소에서 **@** 기호 뒤에, 그리고 웹 주소에서 **www.** 뒤에 나타나는 고유한 이름입니다. 일반적으로  *yourbusiness.com*  또는 stateuniversity.edu와 같은 표준 인터넷 접미사와 조직의 이름 형식을 사용 합니다  *.* 
  
"**Rob \@ contoso.com**"과 같은 사용자 지정 도메인을 Microsoft 365와 함께 사용 하면 신용 및 브랜드를 위한 신뢰도를 구축 하는 데 도움이 될 수 있습니다. 
  
[Microsoft 365에서 도메인을 구입 하 여 자동으로 설정](../get-help-with-domains/buy-a-domain-name.md)하거나 이미 도메인 등록 기관에서 소유한 사용자를 구입 하거나 가져올 수 있습니다.
    
## <a name="what-happens-if-my-dns-provider-doesnt-support-certain-record-types"></a>DNS 공급자가 특정 레코드 종류를 지원 하지 않으면 어떻게 되나요?

자체 DNS 레코드를 관리 하는 경우 DNS 호스트에서 Microsoft 365에 필요한 모든 DNS 레코드를 지원 하지 않으면 일부 Microsoft 365 기능이 작동 하지 않습니다. 필요한 모든 DNS 레코드를 지 원하는 등록자에 게 도메인을 전송 하는 것이 좋습니다.
  
필요한 모든 DNS 레코드를 지 원하는 공급자:
  
- Dynadot
    
- eNomCentral
    
- Europe Registry
    
- GoDaddy
    
- 가리키기
    
- MyHosting.com
    
- Name.com
    
- 거의 무료 음성
    
- Nettica
    
- NIC(Network Information Center)
    
- Network Solutions
    
- Register.com
  
## <a name="how-do-i-set-or-change-the-default-domain-in-microsoft-365"></a>Microsoft 365에서 기본 도메인을 설정 하거나 변경 하려면 어떻게 하나요?

기본 도메인을 선택 하려면 먼저 Microsoft 365에 추가한 사용자 지정 도메인이 하나 이상 있어야 합니다.

::: moniker range="o365-worldwide"

1. I관리 센터에서 ** 설정 ** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank"> 도메인 </a> 페이지로 이동하십시오.

::: moniker-end

::: moniker range="o365-germany"

1. I관리 센터에서 ** 설정 ** > <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank"> 도메인 </a> 페이지로 이동하십시오.

::: moniker-end

::: moniker range="o365-21vianet"

1. I관리 센터에서 ** 설정 ** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank"> 도메인 </a> 페이지로 이동하십시오.

::: moniker-end
    
2. **도메인** 페이지에서 새 전자 메일 주소에 대 한 기본값으로 설정할 도메인을 선택 합니다. 
    
3. **기본값으로 설정**을 선택합니다.
    
::: moniker range="o365-worldwide"

*Onmicrosoft.com* 도메인의 이름은 변경할 수 없습니다. 

::: moniker-end

::: moniker range="o365-germany"

*Onmicrosoft.de* 도메인의 이름은 변경할 수 없습니다. 

::: moniker-end

::: moniker range="o365-21vianet"

*Partner.onmschina.cn* 도메인의 이름은 변경할 수 없습니다. 

::: moniker-end

## <a name="can-i-add-custom-subdomains-or-multiple-domains-to-microsoft-365"></a>사용자 지정 하위 도메인 또는 여러 도메인을 Microsoft 365에 추가할 수 있나요?

::: moniker range="o365-worldwide"

예. 하위 도메인을 추가 하려면 등록자의 웹 사이트에서 자체 DNS 설정을 관리 해야 합니다. Microsoft에서 NS 레코드를 사용 하 여 DNS 설정을 관리할 수 있도록 하거나 Microsoft 로부터 도메인을 구매한 경우에는 하위 도메인을 추가할 수 없습니다.

::: moniker-end

::: moniker range="o365-germany"

예로! 하위 도메인을 추가 하려면 등록자의 웹 사이트에서 자체 DNS 설정을 관리 해야 합니다. Microsoft에서 NS 레코드를 사용 하 여 DNS 설정을 관리할 수 있도록 하거나 Microsoft 로부터 도메인을 구매한 경우에는 하위 도메인을 추가할 수 없습니다.

::: moniker-end

::: moniker range="o365-21vianet"

예로! 하위 도메인을 추가 하려면 등록자의 웹 사이트에서 자체 DNS 설정을 관리 해야 합니다. 21Vianet에서 NS 레코드를 사용 하 여 DNS 설정을 관리할 수 있도록 허용 하는 경우 하위 도메인을 추가 하면 안 됩니다.

::: moniker-end

일반적으로 Microsoft 365 구독에는 최대 900 개의 도메인을 추가할 수 있습니다.
  
예를 들어 contoso.com 및 contosomarketing.com 도메인을 추가한 다음 하위 도메인 www.contoso.com, www.partners.contoso.com, www.partners.marketing.contoso.com 등을 추가할 수 있습니다.
  
하위 도메인을 추가 하면 유효성이 확인 되는 상위 도메인을 기반으로 자동으로 확인 됩니다.
  
Microsoft 365에 여러 도메인을 추가 하면 추가한 도메인에서 모든 서비스 (예를 들어 전자 메일)를 호스팅할 수 있습니다.  *도메인의 MX 레코드를 업데이트 하 여 Microsoft 365에 대 한 전자 메일을 변경 하면 해당 도메인으로 전송 된 모든 전자 메일이 Microsoft 365로 시작 됩니다.* 
 
::: moniker range="o365-worldwide"

> [!NOTE]
> Microsoft 365 구독에 contoso.com 도메인을 추가한 경우 다른 Microsoft 365 조직에 하위 도메인 xyz.contoso.com를 추가할 수도 있습니다. 하위 도메인을 추가할 때 DNS 호스팅 공급자에 TXT 레코드를 추가 하 라는 메시지가 표시 됩니다.

## <a name="how-do-i-transfer-a-domain-from-microsoft-365-to-another-host"></a>도메인을 Microsoft 365에서 다른 호스트로 어떻게 전송 하나요?

도메인을 전송 하는 절차는 도메인을 [Microsoft에서 다른 호스트로 전송을](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/transfer-a-domain-from-microsoft-to-another-host)참조 하십시오.

## <a name="pilot-microsoft-365-from-my-custom-domain"></a>사용자 지정 도메인에서 Microsoft 365 파일럿

사용자 지정 도메인에서 Microsoft 365 사서함으로 Microsoft 365 전자 메일 기능을 파일럿으로 수행 하는 절차는 [사용자 지정 도메인의 파일럿 Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/misc/pilot-microsoft-365-from-my-custom-domain)를 참조 하십시오.

## <a name="why-do-i-have-an-onmicrosoftcom-domain"></a>"Onmicrosoft.com" 도메인을 보유 하는 이유는 무엇 인가요?

Microsoft 365는 서비스에 등록할 때 *contoso.onmicrosoft.com*와 같은 도메인을 만듭니다. 등록할 때 만드는 사용자 ID에는 *alan@contoso.onmicrosoft.com*와 같은 도메인이 포함 됩니다. 
  
 **전자 메일을 *alan \@ contoso.com*:** 으로 지정 하려면 [도메인을 구입](../get-help-with-domains/buy-a-domain-name.md) 하거나 [사용자 및 도메인을 이미 소유 하 고 있는 경우 Microsoft 365에 추가](add-domain.md) 단계를 수행 합니다. 
  
- **등록 후에는 onmicrosoft 도메인의 이름을 바꿀 수 없습니다.** 예를 들어 선택한 초기 도메인이 fourthcoffee.onmicrosoft.com 인 경우 fabrikam.onmicrosoft.com로 변경할 수 없습니다. 다른 onmicrosoft.com 도메인을 사용 하려면 Microsoft 365을 사용 하 여 새 구독을 시작 해야 합니다. 
    
- **팀 사이트 URL의 이름은 바꿀 수 없습니다.** 팀 사이트 URL은 onmicrosoft.com 도메인 이름을 기반으로 합니다. 아쉽게도 SharePoint Online 아키텍처의 작동 방식 때문에 팀 사이트의 이름을 바꿀 수 없습니다. 
    
- **Onmicrosoft 도메인은 제거할 수 없습니다.** Microsoft 365는 구독을 위해 배후에서 사용 되 고 있으므로 주변을 유지 해야 합니다. 하지만 사용자 지정 도메인을 추가한 후에는 직접 도메인을 사용할 필요가 없습니다. 
    
도메인을 추가한 후에도 초기 onmicrosoft.com 도메인을 계속 사용할 수 있습니다. 여전히 전자 메일 및 기타 서비스에 대해 작동 하기 때문에 선택 해야 합니다.
  
::: moniker-end

::: moniker range="o365-germany"
## <a name="why-do-i-have-an-onmicrosoftde-domain"></a>"Onmicrosoft.de" 도메인을 보유 하는 이유는 무엇 인가요?

Microsoft 365는 서비스에 등록할 때 *contoso.onmicrosoft.de*와 같은 도메인을 만듭니다. 등록할 때 만드는 사용자 ID에는 *alan@contoso.onmicrosoft.de*와 같은 도메인이 포함 됩니다. 
  
 **전자 메일을 *alan@contoso.de*같이 표시 하려면** [도메인을 구입](../get-help-with-domains/buy-a-domain-name.md) 하거나 [사용자와 도메인을 이미 소유한 경우 Microsoft 365에 추가](add-domain.md) 의 단계를 따르세요. 
  
- **등록 후에는 onmicrosoft 도메인의 이름을 바꿀 수 없습니다.** 예를 들어 선택한 초기 도메인이 fourthcoffee.onmicrosoft.de 인 경우 fabrikam.onmicrosoft.de로 변경할 수 없습니다. 다른 onmicrosoft.de 도메인을 사용 하려면 Microsoft 365을 사용 하 여 새 구독을 시작 해야 합니다. 
    
- **팀 사이트 URL의 이름은 바꿀 수 없습니다.** 팀 사이트 URL은 onmicrosoft.de 도메인 이름을 기반으로 합니다. 아쉽게도 SharePoint Online 아키텍처의 작동 방식 때문에 팀 사이트의 이름을 바꿀 수 없습니다. 
    
- **Onmicrosoft 도메인은 제거할 수 없습니다.** Microsoft 365는 구독을 위해 배후에서 사용 되 고 있으므로 주변을 유지 해야 합니다. 하지만 사용자 지정 도메인을 추가한 후에는 직접 도메인을 사용할 필요가 없습니다. 
    
도메인을 추가한 후에도 초기 onmicrosoft.de 도메인을 계속 사용할 수 있습니다. 여전히 전자 메일 및 기타 서비스에 대해 작동 하기 때문에 선택 해야 합니다.
  
::: moniker-end

## <a name="how-do-i-verify-my-nonprofit-or-education-status"></a>비영리 또는 학력 상태를 확인 하려면 어떻게 해야 하나요?

1. [관리 센터](https://docs.microsoft.com/microsoft-365/admin/admin-home) 에서 **설치** 를 선택 하 여 마법사를 시작 합니다. (먼저 Microsoft 365에 로그인 해야 합니다.) 
    
2. 학교 관리자가 되기 위해 Microsoft 365에서  **관리자로가** 는 것으로 관리 옵션을 선택 합니다. 
    
3. 도메인에 대 한 DNS 호스트 웹 사이트에 TXT DNS 레코드를 추가 하 라는 메시지가 표시 됩니다. 다음과 같은 이유 때문입니다. DNS 호스트에 로그인 하 고 도메인에 대 한 레코드를 추가 하는 경우 Microsoft 365에서 도메인 이름을 소유 하 고 있음을 증명 합니다.
    
4. 레코드를 추가한 후 Microsoft 365 포털로 돌아가서 추가 된 내용을 확인 한 다음 Microsoft 365에서 확인할 수 있습니다.
    
Microsoft 365을 받으려면 비영리이 있나요? [조직에서](https://www.microsoft.com/en-us/nonprofits/eligibility) 서비스를 확인 한 다음 등록 합니다. 
  
학교에서 관리자 되는 것에 대해 자세히 알고 싶으십니까? 를 [참고](https://docs.microsoft.com/microsoft-365/education/deploy/becoming-an-admin-in-office-365-education
)하세요.