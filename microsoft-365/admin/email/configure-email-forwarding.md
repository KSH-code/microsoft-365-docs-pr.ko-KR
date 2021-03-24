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
- Adm_TOC
ms.custom:
- MSStore_Link
- AdminSurgePortfolio
- okr_smb
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: ab5eb117-0f22-4fa7-a662-3a6bdb0add74
description: Office365를 사용하여 하나 이상의 전자 메일 계정으로 전자 메일 전달을 설정할 수 있습니다.
ms.openlocfilehash: cdefab3df59f1c57abbc221943b58c978ff582a9
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51050717"
---
# <a name="configure-email-forwarding-in-microsoft-365"></a>Microsoft 365에서 전자 메일 전달 구성

::: moniker range="o365-21vianet"

> [!NOTE]
> 관리 센터가 변경되고 있습니다. 사용자의 환경이 여기에 설명된 세부 정보와 맞지 않는 경우에는 [새 Microsoft 365 관리 센터 정보](../microsoft-365-admin-center-preview.md?preserve-view=true&view=o365-21vianet)를 참조하세요.

::: moniker-end

조직의 관리자는 사용자 사서함에 대한 전자 메일 전달을 설정해야 하는 회사 요구 사항이 있을 수 있습니다. 전자 메일 전달을 사용하면 사용자 사서함으로 전송된 전자 메일 메시지를 조직 내부 또는 외부의 다른 사용자의 사서함으로 전달할 수 있습니다.

