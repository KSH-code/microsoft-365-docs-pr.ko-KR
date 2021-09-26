---
title: 전자 메일 전달 구성
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
ms.custom:
- MSStore_Link
- AdminSurgePortfolio
- okr_smb
- AdminTemplateSet
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: ab5eb117-0f22-4fa7-a662-3a6bdb0add74
description: 전자 메일 전달을 사용하면 조직 내부 또는 외부의 다른 사서함으로 Microsoft 365 전자 메일 메시지를 전달할 수 있습니다.
ms.openlocfilehash: 6703e37c1f576a5f3b0671def764deafa7e2daa2
ms.sourcegitcommit: aebcdbef52e42f37492a7f780b8b9b2bc0998d5c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2021
ms.locfileid: "59774691"
---
# <a name="configure-email-forwarding-in-microsoft-365"></a>전자 메일 전달 구성 Microsoft 365

조직의 관리자는 사용자 사서함에 대한 전자 메일 전달을 설정해야 하는 회사 요구 사항이 있을 수 있습니다. 전자 메일 전달을 사용하면 사용자 사서함으로 전송된 전자 메일 메시지를 조직 내부 또는 외부의 다른 사용자의 사서함으로 전달할 수 있습니다.

> [!IMPORTANT]
> 아웃바운드 스팸 필터 정책을 사용하여 외부 받는 사람에게 자동 전달을 제어할 수 있습니다. 자세한 내용은 에서 자동 외부 전자 메일 전달 [제어를 Microsoft 365.](/microsoft-365/security/office-365-security/external-email-forwarding#how-the-outbound-spam-filter-policy-settings-work-with-other-automatic-email-forwarding-controls)

## <a name="configure-email-forwarding"></a>전자 메일 전달 구성

전자 메일 전달을 설정하기 전에 다음에 유의하세요.

- 원격 도메인의 사용자에 자동으로 전달된 메시지를 보낼 수 있도록 허용합니다. 자세한 [내용은 원격 도메인](/exchange/mail-flow-best-practices/remote-domains/manage-remote-domains) 관리를 참조합니다.

- 전자 메일 전달을 설정하면  사서함으로 전송된  새 전자 메일만 전달됩니다.

- 전자 메일 전달을 사용하려면 시작  *계정에*  라이선스가 필요합니다. 사용자가 조직을 떠났기 때문에 전자 메일 전달을 설정하는 경우 사서함을 공유 사서함으로 변환하는 [옵션도 있습니다.](convert-user-mailbox-to-shared-mailbox.md) 이렇게 하면 여러 사람이 액세스할 수 있습니다. 그러나 공유 사서함은 50GB를 초과할 수 없습니다.

이러한 단계를 수행하려면 Exchange 관리자 또는 전역 관리자 Microsoft 365 해야 합니다. 자세한 내용은 관리자 역할 [정보를 참조하세요.](../add-users/about-admin-roles.md)

::: moniker range="o365-worldwide"

1. 관리 센터에서 사용자 활성 **사용자** \> **[페이지로](https://go.microsoft.com/fwlink/p/?linkid=834822)** 이동합니다.

2. 전자 메일을 전달할 사용자의 이름을 선택한 다음 속성 페이지를 여십시오.

3. 메일 **탭에서** 전자 메일 전달 **관리를 선택합니다.**

4. 전자 메일 전달 페이지에서 이 사서함에 전송된 모든 전자 메일 전달을 선택하고 전달 주소를 입력하고 전달된 전자 메일의 복사본을 유지할지 여부를 선택합니다. 이 옵션이 없는 경우 사용자 계정에 라이선스가 할당되어 있는지 확인 합니다. **변경 내용 저장** 을 선택합니다.

    여러 전자 메일 **주소로** 전달하기 위해 사용자에게 주소로 전달할 규칙을 Outlook 수 있습니다. 
    
    1.  Outlook **홈** > **규칙** > **>** **규칙 관리 & 열기**  
    1. 새 **규칙** 목록의 맨 아래에 있는 받은 메시지에 규칙 적용을 선택하고 >  다음 을 **클릭합니다.**
    1. 메시지가 **표시될** 때 예를 클릭합니다. 이 규칙은 받은 모든 메시지에 적용됩니다. 
    1. 다음 목록에서 작업을 선택하여 사용자 또는 공용 그룹으로 **리디렉션하고** 추가 규칙 **처리를 중지합니다.**
    1. 창의 아래쪽에서  밑조가 있는 구 사람 또는 공용 그룹을 클릭합니다.
    1. 전자 메일을 **전달할 전자** 메일 주소를 To 필드에 입력한 다음 확인 을 **클릭합니다.**
    1. 완료 **선택**
    

     또는 관리 센터에서 [](../setup/create-distribution-lists.md)메일 그룹 을 만들고 주소를 추가한 다음 이 문서의 지침을 사용하여 DL을 안내하는 전달을 설정할 수 있습니다. [](add-user-or-contact-to-distribution-list.md)

5. 전달할 전자 메일인 사용자의 계정을 삭제하거나 라이선스를 제거하지 않습니다.  이렇게 하면 전자 메일 전달이 중지됩니다.

::: moniker-end

::: moniker range="o365-germany"

1. 관리 센터에서 사용자 활성 **사용자** \> **[페이지로](https://go.microsoft.com/fwlink/p/?linkid=847686)** 이동합니다.

2. 전자 메일을 전달할 사용자의 이름을 선택하여 속성 페이지를 열 수 있습니다.

3. 메일 **설정을 확장하고** 전자 메일 전달 **섹션에서** 편집 을 **선택합니다.**

4. 전자 메일 전달 페이지에서 토글을 **으로** 설정하고 전달 주소를 입력하고 전달된 전자 메일의 복사본을 유지할지 여부를 선택합니다. 이 옵션이 없는 경우 사용자 계정에 라이선스가 할당되어 있는지 확인 합니다. **저장** 을 선택합니다.

   여러 전자 메일 **주소로** 전달하기 위해 사용자에게 주소로 전달할 규칙을 Outlook 수 있습니다. 자세한 내용은 규칙을 사용하여 메시지를 자동으로 [전달을 참조합니다.](https://support.microsoft.com/office/45aa9664-4911-4f96-9663-ece42816d746)

   또는 관리 센터에서 [](../setup/create-distribution-lists.md)메일 그룹 을 만들고 주소를 추가한 다음 이 문서의 지침을 사용하여 DL을 안내하는 전달을 설정할 수 있습니다. [](add-user-or-contact-to-distribution-list.md)

5. 전달할 전자 메일인 사용자의 계정을 삭제하거나 라이선스를 제거하지 않습니다.  이렇게 하면 전자 메일 전달이 중지됩니다.

::: moniker-end

::: moniker range="o365-21vianet"

1. 관리 센터에서 사용자 활성 **사용자** \> **[페이지로](https://go.microsoft.com/fwlink/p/?linkid=850628)** 이동합니다.

2. 전자 메일을 전달할 사용자의 이름을 선택하여 속성 페이지를 열 수 있습니다.

3. 메일 **설정을 확장하고** 전자 메일 전달 **섹션에서** 편집 을 **선택합니다.**

4. 전자 메일 전달 페이지에서 토글을 **으로** 설정하고 전달 주소를 입력하고 전달된 전자 메일의 복사본을 유지할지 여부를 선택합니다. 이 옵션이 없는 경우 사용자 계정에 라이선스가 할당되어 있는지 확인 합니다. **저장** 을 선택합니다.

   여러 전자 메일 **주소로** 전달하기 위해 사용자에게 주소로 전달할 규칙을 Outlook 수 있습니다. 자세한 내용은 규칙을 사용하여 메시지를 자동으로 [전달을 참조합니다.](https://support.microsoft.com/office/45aa9664-4911-4f96-9663-ece42816d746)

   또는 관리 센터에서 [](../setup/create-distribution-lists.md)메일 그룹 을 만들고 주소를 추가한 다음 이 문서의 지침을 사용하여 DL을 안내하는 전달을 설정할 수 있습니다. [](add-user-or-contact-to-distribution-list.md)

5. 전달할 전자 메일인 사용자의 계정을 삭제하거나 라이선스를 제거하지 않습니다. 이렇게 하면 전자 메일 전달이 중지됩니다.

::: moniker-end

## <a name="related-content"></a>관련 콘텐츠 

[공유 사서함](../email/create-a-shared-mailbox.md) 만들기(문서)\
[다른 주소에서 전자 메일](https://support.microsoft.com/office/ccba89cb-141c-4a36-8c56-6d16a8556d2e) 보내기(문서)\
[사용자 이름 및 전자 메일 주소](../add-users/change-a-user-name-and-email-address.md) 변경(문서)\
자동 외부 전자 메일 전달 [제어(Microsoft 365)](/microsoft-365/security/office-365-security/external-email-forwarding)


