---
title: 도메인 또는 DNS 레코드를 추가한 후 문제 찾기 및 해결
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
ms.assetid: 40398b0b-bdd0-4afd-ab5e-b5ae6b7990bf
description: DNS 레코드가 올바르게 설정되어 있는지 확인하여 사용자 지정 도메인을 설정하는 동안 발생할 수 있는 문제를 추적하는 방법을 학습합니다.
ms.openlocfilehash: dfb3c93c169a3d31c14d912ddd2cc94fb1e4ace1
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50915641"
---
# <a name="find-and-fix-issues-after-adding-your-domain-or-dns-records"></a>도메인 또는 DNS 레코드를 추가한 후 문제 찾기 및 해결

 원하는 정보를 찾지 못한 경우 **[도메인 FAQ를 확인](../setup/domains-faq.yml)** 하세요. 
  
Microsoft 365를 사용하여 도메인을 설정하는 것은 어려울 수 있습니다. DNS 시스템은 번거로우며, 도메인에 대한 DNS 설정은 전자 메일처럼 중요한 비즈니스 활동에 영향을 줍니다.

> [!NOTE]
> 도메인 상태를 확인하여 도메인 문제를 확인할 수 있습니다. 설정 **도메인으로**  >  **이동하여** 상태 열에서 알림을 **볼 수** 있습니다. 문제가 표시면 추가 작업(세 개의 점)을 선택한 다음 상태 **확인 을 선택합니다.** 창이 열리면 도메인에서 발생하는 문제를 설명할 수 있습니다.
  
## <a name="whats-going-on"></a>무슨 일이죠?

- [도메인을 확인할 수 없는 경우](#cant-verify-your-domain)
    
- [Outlook이 작동하지 않는 경우](#outlook-isnt-working)
    
- [모든 사용자 전자 메일이 Microsoft 365로 전환된 후 전자 메일만 전환하고 싶나요?](#everyones-email-got-switched-to-microsoft-365-and-you-only-wanted-your-email-to-switch)

- [비영리 또는 학교 계정 상태를 확인할 수 있나요?](#cant-confirm-non-profit-or-school-account-status)

- [서비스가 도메인과 작동하지 않는 경우](#services-not-working-with-your-domain)
    
- [웹 사이트에 액세스하는 것이 작동하지 않는가요?](#accessing-your-website-isnt-working)

## <a name="cant-verify-your-domain"></a>도메인을 확인할 수 없나요?
<a name="BKMK_verify"> </a>

다음과 같이 몇 가지 일반적인 이유 때문에 도메인 확인이 예상대로 작동하지 않을 수 있습니다.
  
1. **확인 레코드 값이 올바르지 않습니다.** 여러 번 확인하면서 DNS 호스트의 TXT 확인 레코드에 정확한 값을 복사하여 붙여넣으세요. 한 가지 일반적인 문제는 레코드의 "MS =" 부분을 포함하지 않는 경우입니다. 누락하지 않도록 주의하세요! 
    
2. **레코드가 저장되지 않았습니다.** 일부 DNS 호스트에서는 영역 파일(DNS 레코드가 저장되는 위치)이 인터넷을 통해 업데이트되도록 저장하는 추가 단계를 진행해야 합니다. Microsoft 365에서 레코드를 보고 확인할 수 있도록 변경 내용을 저장해야 합니다. 
    
3. **레코드가 인터넷에서 업데이트되지 않았습니다.** 일반적으로 Microsoft에서 새 레코드를 확인하는 데 몇 분 정도면 되지만 경우에 따라 몇 시간이 걸릴 수도 있습니다. 
    
## <a name="outlook-isnt-working"></a>Outlook이 작동하지 않나요?
<a name="BKMK_OutlookBroken"> </a>

도메인에 대해 MX 레코드 및 기타 DNS 레코드를 올바르게 설정했으나 메일이 작동하지 않는 경우 [Outlook 문제 해결](/exchange/troubleshoot/outlook-connectivity/outlook-connection-issues)을 도와드리겠습니다.
  
## <a name="everyones-email-got-switched-to-microsoft-365-and-you-only-wanted-your-email-to-switch"></a>모든 사용자 전자 메일이 Microsoft 365로 전환된 후 전자 메일만 전환하고 싶나요?
<a name="BKMK_EmailSwitched"> </a>

Microsoft 365에 도메인을 추가하면 일반적으로 도메인의 MX 레코드가 Microsoft 365를 지점하기 위해(사용자 또는 Microsoft 365에 의해) 업데이트되어 해당 도메인으로 전송된 모든 전자 메일이 Microsoft 365로 전송됩니다. MX 레코드를 변경하기 전에 도메인에 전자 메일이 있는 모든 사용자에 대해 Microsoft 365에서 사서함을 만들어야 합니다.
  
도메인의 모든 사용자에 대한 전자 메일을 Microsoft 365로 이동하지 않는 경우 어떻게 하나요? 대신 몇 가지 전자 메일 주소만 사용하여 [Microsoft 365를 시험해 볼 수 있습니다.](../setup/domains-faq.yml)
  
## <a name="cant-confirm-non-profit-or-school-account-status"></a>비영리 또는 학교 계정 상태를 확인할 수 있나요?
<a name="BKMK_validateAcct"> </a>

조직의 도메인을 확인하고 서비스를 설정하지 않는 몇 가지 시나리오가 있습니다. 예를 들어 조직이 학교 구독을 한정하는 것을 Microsoft 365에 증명하려면
  
Microsoft [365](../setup/domains-faq.yml) 도메인 확인의 지침을 확인하여 소유권, 비영리 또는 교육 상태를 증명하거나, Yammer 단계를 모두 완료해야 합니다. 각 상황마다 약간 다릅니다. 
  
## <a name="services-not-working-with-your-domain"></a>도메인에서 서비스가 작동하지 않나요?
<a name="BKMK_Test"> </a>

Microsoft에서는 도메인의 DNS 설정 문제를 해결할 수 있도록 지원합니다. Microsoft 365의 도메인 문제 해결사는 수정이 필요한 모든 레코드와 레코드를 설정해야 하는 레코드를 정확하게 보여 주게 됩니다. 

> [!TIP]
> DNS를 올바르게 설정했지만 데스크톱의 Outlook에서 메일이 작동하지 않나요? [Microsoft 365에서](/exchange/mail-flow-best-practices/mail-flow-best-practices) 사용할 수 있는 다양한 메일 흐름 시나리오를 확인하여 비즈니스에 대해 올바르게 설정되어 있는지 확인합니다. 또는 전자 메일과 관련된 추가 문제 해결 도움말을 [Outlook 문제 해결](/exchange/troubleshoot/outlook-connectivity/outlook-connection-issues)에서 확인합니다. 
  
## <a name="accessing-your-website-isnt-working"></a>웹 사이트에 액세스할 수 없나요?
<a name="BKMK_Website"> </a>

DNS 문제를 해결한 경우에도 여전히 문제가 있는 경우 다음 방법 중 하나를 수행합니다.
  
- 다른 사용자가 www.mydomain.com의 내 웹 사이트에 연결할 수 없는 경우: [웹 사이트 문제 추적](../setup/add-domain.md)
    
- 웹 사이트를 설정하기 위해 A 레코드 또는 CNAME 레코드를 업데이트할 수 없습니다. [Microsoft 365에서](../setup/add-domain.md) 사용자 지정 DNS 레코드 업데이트

## <a name="related-content"></a>관련 콘텐츠

[문제 해결: 확인된 도메인 변경에 대한 데이터 감사](/azure/active-directory/reports-monitoring/troubleshoot-audit-data-verified-domain)

