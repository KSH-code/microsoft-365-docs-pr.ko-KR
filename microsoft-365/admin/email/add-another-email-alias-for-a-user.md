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
- AdminTemplateSet
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 0b0bd900-68b1-4bf5-808b-5d240a7739f4
description: '비즈니스용 계정과 연결된 전자 메일 별칭이라는 전자 메일 주소를 두 개 이상 사용할 Microsoft 365 방법을 알아보습니다. '
ms.openlocfilehash: ab1a7b846bb35cce4656a3a5edf941961f5398c2
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2021
ms.locfileid: "59184779"
---
# <a name="add-another-email-alias-for-a-user"></a>사용자의 다른 전자 메일 별칭 추가
  
이 문서는 비즈니스 Microsoft 365 관리자를 위한 것입니다. 가정용 사용자용이 아닙니다.
  
기본 전자 메일 Microsoft 365 계정이 만들어지기 전 사용자가 할당한 전자 메일 주소입니다. 사용자가 다른 사람에게 전자 메일을 보내면 전자 메일 앱의  *보낸 사람*  필드에 일반적으로 사용자의 기본 전자 메일 주소가 표시됩니다. 또한 비즈니스용 계정용 전자 메일 주소와 연결된 전자 메일 Microsoft 365 수 있습니다. 이러한 추가 주소를 별칭이라고 합니다. 
  
예를 들어 Jenna의 전자 메일 주소는 jenna@contosoco.com 있지만 일부 사람들이 해당 이름으로 jen@contosoco.com 전자 메일을 받기를 원합니다. 두 전자 메일 주소가 모두 Jenna의 받은 편지함으로 이동될 수 있도록 별칭을 만들 수 있습니다.
  
사용자는 최대 400의 별칭을 만들 수 있습니다. 추가 요금이나 라이선스는 필요하지 않습니다.
  
> [!Tip]
> 여러 사용자가 단일 전자 메일 주소(info@NodPublishers.com 또는 전자 메일 주소로 전송된 전자 메일을 sales@NodPublishers.com 사서함을 만들 수 있습니다. 자세한 내용은 공유 사서함 [만들기를 참조합니다.](create-a-shared-mailbox.md)
  
## <a name="add-email-aliases-to-a-user"></a>사용자에게 전자 메일 별칭 추가

이렇게하려면 관리자 [권한이](../add-users/about-admin-roles.md) 있어야 합니다. 

1. 관리 센터에서 **사용자** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">활성 사용자</a> 페이지로 이동합니다..

2. 활성 **사용자 페이지에서** 사용자 이름 및 전자 메일 > **사용자를 선택합니다.** 사용자에게 할당된 라이선스가 없는 경우 이 옵션이 표시됩니다. 
    
3. **+ 별칭 추가를 선택하고** 사용자의 새 별칭을 입력합니다.   
    
    > [!Important] 
    > "매개 변수 이름 **'EmailAddresses와** 일치하는 매개 변수를 찾을 수 없습니다.'라는 오류 메시지가 표시될 경우 테넌트 또는 최근에 사용자 지정 도메인을 추가한 경우 사용자 지정 도메인 설정을 완료하는 데 시간이 더 오래 드는 것입니다. 설정 프로세스를 완료하는 데 최대 4시간이 걸릴 수 있습니다. 설정 프로세스가 완료될 때까지 기다린 후 다시 시도하세요. 문제가 계속되는 경우 고객 지원에 문의하면 전체 동기화를 수행해 드립니다.
    
  
    > [!IMPORTANT]
    > GoDaddy 또는 다른 파트너로부터 구독을 구입한 경우 새 별칭을 기본으로 설정하려면 GoDaddy/파트너 관리 콘솔로 이동해야 합니다. 
  
    > [!TIP]
    > 전자 메일 별칭은 드롭다운 목록의 도메인으로 끝나야 합니다. 목록에 다른 도메인 이름을 추가하려면 [Add a domain to Microsoft 365.](../setup/add-domain.md) 
  
     
5. 완료되면 변경 내용 **저장 을 선택 합니다.**
    
6. 새 별칭이 전체적으로 채워지기까지 24시간 Microsoft 365.
    
    이제 사용자에게 기본 주소와 별칭이 있습니다. 예를 들어 Eliza Hoffman의 기본 주소인 Eliza@NodPublishers.com 및 별칭인 Sales@NodPublishers.com 메일은 모두 지민의 받은 편지함으로 이동됩니다.
    
  
7. **사용자가 답장할 때 *From* 주소는 사용자의 클라이언트에 Outlook 않습니다. 웹용 Outlook 받은 별칭을 사용하게 됩니다(이를 ping-pong 원칙으로 지칭). Outlook 데스크톱에서 기본 전자 메일 별칭을 사용할 것입니다.** 예를 들어 메시지가 전자 메일로 전송된 Sales@NodPublishers.com 지민의 받은 편지함으로 도착하는 경우를 예로 들어 보겠습니다. Eliza가 Outlook 데스크톱을 사용하여 메시지에 응답하면 기본 전자 메일 주소가 Eliza@NodPublishers.com 아닌 Sales@NodPublishers.com.
    
## <a name="did-you-get-a-parameter-cannot-be-found-that-matches-parameter-name-emailaddresses"></a>"매개 변수 이름 EmailAddresses와 일치하는 매개 변수를 찾을 수 없습니다."가 있나요?

"매개 변수 이름 **EmailAddresses와** 일치하는 매개 변수를 찾을 수 없습니다." 오류 메시지가 표시될 경우 테넌트 또는 최근에 사용자 지정 도메인을 추가한 경우 사용자 지정 도메인 설정이 완료됩니다. 설정 프로세스를 완료하는 데 최대 4시간이 걸릴 수 있습니다. 설정 프로세스가 완료될 때까지 기다린 후 다시 시도하세요. 문제가 계속되는 경우 고객 지원에 문의하면 전체 동기화를 수행해 드립니다.
  
## <a name="did-you-purchase-your-subscription-from-godaddy-or-another-partner"></a>GoDaddy 또는 다른 파트너로부터 구독을 구입했나요?


GoDaddy 또는 다른 파트너로부터 구독을 구입한 경우 새 별칭을 기본으로 설정하려면 GoDaddy/파트너 관리 콘솔로 이동해야 합니다.

## <a name="sending-email-from-the-proxy-address-easily"></a>프록시 주소에서 전자 메일 쉽게 보내기

새로운 기능은 2021년 7월에 출시되어 사용자가 별칭을 사용하여 쉽게 별칭에서 보낼 수 웹용 Outlook. 이 기능이 테넌트 관리자가 cmdlet을 사용하는 테넌시로 롤아웃하면 테넌시 내의 사용자는 각 항목이 해당 Outlook 설정의 별칭에 해당하는 `Set-OrganizationConfig -SendFromAliasEnabled $true` 확인란 목록에 액세스할 수 있습니다. 별칭을 선택하면 작성 양식의 From 드롭다운에 별칭이 표시됩니다.
  
## <a name="related-content"></a>관련 콘텐츠

[다른 주소에서 전자 메일 보내기(문서)](https://support.microsoft.com/office/ccba89cb-141c-4a36-8c56-6d16a8556d2e)

[사용자 이름 및 전자 메일 주소](../add-users/change-a-user-name-and-email-address.md) 변경(문서)

[Microsoft 365에서 전자 메일 전달 구성](configure-email-forwarding.md)(문서)
