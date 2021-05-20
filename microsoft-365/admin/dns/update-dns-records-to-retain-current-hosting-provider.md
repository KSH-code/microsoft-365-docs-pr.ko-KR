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
description: 사용자 지정 도메인에 대한 DNS 레코드를 관리하도록 Microsoft를 설정한 경우 Microsoft 외부에서 호스팅되는 기존 공용 웹 사이트로 트래픽을 라우팅하는 방법을 알아봅니다.
ms.openlocfilehash: 2a1559bbb902375bbc363180cdb4f98ec2b3a939
ms.sourcegitcommit: 0936f075a1205b8f8a71a7dd7761a2e2ce6167b3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/19/2021
ms.locfileid: "52572144"
---
# <a name="update-dns-records-to-keep-your-website-with-your-current-hosting-provider"></a>DNS 레코드를 업데이트하여 현재 호스팅 공급자에 웹 사이트 유지

 **DNS 호스팅 공급자에서 도메인의 Microsoft 레코드를 관리하는 경우** 이 항목의 단계에 대해 걱정할 필요가 없습니다. 웹 사이트 위치가 그대로 유지되며 사용자가 계속해서 액세스할 수 있습니다. 
  
 **Microsoft에서 DNS 레코드를 관리하여** Microsoft 외부에서 호스팅되는 기존 공용 웹 사이트로 트래픽을 라우팅하는 경우 도메인을 Microsoft에 추가한 후 다음을 수행합니다. 
  
## <a name="update-dns-records-in-the-microsoft-365-admin-center"></a>Microsoft 365 관리 센터에서 DNS 레코드 업데이트
1. I관리 센터에서 **설정** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank"> 도메인</a> 페이지로 이동하십시오.

1. 도메인 페이지에서 **도메인을** 선택한 다음 **DNS 레코드를 선택합니다.**

1. **+ 레코드 추가** 를 선택하고 다음을 입력합니다. 
    
   - **유형** 입력: **A(주소)**
    
   - **호스트 이름 또는 별칭** 에는 **@** 을 입력합니다.
    
   - **IP 주소** 에는 현재 호스팅되는 웹 사이트의 고정 IP 주소를 입력합니다(예: 172.16.140.1). 
    
   이 IP 주소는  *동적*  IP 주소가 아니라 웹 사이트의  *고정*  IP 주소여야 합니다. 웹 사이트가 호스트되는 사이트에서 공개 웹 사이트의 고정 IP 주소를 가져올 수 있는지 확인합니다. 
    
1. **저장** 을 선택합니다. 
    
추가로, 고객이 쉽게 사용자의 웹 사이트를 찾을 수 있도록 CNAME 레코드를 만들 수 있습니다.
  
1. **+ 레코드 추가** 를 선택하고 다음을 입력합니다. 
    
   - **유형** 입력: **CNAME(별칭)**
    
   - **호스트 이름 또는 별칭** 에는 **www** 를 입력합니다.
    
   - **대상 주소** 에 웹 사이트의 FQDN(정규화된 도메인 이름)을 contoso.com과 같이 입력합니다. 
    
2. **저장** 을 선택합니다. 
    
끝으로 다음을 실행합니다.
  
[도메인의 NS 레코드를 업데이트하여](../get-help-with-domains/set-up-your-domain-host-specific-instructions.md) Microsoft를 가리킵니다. 
  
NS 레코드가 Microsoft를 가리키도록 업데이트된 경우 도메인이 모두 설정됩니다. 이메일은 Microsoft로 라우팅되며 웹 사이트 주소로의 트래픽은 현재 웹 사이트 호스트로 계속 이동합니다.
