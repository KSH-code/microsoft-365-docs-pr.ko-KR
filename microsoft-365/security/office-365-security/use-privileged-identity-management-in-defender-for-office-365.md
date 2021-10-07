---
title: Office 365용 Microsoft Defender에서 Azure PIM(Privileged Identity Management)을 사용하여 사이버 보안 도구에 대한 관리자 액세스를 제한합니다.
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 09/03/2021
audience: ITPro
ms.topic: article
ms.localizationpriority: high
search.appverid:
- MET150
ms.assetid: 56fee1c7-dc37-470e-9b09-33fff6d94617
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
ms.custom:
- seo-marvel-apr2020
description: 사용자가 Office 365용 Microsoft Defender에서 상승된 권한 작업을 수행하여 데이터에 대한 위험을 낮출 수 있도록 시간이 제한된 Just-In-Time 액세스 권한을 부여하기 위해 Azure PIM을 통합하는 방법을 알아보세요.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 9ea618a24c14aa49973ae05287a65cbb756f5467
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2021
ms.locfileid: "60196288"
---
<!--A-->
# <a name="privileged-identity-management-pim-and-why-to-use-it-with-microsoft-defender-for-office-365"></a>PIM(Privileged Identity Management) 및 Office 365용 Microsoft Defender와 함께 사용해야 하는 이유

PIM(Privileged Identity Management)은 일단 설정되면 특정 작업을 수행할 수 있도록 제한된 기간(시간 제한 기간이라고도 함) 동안 사용자에게 데이터에 대한 액세스 권한을 부여하는 Azure 기능입니다. 이 액세스 권한은 필요한 작업을 수행하기 위해 'Just-In-Time로 부여된 다음 취소됩니다. PIM은 사용자가 중요한 데이터에 액세스해야 하는 시간과 시간을 제한하여 데이터 및 기타 설정에 장기간 액세스할 수 있는 권한 있는 관리 계정과 비교할 때 노출 위험을 줄입니다. 그렇다면 이 기능(PIM)을 Office 365용 Microsoft Defender와 함께 어떻게 사용할 수 있을까요?

> [!TIP]
> PIM 액세스는 역할 및 ID 수준으로 범위가 지정되며 여러 작업을 완료할 수 있습니다. 작업 수준에서 범위가 지정된 PAM(Privileged Access Management)과 혼동하지 마세요.

## <a name="steps-to-use-pim-to-grant-just-in-time-access-to-defender-for-office-365-related-tasks"></a>PIM을 사용하여 Office 365용 Defender 관련 작업에 대한 Just-In-Time 액세스 권한을 부여하는 단계

관리자는 Office 365용 Microsoft Defender와 함께 작동하도록 PIM을 설정하여 사용자가 필요한 작업을 수행하기 위해 액세스를 요청하는 프로세스를 만듭니다. 사용자는 권한 상승이 필요한 *이유를 설명* 해야 합니다.

이 예에서는 Office 365 내에서 상시 액세스 권한은 없지만 [위협 헌팅](threat-hunting-in-threat-explorer.md)처럼 일상적인 작업에 필요한 역할로 승격할 수 있는 보안 팀의 구성원인 "Alex"를 구성할 예정이며, [악의적인 전달된 이메일 교정](remediate-malicious-email-delivered-office-365.md)과 같이 빈도가 낮지만 중요한 작업이 필요한 경우 권한 수준을 높일 수 있습니다.

> [!NOTE]
> 이 예제는 Office 365용 Microsoft Defender에서 위협 탐색기를 사용하여 전자 메일을 제거하는 기능이 필요한 보안 분석가를 위해 PIM을 설정하는 데 필요한 단계를 안내하지만 보안 및 규정 준수 포털 내의 다른 RBAC 역할에 동일한 단계를 사용할 수 있습니다. 예를 들어 이 프로세스는 검색 및 케이스 작업을 수행하기 위해 매일 eDiscovery에 액세스해야 하지만 테넌트에서 데이터를 내보낼 수 있는 승격된 권한이 필요한 정보 작업자에게 사용할 수 있습니다.

***1단계***. 구독에 대한 Azure PIM 콘솔에서 사용자(Alex)를 Azure 보안 리더 역할에 추가하고 활성화와 관련된 보안 설정을 구성합니다.

