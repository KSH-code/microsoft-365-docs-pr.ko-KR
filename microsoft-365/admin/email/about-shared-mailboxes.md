---
title: 공유 사서함 정보
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
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
description: 공유 사서함은 여러 사용자가 같은 사서함에 액세스 해야 하는 경우에 사용 됩니다. 공유 사서함을 만들기 전에 알아야 할 사항에 대해 알아봅니다.
ms.openlocfilehash: 6d9b7f59840b8eb4ce38822945066e14d9a86a4d
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/27/2020
ms.locfileid: "44400211"
---
# <a name="about-shared-mailboxes"></a>공유 사서함 정보

공유 사서함은 여러 사용자가 같은 사서함에 액세스해야 하는 경우(예: 회사 정보 또는 지원 전자 메일 주소, 리셉션 데스크 또는 여러 사용자에 의해 공유될 수도 있는 기타 기능)에 사용됩니다.

그룹 사서함에 대한 권한이 있는 사용자는 관리자가 해당 사용자에게 권한을 부여한 경우 사서함 전자 메일 주소를 보내기 혹은 대신하여 보낼 수 있습니다. 이 기능은 사용자가 "Contoso 지원" 또는 “A 빌딩 리셉션 데스크"에서 전자 메일을 보낼 수 있기 때문에 도움말 및 지원 사서함에 특히 유용합니다.

[공유 사서함을 만들기](create-a-shared-mailbox.md)전에 알아야 할 몇 가지 사항은 다음과 같습니다.

- **라이선스:** 공유 사서함에는 라이선스를 할당 하지 않고 최대 50GB의 데이터를 저장할 수 있습니다. 그 후에는 추가 데이터를 저장하도록 사서함에 라이선스를 할당해야 합니다. 공유 사서함 라이선스에 대 한 자세한 내용은 [Exchange Online 제한을](https://technet.microsoft.com/library/exchange-online-limits.aspx#StorageLimits)참조 하세요. 공유 사서함이 저장소 한도에 도달하면 한동안 전자 메일을 받을 수 있지만, 새 전자 메일은 보낼 수 없습니다. 그런 다음 전자 메일 수신이 중단됩니다. 사서함에 보낸 사람에게 배달 못 함 메일이 전송됩니다.

- **사용자 권한:** 공유 사서함을 사용 하려면 사용자에 게 사용 권한 (구성원)을 부여 해야 합니다. 공유 사서함은 조직 내부 사용자만 사용할 수 있습니다.

- **외부 사용자:** 회사 외부의 사용자 (예: Gmail 계정을 가진 사용자)에 게 공유 사서함에 대 한 액세스 권한을 부여할 수 없습니다. 이렇게 하려면 대신 Outlook용 그룹을 만드는 것이 좋습니다. 자세한 내용은 [관리 센터에서 Microsoft 365 그룹 만들기](../create-groups/create-groups.md)를 참조 하세요.

-  **Outlook에서 사용:** 브라우저에서 웹에 있는 Outlook을 사용 하 여 공유 사서함에 액세스 하는 것 외에도 iOS 용 Outlook 앱 또는 Android 용 Outlook 사용 앱을 사용할 수도 있습니다. 자세한 내용은 <a href="https://support.office.com/article/f866242c-81b2-472e-8776-6c49c5473c9f" target="_blank">Outlook mobile에 공유 사서함을 추가</a>합니다 .를 참조 하십시오. 또 다른 옵션으로는 공유 사서함에 대 한 그룹을 만들 수 있습니다. 자세한 내용은 [그룹 비교](../create-groups/compare-groups.md)를 참조 하십시오.  

- **암호화:** 공유 사서함에서 보낸 전자 메일은 암호화할 수 없습니다. 공유 사서함에는 키를 할당할 수 없도록 하는 자체 보안 컨텍스트 (사용자 이름/암호)가 없기 때문입니다. 두 명 이상이 구성원 인 경우 해당 사용자가 자신의 키를 사용 하 여 암호화 된 전자 메일을 전송/수신 하는 경우에는 다른 구성원이 메일을 암호화 한 공개 키에 따라 전자 메일이 읽기 어려울 수 있습니다.

- **사서함 변환:** 사용자 사서함을 공유 사서함으로 변환할 수 있습니다. [사용자 사서함을 공유 사서함으로 변환](convert-user-mailbox-to-shared-mailbox.md)을 참조하세요.

- **관리자 역할:** 전역 관리자 또는 Exchange 관리 역할이 있는 사용자는 공유 사서함을 만들 수 있습니다.

- **구독 요구 사항:** 공유 사서함을 만들려면 전자 메일 (Exchange Online 서비스)을 포함 하는 Microsoft 365 for business plan에 가입 해야 합니다. Microsoft 365 비즈니스용 앱 구독에는 전자 메일이 포함 되지 않습니다. Microsoft 365 비즈니스 표준에 해당 합니다.

- **로그인:** 공유 사서함은 연결 된 사용자 계정에의 한 직접 로그인이 아닙니다. 공유 사서함 계정의 로그인은 항상 차단 하 고 차단 된 상태로 유지 해야 합니다.

- **사용자가 너무 많음:** 공유 사서함에 동시에 액세스 하는 지정 된 사용자가 너무 많으면 일시적으로이 사서함에 연결 하지 못할 수 있습니다. 이 경우 사용자 수를 줄이거나 Microsoft 365 그룹 또는 공용 폴더와 같은 다른 작업을 사용 하는 것을 고려할 수 있습니다.

- **메시지 삭제:** 아쉽게도 공유 사서함에서 메시지를 삭제 하는 것을 방지할 수는 없습니다. 이 문제를 해결 하는 유일한 방법은 공유 사서함 대신 Microsoft 365 그룹을 만드는 것입니다. Outlook의 그룹은 공유 사서함과 같습니다. 이 둘을 비교 하려면 [그룹 비교](../create-groups/compare-groups.md)를 참조 하세요. 그룹에 대 한 자세한 내용은 [그룹에 대 한 자세한](https://support.office.com/article/b565caa1-5c40-40ef-9915-60fdb2d97fa2.aspx)정보를 참조 하십시오.

## <a name="related-articles"></a>관련 문서

[공유 사서함 만들기](create-a-shared-mailbox.md)

[공유 사서함 구성](configure-a-shared-mailbox.md)

[사용자 사서함을 공유 사서함으로 변환](convert-user-mailbox-to-shared-mailbox.md)

[공유 사서함에서 라이선스 제거](remove-license-from-shared-mailbox.md)

[공유 사서함의 문제 해결](resolve-issues-with-shared-mailboxes.md)
