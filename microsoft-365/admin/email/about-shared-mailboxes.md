---
title: 공유 사서함 정보
f1.keywords:
- NOCSH
ms.author: sharik
author: SKjerland
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
- AdminTemplateSet
search.appverid:
- BCS160
- MET150
- MOE150
description: 공유 사서함은 여러 사용자가 동일한 사서함에 액세스해야 하는 경우 사용됩니다. 공유 사서함을 만들기 전에 알아야 할 내용을 알아보세요.
ms.openlocfilehash: d00c234179b67961da3003b5fccbe886158d11df
ms.sourcegitcommit: f9e038dd8420e7af2d1b0244d3567b376475c641
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/30/2021
ms.locfileid: "60011248"
---
# <a name="about-shared-mailboxes"></a>공유 사서함 정보

공유 사서함은 여러 사용자가 같은 사서함에 액세스해야 하는 경우(예: 회사 정보 또는 지원 전자 메일 주소, 리셉션 데스크 또는 여러 사용자에 의해 공유될 수도 있는 기타 기능)에 사용됩니다.

그룹 사서함에 대한 권한이 있는 사용자는 관리자가 해당 사용자에게 권한을 부여한 경우 사서함 전자 메일 주소를 보내기 혹은 대신하여 보낼 수 있습니다. 이 기능은 사용자가 "Contoso 지원" 또는 “A 빌딩 리셉션 데스크"에서 전자 메일을 보낼 수 있기 때문에 도움말 및 지원 사서함에 특히 유용합니다.

## <a name="before-you-begin"></a>시작하기 전에

공유 [사서함을 만들기 전에](create-a-shared-mailbox.md)알아야 할 몇 가지 항목은 다음과 같습니다.