1. [Azure AD 관리 센터](https://aad.portal.azure.com/)에 로그인하고 **Azure Active Directory** > **역할 및 관리자** 를 선택합니다.
2. 역할 목록에서 **보안 리더** 를 선택한 다음 **설정** > **편집** 을 선택합니다.
3. '**활성화 최대 기간(시간)**'을 정상 근무일로 설정하고 '활성화 시'에 **Azure MFA** 를 요구하도록 설정합니다.
4. 이것은 일상적인 작업에 대한 Alex의 일반 권한 수준이므로 **활성화 시 사유 필요**' > **업데이트** 를 선택 취소합니다.
5. **할당 추가** > **선택한 구성원 없음** > 이름을 선택하거나 입력하여 올바른 구성원을 검색을 선택합니다.
6. **선택** 버튼을 클릭하여 PIM 권한에 추가해야 하는 구성원을 선택하고 **다음** > 할당 추가 페이지에서 변경하지 않음(두 할당 유형 모두 *적격* 기간은 *영구 적격* 이 기본값임) 및 **할당** 을 클릭합니다.

사용자 이름(여기서는 'Alex')은 다음 페이지의 적격 할당 아래에 표시됩니다. 즉, 이전에 구성된 설정으로 역할에 PIM할 수 있음을 의미합니다.

> [!NOTE]
> Privileged Identity Management에 대한 간략한 검토는 [이 동영상](https://www.youtube.com/watch?v=VQMAg0sa_lE)을 참조하세요.

:::image type="content" source="../../media/pim-mdo-role-setting-details-for-security-reader-show-8-hr-duration.png" alt-text="Privileged Access Management에서 보안 리더 역할에 대한 설정을 검색해야 합니다. 여기에서는 PIM 활성화의 최대 기간이 8시간임을 알 수 있습니다.":::

***2단계***. 추가 작업에 필요한 두 번째(승격된) 권한 그룹을 만들고 자격을 할당합니다.

[권한 있는 액세스 그룹](/azure/active-directory/privileged-identity-management/groups-features)을 사용하여 이제 자체 사용자 지정 그룹을 만들고 권한을 결합하거나 조직의 관행 및 요구 사항을 충족하는 데 필요한 세분성을 높일 수 있습니다.

### <a name="create-a-role-group-requiring-the-permissions-we-need"></a>필요한 권한을 요구하는 역할 그룹을 만듭니다.

보안 포털에서 원하는 권한이 포함된 사용자 지정 역할 그룹을 만듭니다.

1. Microsoft 365 Defender 포털(https://security.microsoft.com)로 이동하여  > **권한 및 역할** > 이메일 및 공동 작업 **역할** > **만들기** 를 선택합니다.
2. 'PIM 검색 및 제거'와 같은 목적을 반영하도록 그룹 이름을 지정합니다.
3. 구성원을 추가하지 말고 그룹을 저장하고 다음 부분으로 이동하세요!

### <a name="create-the-security-group-in-azure-ad-for-elevated-permissions"></a>상승된 권한을 위해 Azure AD에서 보안 그룹 만들기

1. [Azure AD 관리 센터](https://aad.portal.azure.com/)로 돌아가서 **Azure AD** > **그룹** > **새 그룹** 으로 이동합니다.
2. 목적을 반영하도록 AAD 그룹의 이름을 지정합니다. 지금은 **소유자나 구성원이 필요하지 않습니다**.
3. **Azure AD 역할을 그룹에 할당할 수 있음** 을 **예** 로 설정합니다.
4. 역할, 구성원 또는 소유자를 추가하지 말고 그룹을 만드세요.
5. 방금 만든 그룹으로 돌아가서 **권한 있는 액세스** > **권한 있는 액세스 사용** 을 선택합니다.
6. 그룹 내에서 **적격 할당** > **할당 추가** > 검색 및 삭제가 필요한 사용자를 **구성원** 역할로 추가를 선택합니다.
7. 그룹의 권한 있는 액세스 창에서 **설정** 을 구성합니다. **구성원** 역할에 대한 설정을 **편집** 하도록 선택합니다.
8. 조직에 맞게 활성화 시간을 변경하세요. 이 예에서는 **업데이트** 를 선택하기 전에 *Azure MFA*, *사유* 및 *티켓 정보* 가 필요합니다.

### <a name="nest-the-newly-created-security-group-into-the-role-group"></a>새로 생성된 보안 그룹을 역할 그룹에 중첩합니다.

1. [보안 및 규정 준수 센터 PowerShell에 연결](/powershell/exchange/connect-to-scc-powershell)하고 다음을 실행합니다.

    `Add-RoleGroupMember "<<Role Group Name>>" -Member "<<Azure Security Group>>"`

## <a name="test-your-configuration-of-pim-with-defender-for-office-365"></a>Office 365용 Defender로 PIM 구성 테스트

1. 이 시점에서 [Microsoft 365 Defender 포털](/microsoft-365/security/defender/overview-security-center) 내에서 관리 액세스 권한이 없어야 하는 테스트 사용자(Alex)로 로그인합니다.
2. 사용자가 일상적인 보안 리더 역할을 활성화할 수 있는 PIM으로 이동합니다.
3. 위협 탐색기를 사용하여 이메일을 제거하려고 하면 추가 권한이 필요하다는 오류가 표시됩니다.
4. PIM을 두 번째로 더 높은 역할로 변경하면 잠시 후 이제 문제 없이 이메일을 삭제할 수 있습니다.

   :::image type="content" source="../../media/pim-mdo-add-the-search-and-purge-role-assignment-to-this-pim-role.PNG" alt-text="보안 리더 PIM 역할을 통해 추가한 사용자(Alex)가 의심스러운 이메일을 삭제하려고 하면 '이 이메일에 조치를 취하려면 검색 및 제거 역할이 필요합니다. 역할 할당을 받거나 인시던트에 이메일을 추가하려면 관리자에게 문의하세요'라는 메시지를 받게 됩니다.":::

검색 및 제거 역할과 같은 관리 역할 및 권한의 영구 할당은 제로 트러스트 보안 이니셔티브와 관련이 없지만, 보이는 것처럼 을 사용하여 필요한 도구 세트에 대한 Just-In-Time 액세스 권한을 부여할 수 있습니다.

*블로그 게시물과 이 콘텐츠에 사용된 리소스에 액세스할 수 있게 해 준 고객 엔지니어 Ben Harris에게 감사드립니다.*

<!--A-->