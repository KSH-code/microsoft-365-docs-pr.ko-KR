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
ms.assetid: 77f90d4a-dc7f-4f09-8972-c1b03ea85a67
description: 'Microsoft 365에 대 한 DNS 레코드를 만드는 데 필요한 값/정보를 확인 하는 방법을 설명 합니다. '
ms.openlocfilehash: eca9dbe4e40193f76538b639624b827177ff7772
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/21/2020
ms.locfileid: "48645314"
---
# <a name="gather-the-information-you-need-to-create-dns-records"></a>DNS 레코드를 만드는 데 필요한 정보 수집

 원하는 정보를 찾지 못한 경우 **[도메인 FAQ를 확인](../setup/domains-faq.md)** 하세요. 
  
### <a name="step-1-find-the-txt-record-value-and-verify"></a>1 단계: TXT 레코드 값을 찾아서 확인

::: moniker range="o365-worldwide"

1. Microsoft 365 관리 센터에서 **Setup** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">도메인</a> 설정 페이지로 이동 합니다.

::: moniker-end

::: moniker range="o365-germany"

1. 관리 센터에서 **Setup** > <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">도메인</a> 설정 페이지로 이동 합니다.

::: moniker-end

::: moniker range="o365-21vianet"

1. 관리 센터에서 **Setup** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">도메인</a> 설정 페이지로 이동 합니다.

::: moniker-end
    
2. **도메인** 페이지에서 도메인을 선택한 다음 **설치 시작**을 선택 합니다. 추가해야 하는 특정 값을 확인하려면 도메인 설정 마법사로 이동합니다.
    
3. **도메인 확인** 페이지에서 **대신 TXT 레코드 추가**를 선택 하 고 **다음**을 선택 합니다.
    
4. 표시 된 **TXT 값** 을 복사 합니다. **MS = msXXXXXXXX**를 선택 합니다. 
    
5. [Dns 호스팅 공급자에서 dns 레코드 만들기](create-dns-records-at-any-dns-hosting-provider.md)로 이동 하 여 등록 기관 목록에서 dns 호스트를 선택 하 여 단계별 지침을 확인 합니다.
    
6. DNS 호스트에서 TXT 레코드 (또는 MX 레코드)를 만들기 위한 단계를 따른 다음 Microsoft 365에서 도메인을 다시 확인 합니다.

7. Microsoft 365에서 도메인을 확인 한 후 DNS 호스트에서 TXT 레코드 (또는 MX 레코드)를 제거 합니다.
    
### <a name="step-2-find-the-mx-record-value-for-email-and-more"></a>2 단계: 전자 메일에 대 한 MX 레코드 값 찾기

::: moniker range="o365-worldwide"

1. Microsoft 365 관리 센터에서 **Setup** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">도메인</a> 설정 페이지로 이동 합니다.

::: moniker-end
    
::: moniker range="o365-germany"

1. 관리 센터에서 **Setup** > <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">도메인</a> 설정 페이지로 이동 합니다.

::: moniker-end

::: moniker range="o365-21vianet"

1. 관리 센터에서 **Setup** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">도메인</a> 설정 페이지로 이동 합니다.

::: moniker-end
    
2. **도메인** 페이지에서 도메인을 선택합니다. 
    
3. **필수 DNS 설정**에서 추가할 DNS 레코드를 볼 수 있습니다.
    
    DNS 호스트에서 변경하는 동안 이 정보를 사용할 수 있도록 유지하여 값을 복사하고 붙여 넣을 수 있습니다.
    
    이 페이지에 나열되는 DNS 레코드 그룹은 **도메인 용도** 아래에 나열된 선택 사항에 따라 달라집니다.
    
4. Dns [호스팅 공급자에서 dns 레코드 만들기](create-dns-records-at-any-dns-hosting-provider.md)로 이동 하 여 등록 기관 목록에서 dns 호스트를 선택 하면 해당 dns 호스트 웹 사이트에서 레코드를 추가 하는 단계별 지침을 볼 수 있습니다.
    
5. DNS 호스트에서 레코드를 만들기 위한 단계를 따릅니다.