- **라이선스:** 공유 사서함에 라이선스를 할당하지 않고도 최대 50GB의 데이터를 저장할 수 있습니다. 그 후에는 추가 데이터를 저장하도록 사서함에 라이선스를 할당해야 합니다. 공유 사서함 라이선스에 대한 자세한 내용은 제한 Exchange Online [참조하시기 바랍니다.](/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#StorageLimits) 공유 사서함이 저장소 한도에 도달하면 한동안 전자 메일을 받을 수 있지만, 새 전자 메일은 보낼 수 없습니다. 그런 다음 전자 메일 수신이 중단됩니다. 사서함에 보낸 사람에게 배달 못 함 메일이 전송됩니다.

- **사용자 권한:** 공유 사서함을 사용하려면 사용자에게 사용 권한(구성원 자격)을 부여해야 합니다. 공유 사서함은 조직 내부 사용자만 사용할 수 있습니다.

- **외부 사용자:** 비즈니스 외부 사용자(예: Gmail 계정이 있는 사용자)에게 공유 사서함에 대한 액세스 권한을 부여할 수 없습니다. 이렇게 하려면 대신 Outlook용 그룹을 만드는 것이 좋습니다. 자세한 내용은 관리 센터에서 Microsoft 365 [그룹 만들기를 참조하세요.](../create-groups/create-groups.md)

- **다음 Outlook.** 브라우저에서 웹용 Outlook 사용하여 공유 사서함에 액세스하는 것 외에도 iOS 앱용 Outlook Android 앱용 Outlook 사용할 수도 있습니다. 자세한 내용은 [Add a shared mailbox to Outlook.](https://support.microsoft.com/office/f866242c-81b2-472e-8776-6c49c5473c9f) 또 다른 옵션은 공유 사서함에 대한 그룹을 만드는 것입니다. 자세한 내용은 그룹 [비교를 참조합니다.](../create-groups/compare-groups.md)

- **암호화:** 공유 사서함에서 보낸 전자 메일을 암호화할 수 없습니다. 공유 사서함에는 자체 보안 컨텍스트(사용자 이름/암호)가 있으므로 키를 할당할 수 없습니다. 둘 이상의 사용자가 구성원인 경우 자신의 키로 암호화된 전자 메일을 보내고 받는 경우 다른 구성원은 전자 메일이 암호화된 공개 키에 따라 전자 메일을 읽을 수 있을 수 있으며 다른 구성원은 전자 메일을 읽을 수 없습니다.

- **사서함 변환:** 사용자 사서함을 공유 사서함으로 변환할 수 있습니다. [사용자 사서함을 공유 사서함으로 변환](convert-user-mailbox-to-shared-mailbox.md)을 참조하세요.

- **관리자 역할:** 전역 관리자 또는 Exchange 사용자가 공유 사서함을 만들 수 있습니다.

- **구독 요구 사항:** 공유 사서함을 만들하려면 전자 메일(Microsoft 365 서비스)이 포함된 비즈니스용 Exchange Online 구독해야 합니다. 비즈니스용 Microsoft 365 앱 구독에 전자 메일이 포함되어 없습니다. Microsoft 365 Business Standard 전자 메일이 포함됩니다.

- **로그인:** 공유 사서함은 연결된 사용자 계정으로 직접 로그인하기 위한 것이 아니며, 공유 사서함 계정에 대한 로그인을 항상 차단하고 차단된 유지해야 합니다.

- **사용자가 너무 많지 않습니다.** 지정된 사용자가 공유 사서함에 동시 액세스하는 사용자가 너무 많을 경우(25명 이상 권장) 이 사서함에 간헐적으로 연결하지 못하거나 보낼 편지함에 메시지가 중복되는 경우와 같은 불일치가 발생할 수 있습니다. 이 경우 사용자 수를 줄이거나 다른 작업(예: Microsoft 365 그룹 또는 공용 폴더)을 사용할 수 있습니다.

- **메시지 deletion:** 안타깝게도 사용자가 공유 사서함에서 메시지를 삭제하지 못하게 할 수 없습니다. 이 경우 공유 사서함 대신 Microsoft 365 그룹을 만들 수 있습니다. 그룹의 Outlook 공유 사서함과 같아야 합니다. 두 가지 비교는 [그룹 비교를 참조합니다.](../create-groups/compare-groups.md) 그룹에 대한 자세한 내용은 그룹에 대한 [자세한 정보를 참조합니다.](https://support.microsoft.com/office/b565caa1-5c40-40ef-9915-60fdb2d97fa2)


> [!NOTE]
> 공유 사서함에 액세스하려면 사용자에게 Exchange Online 라이선스가 있어야 하지만 공유 사서함에는 별도의 라이선스가 필요하지 않습니다. 모든 공유 사서함에는 해당하는 사용자 계정이 있습니다. 공유 사서함을 만들 때 암호를 입력하라는 메시지가 표시되지 않으면 어떻게 하나요? 계정에 암호가 있지만 시스템이 생성(알 수 없음)한 것입니다. 계정을 사용하여 공유 사서함에 로그인하면 안 됩니다. 라이선스가 없는 공유 사서함은 50GB로 제한됩니다. 크기 제한을 100GB로 늘리려면 공유 사서함에 Exchange Online 계획 2 라이선스가 할당되어야 합니다. 추가 Exchange Online 라이선스가 있는 Exchange Online Archiving 계획 1 라이선스는 보관 사서함의 크기만 증가합니다. 이렇게 하면 추가 보관 저장소 용량에 대해 자동 확장 보관을 사용하도록 설정할 수도 있습니다. 마찬가지로, 공유 사서함을 소송 보존에 추가하려면 공유 사서함에 Exchange Online 플랜 2 라이선스 또는 Exchange Online Archiving 추가 기능 라이선스가 있는 Exchange Online 플랜 1 라이선스가 있어야 합니다. Microsoft Defender for Office 365, Advanced eDiscovery 또는 자동 보존 정책과 같은 고급 기능을 적용하려면 해당 기능에 대해 공유 사서함의 사용이 허가되어야 합니다.

## <a name="related-content"></a>관련 콘텐츠

[공유 사서함](create-a-shared-mailbox.md) 만들기(문서)\
[공유 사서함 구성](configure-a-shared-mailbox.md)(문서)\
[사용자 사서함을 공유 사서함으로 변환](convert-user-mailbox-to-shared-mailbox.md)(문서)\
[공유 사서함에서 라이선스 제거](remove-license-from-shared-mailbox.md)(문서)\
[공유 사서함 문제 해결](resolve-issues-with-shared-mailboxes.md)(문서)
