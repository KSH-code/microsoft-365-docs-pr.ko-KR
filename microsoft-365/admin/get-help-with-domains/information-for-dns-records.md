---
title: DNS 레코드를 만드는 데 필요한 정보 수집
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
- AdminTemplateSet
- admindeeplinkMAC
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: 77f90d4a-dc7f-4f09-8972-c1b03ea85a67
description: 도메인을 Microsoft 365 DNS 레코드를 만드는 데 필요한 값/정보를 수집합니다.
ms.openlocfilehash: c56120e446ccde93d353bd4e36fd03493cda4688
ms.sourcegitcommit: aebcdbef52e42f37492a7f780b8b9b2bc0998d5c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2021
ms.locfileid: "59774451"
---
# <a name="gather-the-information-you-need-to-create-dns-records"></a>DNS 레코드를 만드는 데 필요한 정보 수집

 원하는 정보를 찾지 못한 경우 **[도메인 FAQ를 확인](../setup/domains-faq.yml)** 하세요. 
  
### <a name="step-1-find-the-txt-record-value-and-verify"></a>1단계: TXT 레코드 값 찾기 및 확인

::: moniker range="o365-worldwide"

1. In the Microsoft 365 관리 센터, go to the **설정** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.

::: moniker-end

::: moniker range="o365-germany"

1. I관리 센터에서 **설정** > <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank"> 도메인</a> 페이지로 이동하십시오.

::: moniker-end

::: moniker range="o365-21vianet"

1. I관리 센터에서 **설정** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank"> 도메인</a> 페이지로 이동하십시오.

::: moniker-end
    
2. On the **Domains** page, select your domain, then select **Start setup**. 추가해야 하는 특정 값을 확인하려면 도메인 설정 마법사로 이동합니다.
    
3. 도메인 확인 **페이지에서** 도메인의 DNS 레코드에 **TXT 레코드** 추가를 선택하고 계속을 **선택합니다.**
    
4. 표시된 **TXT 값을 복사합니다.** **MS=msXXXXXXXXX는** 다음과 같습니다. 
    
5. 도메인을 [연결하려면 DNS](create-dns-records-at-any-dns-hosting-provider.md)레코드 추가로 이동한 다음 단계에 따라 DNS 호스트의 웹 사이트에서 레코드를 추가합니다.
    
6. DNS 호스트에서 TXT 레코드(또는 MX 레코드)를 만들기 위한 단계를 수행한 다음 도메인이 DNS 호스트에서 다시 Microsoft 365.

7. 도메인이 도메인에서 확인되면 DNS 호스트에서 TXT 레코드(또는 MX 레코드)를 Microsoft 365.
    
### <a name="step-2-find-the-mx-record-value-for-email-and-more"></a>2단계: 전자 메일에 대한 MX 레코드 값 찾기

::: moniker range="o365-worldwide"

1. In the Microsoft 365 관리 센터, go to the **설정** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.

::: moniker-end
    
::: moniker range="o365-germany"

1. I관리 센터에서 **설정** > <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank"> 도메인</a> 페이지로 이동하십시오.

::: moniker-end

::: moniker range="o365-21vianet"

1. I관리 센터에서 **설정** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank"> 도메인</a> 페이지로 이동하십시오.

::: moniker-end
    
2. **도메인** 페이지에서 도메인을 선택합니다.
    
3. CHOOSE **Manage DNS**, select More **Options** Add your  >  **own DNS** and select **Continue** to see the DNS records to add.
    
    DNS 호스트에서 변경하는 동안 이 정보를 사용할 수 있도록 유지하여 값을 복사하고 붙여 넣을 수 있습니다.
    
    이 페이지에 나열되는 DNS 레코드 그룹은 **도메인 용도** 아래에 나열된 선택 사항에 따라 달라집니다.
    
4. 도메인을 [연결하려면 DNS](create-dns-records-at-any-dns-hosting-provider.md)레코드 추가로 이동한 다음 단계에 따라 DNS 호스트의 웹 사이트에서 레코드를 추가합니다.

5. DNS 호스트에서 레코드를 만들기 위한 단계를 따릅니다.

## <a name="related-content"></a>관련 콘텐츠

[도메인 FAQ](../setup/domains-faq.yml)(문서)\
[도메인 또는 DNS 레코드를 추가한 후 문제 찾기 및 수정](find-and-fix-issues.md)(문서)\
[도메인 관리](index.yml)(링크 페이지)