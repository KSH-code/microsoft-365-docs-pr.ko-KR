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
ms.localizationpriority: medium
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
description: 사용자 지정 도메인에 대한 DNS 레코드를 관리하기 위해 Microsoft를 설정한 경우 트래픽을 Microsoft 외부에 호스트된 기존 공개 웹 사이트로 라우팅하는 방법을 학습합니다.
ms.openlocfilehash: bd318710b20373abafc0d27bbd9f91d5b42c7be6
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2021
ms.locfileid: "60165283"
---
# <a name="update-dns-records-to-keep-your-website-with-your-current-hosting-provider"></a>DNS 레코드를 업데이트하여 현재 호스팅 공급자에 웹 사이트 유지

 **DNS 호스팅 공급자에서 도메인의 Microsoft** 레코드를 관리하는 경우 이 항목의 단계에 대해 걱정할 필요가 없습니다. 웹 사이트 위치가 그대로 유지되며 사용자가 계속해서 액세스할 수 있습니다. 
  
 **Microsoft에서 DNS** 레코드 를 관리하는 경우 Microsoft 외부에 호스트된 기존 공개 웹 사이트로 트래픽을 라우팅하려면 Microsoft에 도메인을 추가한 후 다음을 합니다. 
  
## <a name="update-dns-records-in-the-microsoft-365-admin-center"></a>서버의 DNS 레코드를 Microsoft 365 관리 센터
1. I관리 센터에서 **설정** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank"> 도메인</a> 페이지로 이동하십시오.

1. On the **Domains** page, select the domain and then choose **DNS Records**.

1. **+ 레코드 추가를 선택하고** 다음을 입력합니다. 
    
   - 형식 **입력:** **A(주소)**
    
   - **호스트 이름 또는 별칭** 에는 **@** 을 입력합니다.
    
   - **IP 주소** 에는 현재 호스팅되는 웹 사이트의 고정 IP 주소를 입력합니다(예: 172.16.140.1). 
    
   이 IP 주소는  *동적*  IP 주소가 아니라 웹 사이트의  *고정*  IP 주소여야 합니다. 웹 사이트가 호스트되는 사이트에서 공개 웹 사이트의 고정 IP 주소를 가져올 수 있는지 확인합니다. 
    
1. **저장** 을 선택합니다. 
    
추가로, 고객이 쉽게 사용자의 웹 사이트를 찾을 수 있도록 CNAME 레코드를 만들 수 있습니다.
  
1. **+ 레코드 추가를 선택하고** 다음을 입력합니다. 
    
   - 형식 **입력:** **CNAME(별칭)**
    
   - **호스트 이름 또는 별칭** 에는 **www** 를 입력합니다.
    
   - **대상 주소** 에 웹 사이트의 FQDN(정규화된 도메인 이름)을 contoso.com과 같이 입력합니다. 
    
2. **저장** 을 선택합니다. 
    
끝으로 다음을 실행합니다.
  
[Microsoft를 지점으로 도메인의 NS](../setup/add-domain.md) 레코드를 업데이트합니다. 
  
NS 레코드가 Microsoft를 지점으로 업데이트하면 도메인이 모두 설정됩니다. 전자 메일이 Microsoft로 라우팅되고, 웹 사이트 주소에 대한 트래픽이 현재 웹 사이트 호스트로 계속 이동됩니다.
