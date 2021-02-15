---
title: DNS 레코드를 업데이트하여 현재 호스팅 공급자에 웹 사이트 유지
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
- Adm_NonTOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: 2c4cf347-b897-45c1-a71f-210bdc8f1061
description: 사용자 지정 도메인에 대한 DNS 레코드를 관리하기 위해 Microsoft를 설정한 경우 트래픽을 Microsoft 외부에 호스트된 기존 공개 웹 사이트로 라우팅하는 방법을 자세히 알아보는 것이 좋습니다.
ms.openlocfilehash: 5d2bf23d4052815fae210d0fdf6635288ff46b57
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/21/2020
ms.locfileid: "48645566"
---
# <a name="update-dns-records-to-keep-your-website-with-your-current-hosting-provider"></a>DNS 레코드를 업데이트하여 현재 호스팅 공급자에 웹 사이트 유지

 DNS 호스팅 공급자에서 **도메인의 Microsoft** 레코드를 관리하는 경우 이 항목의 단계에 대해 걱정할 필요가 없습니다. 웹 사이트 위치가 그대로 유지되며 사용자가 계속해서 액세스할 수 있습니다. 
  
 **Microsoft에서 DNS** 레코드를 관리하는 경우 Microsoft 외부에 호스트된 기존 공개 웹 사이트로 트래픽을 라우팅하려면 Microsoft에 도메인을 추가한 후 다음을 합니다. 
  
## <a name="update-dns-records-in-the-microsoft-365-admin-center"></a>Microsoft 365 관리 센터에서 DNS 레코드 업데이트
1. I관리 센터에서 **설정** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank"> 도메인</a> 페이지로 이동하십시오.

2. 도메인 **페이지에서** 도메인을 선택한 다음 **DNS 레코드를 선택합니다.**

3. **DNS 설정에서** 사용자 지정 **레코드를 선택합니다.**

4. **+ 새 사용자 지정 레코드** 를 선택하고 다음을 입력합니다. 
    
   - **DNS 유형** 에 대해 다음을 입력합니다. **A(주소)**
    
   - **호스트 이름 또는 별칭** 에는 **@** 을 입력합니다.
    
   - **IP 주소** 에는 현재 호스팅되는 웹 사이트의 고정 IP 주소를 입력합니다(예: 172.16.140.1). 
    
   이 IP 주소는  *동적*  IP 주소가 아니라 웹 사이트의  *고정*  IP 주소여야 합니다. 웹 사이트가 호스트되는 사이트에서 공개 웹 사이트의 고정 IP 주소를 가져올 수 있는지 확인합니다. 
    
5. **저장** 을 선택합니다. 
    
추가로, 고객이 쉽게 사용자의 웹 사이트를 찾을 수 있도록 CNAME 레코드를 만들 수 있습니다.
  
1. **+ 새 사용자 지정 레코드** 를 선택하고 다음을 입력합니다. 
    
   - **DNS 유형** 에 대해 다음을 입력합니다. **CNAME(별칭)**
    
   - **호스트 이름 또는 별칭** 에는 **www** 를 입력합니다.
    
   - **대상 주소** 에 웹 사이트의 FQDN(정규화된 도메인 이름)을 contoso.com과 같이 입력합니다. 
    
2. **저장** 을 선택합니다. 
    
끝으로 다음을 실행합니다.
  
[Microsoft를 지점으로 도메인의 NS](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/set-up-your-domain-host-specific-instructions) 레코드를 업데이트합니다. 
  
NS 레코드가 Microsoft를 지점으로 업데이트하면 도메인이 모두 설정됩니다. 전자 메일이 Microsoft로 라우팅되고, 웹 사이트 주소로 트래픽이 계속 이동하여 현재 웹 사이트 호스트로 이동됩니다.
 
