---
title: 사용자의 다른 전자 메일 별칭 추가
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- MSStore_Link
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 0b0bd900-68b1-4bf5-808b-5d240a7739f4
description: '비즈니스 계정에 대한 Microsoft 365 연결된 이메일 별칭이라는 두 개 이상의 이메일 주소를 가질 수 있는 방법에 대해 알아봅니다. '
ms.openlocfilehash: ec5bc69a42c5183413f11649b7d7ec6baaf40b01
ms.sourcegitcommit: 0936f075a1205b8f8a71a7dd7761a2e2ce6167b3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/19/2021
ms.locfileid: "52572108"
---
# <a name="add-another-email-alias-for-a-user"></a>사용자의 다른 전자 메일 별칭 추가
  
이 문서는 비즈니스 구독이 있는 관리자를 Microsoft 365 위한 것입니다. 가정용 사용자용이 아닙니다.
  
Microsoft 365 기본 이메일 주소는 일반적으로 사용자가 계정을 만들 때 할당된 이메일 주소입니다. 사용자가 다른 사람에게 전자 메일을 보내면 전자 메일 앱의  *보낸 사람*  필드에 일반적으로 사용자의 기본 전자 메일 주소가 표시됩니다. 또한 비즈니스 계정에 대한 Microsoft 365 연결된 두 개 이상의 이메일 주소를 가질 수도 있습니다. 이러한 추가 주소를 별칭이라고 합니다. 
  
예를 들어, 제나는 이메일 주소가 jenna@contosoco.com 있다고 가정해 보지만, 어떤 사람들은 그 이름으로 그녀를 참조하기 때문에 jen@contosoco.com 이메일을 받고 싶다고 가정해 봅시다. 두 이메일 주소가 제나의 받은 편지함으로 이동하도록 그녀를 위해 별칭을 만들 수 있습니다.
  
사용자는 최대 400의 별칭을 만들 수 있습니다. 추가 요금이나 라이선스는 필요하지 않습니다.
  
> [!Tip]
> 여러 사람이 info@NodPublishers.com 또는 sales@NodPublishers.com 같은 단일 이메일 주소로 전송된 전자 메일을 관리하려면 공유 사서함을 만듭니다. 자세한 내용은 [공유 사서함 만들기를](create-a-shared-mailbox.md)참조하십시오.
  
## <a name="add-email-aliases-to-a-user"></a>사용자에게 전자 메일 별칭 추가

이 작업을 수행할 [관리자 권한이](../add-users/about-admin-roles.md) 있어야 합니다. 

1. 관리 센터에서 **사용자** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">활성 사용자</a> 페이지로 이동합니다..

2. 활성 **사용자** 페이지에서 사용자 이름 **및 전자 메일 관리**> 사용자를 선택합니다. 사람이 자신에게 할당된 라이선스가 없는 경우 이 옵션이 표시되지 않습니다. 
    
3. **선택 + 별칭을 추가하고** 사용자에 대한 새 별칭을 입력합니다.   
    
    > [!Important] 
    > **'앱미터 이름 'emailNames'와 일치하는 매개 변수를 찾을 수 없는** 경우 테넌트 설정또는 최근에 추가한 경우 사용자 지정 도메인을 설정하는 데 조금 더 오래 걸리는 것을 의미합니다. 설정 프로세스를 완료하는 데 최대 4시간이 걸릴 수 있습니다. 설정 프로세스가 완료될 때까지 기다린 후 다시 시도하세요. 문제가 계속되는 경우 고객 지원에 문의하면 전체 동기화를 수행해 드립니다.
    
  
    > [!IMPORTANT]
    > GoDaddy 또는 다른 파트너로부터 구독을 구입한 경우 새 별칭을 기본으로 설정하려면 GoDaddy/파트너 관리 콘솔로 이동해야 합니다. 
  
    > [!TIP]
    > 전자 메일 별칭은 드롭다운 목록의 도메인으로 끝나야 합니다. 목록에 다른 도메인 이름을 추가하려면 [도메인을 Microsoft 365.](../setup/add-domain.md) 
  
     
5. 작업이 완료되면 **변경 내용 저장을** 선택합니다.
    
6. 새 별칭이 Microsoft 365 전체로 채워지도록 24시간을 기다립니다.
    
    이제 사용자에게 기본 주소와 별칭이 있습니다. 예를 들어, 엘리자 호프만의 주요 주소인 Eliza@NodPublishers.com 및 그녀의 별칭인 Sales@NodPublishers.com 엘리자의 받은 편지함으로 전송된 모든 메일이 엘리자의 받은 편지함으로 이동합니다.
    
  
7. **사용자가 회신하면 *From* 주소는 Outlook 클라이언트에 따라 달라집니다. 웹의 Outlook 이메일이 수신된 별칭을 사용합니다(탁구 원칙이라고 함). Outlook 데스크톱은 그녀의 기본 이메일 별칭을 사용합니다.** 예를 들어 Sales@NodPublishers.com 메시지가 전송되고 Eliza의 받은 편지함으로 전송됩니다. Eliza가 Outlook 데스크톱을 사용하여 메시지에 회신하면 기본 이메일 주소가 Sales@NodPublishers.com 아닌 Eliza@NodPublishers.com 나타납니다.
    
## <a name="did-you-get-a-parameter-cannot-be-found-that-matches-parameter-name-emailaddresses"></a>"매개 변수 이름 Email주소와 일치하는 매개 변수를 찾을 수 없습니다"를 얻었습니까?

오류 메시지가 있는 경우 "**매개 변수 이름 EmailNames와 일치하는 매개 변수를 찾을 수 없습니다**" 그것은 테넌트 설정을 완료하는 데 조금 더 오래 걸리는 것을 의미, 또는 사용자 지정 도메인을 최근에 추가 하는 경우. 설정 프로세스를 완료하는 데 최대 4시간이 걸릴 수 있습니다. 설정 프로세스가 완료될 때까지 기다린 후 다시 시도하세요. 문제가 계속되는 경우 고객 지원에 문의하면 전체 동기화를 수행해 드립니다.
  
## <a name="did-you-purchase-your-subscription-from-godaddy-or-another-partner"></a>GoDaddy 또는 다른 파트너로부터 구독을 구입했나요?


GoDaddy 또는 다른 파트너로부터 구독을 구입한 경우 새 별칭을 기본으로 설정하려면 GoDaddy/파트너 관리 콘솔로 이동해야 합니다.

## <a name="sending-email-from-the-proxy-address-easily"></a>프록시 주소에서 전자 메일 보내기

2021년 4월에 새로운 기능이 출시되어 사용자가 웹에서 Outlook 사용할 때 별칭에서 쉽게 보낼 수 있습니다. 테넌트 관리자가 cmdlet을 사용하는 테넌트로 기능이 `Set-OrganizationConfig -SendFromAliasEnabled $true` 출시되면 테넌트 내의 사용자는 각 항목이 Outlook 설정의 별칭에 해당하는 확인란 목록에 액세스할 수 있습니다. 별칭을 선택하면 컴포지트 양식의 From 드롭다운에 표시됩니다.
  
## <a name="related-content"></a>관련 콘텐츠

[다른 주소에서 이메일](https://support.microsoft.com/office/ccba89cb-141c-4a36-8c56-6d16a8556d2e) 보내기(기사)

[사용자 이름 및 이메일 주소](../add-users/change-a-user-name-and-email-address.md) 변경(문서)

[Microsoft 365에서 전자 메일 전달 구성](configure-email-forwarding.md)(문서)