> [!IMPORTANT]
> 아웃바운드 스팸 필터 정책을 사용하여 외부 받는 사람에게 자동 전달을 제어할 수 있습니다. 자세한 내용은 [Microsoft 365에서](https://docs.microsoft.com/microsoft-365/security/defender-365-security/external-email-forwarding?view=o365-worldwide&preserve-view=true#how-the-outbound-spam-filter-policy-settings-work-with-other-automatic-email-forwarding-controls)자동 외부 전자 메일 전달 제어를 참조하세요.

## <a name="configure-email-forwarding"></a>전자 메일 전달 구성

전자 메일 전달을 설정하기 전에 다음에 유의하세요.

- 전자 메일 전달을 설정하면  사서함으로 전송된  새 전자 메일만 전달됩니다.

- 전자 메일 전달을 사용하려면 시작  *계정에*  라이선스가 필요합니다. 사용자가 조직을 떠났기 때문에 전자 메일 전달을 설정하는 경우 사서함을 공유 사서함으로 변환하는 [옵션도 있습니다.](convert-user-mailbox-to-shared-mailbox.md) 이렇게 하면 여러 사람이 액세스할 수 있습니다. 그러나 공유 사서함은 50GB를 초과할 수 없습니다.

다음 단계를 수행하려면 Microsoft 365의 Exchange 관리자 또는 전역 관리자 되어야 합니다. 자세한 내용은 관리자 역할 [정보를 참조하세요.](../add-users/about-admin-roles.md)

::: moniker range="o365-worldwide"

1. 관리 센터에서 사용자 활성 **사용자** \> **[페이지로](https://go.microsoft.com/fwlink/p/?linkid=834822)** 이동합니다.

2. 전자 메일을 전달할 사용자의 이름을 선택하여 속성 페이지를 열 수 있습니다.

3. 메일 **탭에서** 전자 메일 전달 **관리를 선택합니다.**

4. 전자 메일 전달 페이지에서 이 사서함에 전송된 모든 전자 메일 전달을 선택하고 전달 주소를 입력하고 전달된 전자 메일의 복사본을 유지할지 여부를 선택합니다. 이 옵션이 없는 경우 사용자 계정에 라이선스가 할당되어 있는지 확인 합니다. **변경 내용 저장** 을 선택합니다.

    **여러 전자 메일 주소로** 전달할 경우 사용자에게 Outlook에서 주소로 전달할 규칙을 설정하도록 할 수 있습니다. 자세한 내용은 규칙을 사용하여 메시지를 자동으로 [전달을 참조합니다.](https://support.microsoft.com/office/45aa9664-4911-4f96-9663-ece42816d746)

     또는 관리 센터에서 [](../setup/create-distribution-lists.md)메일 그룹 을 만들고 주소를 추가한 다음 이 문서의 지침을 사용하여 DL을 안내하는 전달을 설정할 수 있습니다. [](add-user-or-contact-to-distribution-list.md)

5. 전달할 전자 메일인 사용자의 계정을 삭제하거나 라이선스를 제거하지 않습니다.  이렇게 하면 전자 메일 전달이 중지됩니다.

::: moniker-end

::: moniker range="o365-germany"

1. 관리 센터에서 사용자 활성 **사용자** \> **[페이지로](https://go.microsoft.com/fwlink/p/?linkid=847686)** 이동합니다.

2. 전자 메일을 전달할 사용자의 이름을 선택하여 속성 페이지를 열 수 있습니다.

3. 메일 **설정을 확장하고** 전자 메일 전달 **섹션에서** 편집 을 **선택합니다.**

4. 전자 메일 전달 페이지에서 토글을 **으로** 설정하고 전달 주소를 입력하고 전달된 전자 메일의 복사본을 유지할지 여부를 선택합니다. 이 옵션이 없는 경우 사용자 계정에 라이선스가 할당되어 있는지 확인 합니다. **저장** 을 선택합니다.

   **여러 전자 메일 주소로** 전달할 경우 사용자에게 Outlook에서 주소로 전달할 규칙을 설정하도록 할 수 있습니다. 자세한 내용은 규칙을 사용하여 메시지를 자동으로 [전달을 참조합니다.](https://support.microsoft.com/office/45aa9664-4911-4f96-9663-ece42816d746)

   또는 관리 센터에서 [](../setup/create-distribution-lists.md)메일 그룹 을 만들고 주소를 추가한 다음 이 문서의 지침을 사용하여 DL을 안내하는 전달을 설정할 수 있습니다. [](add-user-or-contact-to-distribution-list.md)

5. 전달할 전자 메일인 사용자의 계정을 삭제하거나 라이선스를 제거하지 않습니다.  이렇게 하면 전자 메일 전달이 중지됩니다.

::: moniker-end

::: moniker range="o365-21vianet"

1. 관리 센터에서 사용자 활성 **사용자** \> **[페이지로](https://go.microsoft.com/fwlink/p/?linkid=850628)** 이동합니다.

2. 전자 메일을 전달할 사용자의 이름을 선택하여 속성 페이지를 열 수 있습니다.

3. 메일 **설정을 확장하고** 전자 메일 전달 **섹션에서** 편집 을 **선택합니다.**

4. 전자 메일 전달 페이지에서 토글을 **으로** 설정하고 전달 주소를 입력하고 전달된 전자 메일의 복사본을 유지할지 여부를 선택합니다. 이 옵션이 없는 경우 사용자 계정에 라이선스가 할당되어 있는지 확인 합니다. **저장** 을 선택합니다.

   **여러 전자 메일 주소로** 전달할 경우 사용자에게 Outlook에서 주소로 전달할 규칙을 설정하도록 할 수 있습니다. 자세한 내용은 규칙을 사용하여 메시지를 자동으로 [전달을 참조합니다.](https://support.microsoft.com/office/45aa9664-4911-4f96-9663-ece42816d746)

   또는 관리 센터에서 [](../setup/create-distribution-lists.md)메일 그룹 을 만들고 주소를 추가한 다음 이 문서의 지침을 사용하여 DL을 안내하는 전달을 설정할 수 있습니다. [](add-user-or-contact-to-distribution-list.md)

5. 전달할 전자 메일인 사용자의 계정을 삭제하거나 라이선스를 제거하지 않습니다.  이렇게 하면 전자 메일 전달이 중지됩니다.

::: moniker-end