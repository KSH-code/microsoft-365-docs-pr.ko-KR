---
title: 고객 키 설정
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 02/05/2020
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
description: Exchange Online, 비즈니스용 Skype, SharePoint Online, 비즈니스용 OneDrive 및 Teams 파일에 대해 Microsoft 365 고객 키를 설정하는 방법을 알아보세요.
ms.openlocfilehash: 87c18c1695d2963fc8a0c064d34d2b6cdc14199c
ms.sourcegitcommit: 260bbb93bbda62db9e88c021ccccfa75ac39a32e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/21/2020
ms.locfileid: "46845836"
---
# <a name="set-up-customer-key"></a>고객 키 설정

고객 키를 사용하여 조직의 암호화 키를 제어하고 Microsoft365를 구성 및 사용하여 Microsoft의 데이터 센터의 미사용 데이터를 암호화할 수 있습니다. 즉, 고객 키를 사용하면 고객이 키를 사용하여 속한 암호화 계층을 추가할 수 있습니다. 미사용 데이터에는 SharePoint Online 및 비즈니스용 OneDrive에 저장되어 있는 사서함과 파일에 저장된 Exchange Online 및 비즈니스용 Skype의 데이터를 포함합니다.

Office 365에 대한 고객 키를 사용하려면 먼저 Azure를 설정해야 합니다. 이 항목에서는 필수 Azure 리소스를 만들고 구성하고 Office 365에서 고객 키를 설정하는 단계를 설명합니다. Azure 설정을 완료한 후 조직의 사서함 및 파일에 할당할 정책과 어떤 키를 결정합니다. 정책을 할당하지 않은 사서함과 파일은 Microsoft에서 제어 및 관리하는 암호화 정책을 사용합니다. 고객 키 또는 일반 개요에 대한 자세한 내용은 [Office 365의 고객 키를 사용한 서비스 암호화를 참조하세요.](customer-key-overview.md)
  
> [!IMPORTANT]
> 이 항목의 모범 사례를 따르는 것이 좋습니다. **TIP** 및 IMPORTANT라고 **합니다.** 고객 키를 사용하면 전체 조직만큼 범위를 가할 수 있는 루트 암호화 키를 제어할 수 있습니다. 다시 말해 이러한 키를 사용한 실수로 발생하는 실수로 인해 광범위한 영향을 미치고 데이터가 중단되거나 해지할 수 있습니다.
  
## <a name="before-you-set-up-customer-key"></a>고객 키 설정 전

시작하기 전에 조직에 적합한 라이선스가 제공되었는지 확인합니다. Microsoft 365의 고객 키는 Office 365 E5 또는 고급 규정 준수 SKU에서 제공됩니다. 이 항목의 개념과 절차를 이해하려면 Azure [Key Vault 설명서를 검토합니다.](https://docs.microsoft.com/azure/key-vault/) 또한 Azure에서 사용되는 용어(예: 테넌트)에 익숙해지도록 [합니다.](https://docs.microsoft.com/previous-versions/azure/azure-services/jj573650(v=azure.100))

FastTrack은 고객 키를 등록하는 데 사용되는 필요한 테넌트 및 서비스 구성 정보를 수집하는 데만 사용됩니다. 고객 키 제안은 FastTrack을 통해 게시되므로 편리하면서와 파트너가 동일한 방법을 사용하여 필요한 정보를 제출할 수 있습니다. FastTrack은 판매에서 제공하는 데이터를 보관하기도 한편 편리합니다.
  
설명서 이후에 추가적인 지원이 필요한 경우에는 MCS(Microsoft Consulting Services), PFE(프리미어 필드 엔지니어링) 또는 Microsoft 파트너에게 도울수가 있습니다. 설명서를 포함하여 고객 키에 대한 의견을 제공하려면 고객의 아이디어, 제안 사항 및 기술 정보를 customerkeyfeedback@microsoft.com.
  
## <a name="overview-of-steps-to-set-up-customer-key"></a>고객 키 설정 단계 개요

고객 키를 설정하려면 이러한 작업을 나열된 순서대로 완료합니다. 이 문서의 나머지 부분에서는 각 작업에 대한 자세한 지침을 제공하거나 프로세스의 각 단계에 대한 추가 정보를 연결합니다.
  
**Azure 및 Microsoft FastTrack의 내용:**
  
Azure PowerShell에 원격으로 연결하여 이러한 작업 대부분을 완료합니다. 최상의 결과를 얻을 수 있도록 Azure PowerShell 버전 4.4.0 이상을 사용하세요.
  
- [새 Azure 구독 2개를 만듭니다.](#create-two-new-azure-subscriptions)

- [필수 보존 기간을 사용하도록 Azure 구독 등록](#register-azure-subscriptions-to-use-a-mandatory-retention-period)

  등록은 일주일-5일(업무일)에 이를 걸 릴리게 할 수 있습니다.

- [Office 365의 고객 키 인증 요청을 제출합니다.](#submit-a-request-to-activate-customer-key-for-office-365)

Azure 구독 2개를 만들었으면 Microsoft FastTrack 포털에서 호스트되는 웹 양식을 작성하여 적절한 고객 키 제공 요청을 제출해야 합니다. **FastTrack 팀은 고객 키에 대한 지원을 제공하지 않습니다. Office에서는 단순히 FastTrack 포털을 사용하여 양식을 제출하고 고객 키에 대한 관련 제품을 추적하는 데 도움이 됩니다.**

- [구독마다 프리미어 Azure Key Vault 만들기](#create-a-premium-azure-key-vault-in-each-subscription)

- [각 키 상의에 사용 권한 할당](#assign-permissions-to-each-key-vault)

- [키 취미있는 경우 소미삭제를 사용하도록 설정하고 확인합니다.](#enable-and-then-confirm-soft-delete-on-your-key-vaults)

- [키를 만들거나 가져오는 방법으로 각 키 매개 키 변경 에키를 추가합니다.](#add-a-key-to-each-key-vault-either-by-creating-or-importing-a-key)

- [키의 복구 수준 확인](#check-the-recovery-level-of-your-keys)

- [Azure Key Vault 백업](#back-up-azure-key-vault)

- [Azure Key Vault 구성 설정 확인](#validate-azure-key-vault-configuration-settings)

- [각 Azure Key Vault 키의 URI 가져오기](#obtain-the-uri-for-each-azure-key-vault-key)

**Office 365의 경우**
  
Exchange Online 및 비즈니스용 Skype:
  
- [Exchange Online 및 비즈니스용 Skype에 사용할 DEP(데이터 암호화 정책) 만들기](#create-a-data-encryption-policy-dep-for-use-with-exchange-online-and-skype-for-business)

- [사서함에 DEP 할당](#assign-a-dep-to-a-mailbox)

- [사서함 암호화 유효성 검사](#validate-mailbox-encryption)

SharePoint Online 및 비즈니스용 OneDrive:
  
- [각 SharePoint Online 및 비즈니스용 OneDrive 지역에 대한 DEP(데이터 암호화 정책) 만들기](#create-a-data-encryption-policy-dep-for-each-sharepoint-online-and-onedrive-for-business-geo)

- [SharePoint Online, 비즈니스용 OneDrive 및 Teams 파일에 대한 파일 암호화 유효성 검사](#validate-file-encryption)

## <a name="complete-tasks-in-azure-key-vault-and-microsoft-fasttrack-for-customer-key"></a>고객 키에 대한 Azure Key Vault 및 Microsoft FastTrack에서 작업 완료

Azure Key Vault에서 다음과 같은 작업을 완료합니다. Exchange Online 및 비즈니스용 Skype에 대해 고객 키를 설정하거나 SharePoint Online, 비즈니스용 OneDrive 및 Teams 파일에 대해 설정하거나 Office 365에서 지원되는 모든 서비스에 대해 고객 키를 설정하고 있는지와 관계없이 이러한 단계를 완료해야 합니다.
  
### <a name="create-two-new-azure-subscriptions"></a>새 Azure 구독 2개를 만듭니다.

고객 키에는 두 개의 Azure 구독이 필요합니다. 고객 키에 사용할 새 Azure 구독을 만드는 것이 가장 좋습니다. Azure Key Vault 키는 동일한 AAD(Azure Active Directory) 테넌트의 응용 프로그램에 대해 권한만 부여될 수 있으며, DEP가 할당되는 조직에 사용된 것과 동일한 Azure AD 테넌트를 사용하여 새 구독을 생성해야 합니다. 예를 들어 조직에서 전역 관리자 권한이 있는 회사 또는 학교 계정을 사용합니다. 자세한 단계는 조직으로 [Azure에 등록을 참조하세요.](https://azure.microsoft.com/documentation/articles/sign-up-organization/)
  
> [!IMPORTANT]
> 고객 키는 각 DEP(데이터 암호화 정책)에 대해 두 개의 키가 필요합니다. 이 작업을 수행하기 위해 두 개의 Azure 구독을 만듭니다. 모범 사례에 따르면 조직에 있는 별도의 구성원이 각 구독에서 하나의 키를 구성하는 것이 좋습니다. 또한 이러한 Azure 구독은 Office 365의 암호화 키를 관리하는 용도로만 사용해야 합니다. 이렇게 하면 운영자 중 한 명이 실수로 또는 의도적으로 삭제하거나 악의적으로 삭제하거나 관리하는 경우 조직을 보호할 수 있습니다. <br/> 고객 키와 함께 사용하기 위해 Azure Key Vault 리소스를 관리하는 데만 사용되는 새 Azure 구독을 설정하는 것이 좋습니다. 조직을 위해 만들 수 있는 Azure 구독 수에는 실용성이 없습니다. 이러한 모범 사례를 따르면 고객 키에서 사용되는 리소스를 관리하는 동시에 인간 오류의 영향을 최소화할 수 있습니다.
  
### <a name="submit-a-request-to-activate-customer-key-for-office-365"></a>Office 365의 고객 키 인증 요청을 제출합니다.

Azure 단계를 완료한 후 Microsoft FastTrack 포털에서 제품 요청을 [제출해야 합니다.](https://fasttrack.microsoft.com/) FastTrack 웹 포털을 통해 요청을 제출하면 Microsoft는 Azure Key Vault 구성 데이터와 제공한 연락처 정보를 확인합니다. 조직의 권한이 있는 관리자와 관련하여 제품 양식에서 선택한 사항은 고객 키 등록을 완료하는 데 중요하며 필수 사항입니다. 양식에서 선택한 조직의 관리자는 고객 키 데이터 암호화 정책과 함께 사용되는 모든 키를 해지 및 삭제하기 위한 요청의 신뢰성을 보보보하는 데 사용됩니다. Exchange Online 및 비즈니스용 Skype 범위에 대한 고객 키를 활성화하려면 이 단계를 한 번 수행하고 SharePoint Online 및 비즈니스용 OneDrive에 대한 고객 키를 활성화하려면 이 단계를 한 번 수행해야 합니다.
  
고객 키를 활성화하기 위해 제품을 제출하려면 다음 단계를 완료하세요.
  
1. 조직에서 전역 관리자 권한을 가지고 있는 회사 또는 학교 계정을 사용하여 [Microsoft FastTrack 포털에 로그인합니다.](https://fasttrack.microsoft.com/)

2. 로그인한 후 대시보드를 **찾습니다.**

3. 탐색 **모음에서** 배포를 **선택하거나** **정보 카드의 모든** 배포 **리소스보기를** 선택한 다음 현재 제품 목록을 검토합니다.

4. 사용자에게 적용되는 제품의 정보 카드를 선택합니다.

   - **Exchange Online 및 비즈니스용 Skype:** Exchange **Online 서비스용 암호화 키 요청 도움말을** 선택합니다.

   - **SharePoint Online, OneDrive 및 Teams 파일:** Choose the **Request encryption key help for Sharepoint and OneDrive** offer.

5. 제품 세부 정보를 검토한 후 **계속 2단계를 선택합니다.**

6. 적용 가능한 모든 세부 정보 및 요청된 정보를 제품 양식에 작성합니다. 조직 관리자가 암호화 키와 데이터의 영구 적독 및 영구 소파 대독을 승인할 권한을 부여하려는 특정 사용자의 선택에 특히 주의해야 합니다. 양식을 완료한 후 전송을 **선택합니다.**

### <a name="register-azure-subscriptions-to-use-a-mandatory-retention-period"></a>필수 보존 기간을 사용하도록 Azure 구독 등록

루트 암호화 키가 일시적으로 또는 영구적으로 손실되면 부상이 발생하거나 서비스 작업에 치명적이 생길 수 있기 어려우며 데이터 손실이 발생할 수 있습니다. 따라서 고객 키와 함께 사용되는 리소스는 강력한 보호가 필요합니다. 고객 키와 함께 사용되는 모든 Azure 리소스는 기본 구성 이후 보호 메커니즘을 제공합니다. Azure 구독은 즉시 취소할 수 없는 취소를 방지하는 방식으로 태그를 지정하거나 등록할 수 있습니다. 이것을 필수 보존 기간에 등록하는 것을 의미합니다. 필수 보존 기간 동안 Azure 구독을 등록하는 데 필요한 단계는 Microsoft 365 팀과 공동의 공동 작업이 필요합니다. 이 프로세스는 업무 일주일 1일에서 5일까지 걸릴 수 있습니다. 이전에는 이 작업을 "취소 안 함"이라고도 했습니다.
  
Microsoft 365 팀에 연락하기 전에 고객 키와 함께 사용하는 각 Azure 구독에 대해 다음 단계를 수행해야 합니다. 시작하기 전에 [Azure PowerShell Az 모듈이](https://docs.microsoft.com/powershell/azure/new-azureps-module-az) 설치되어 있는지 확인합니다.
  
1. Azure PowerShell을 사용하여 로그인합니다. 지침은 Azure [PowerShell로 로그인을 참조하세요.](https://docs.microsoft.com/powershell/azure/authenticate-azureps)

2. Register-AzProviderFeature cmdlet를 실행하여 필수 보존 기간을 사용하도록 구독을 등록합니다. 각 구독에 대해 이 작업을 수행합니다.

   ```powershell
   Set-AzContext -SubscriptionId <SubscriptionId>
   Register-AzProviderFeature -FeatureName mandatoryRetentionPeriodEnabled -ProviderNamespace Microsoft.Resources
   ```

3. 프로세스를 완료하려면 Microsoft에 문의하세요. SharePoint 및 비즈니스용 OneDrive 팀의 경우 다음 [spock@microsoft.com.](mailto:spock@microsoft.com) Exchange Online 및 비즈니스용 Skype에 대 한 [exock@microsoft.com.](mailto:exock@microsoft.com) 전자 메일에 다음을 포함합니다.

   **제목**: 다음에 대한 고객 키 \<*Your tenant's fully-qualified domain name*\>

   **본문:** 필수 보존 기간을 마무리할 수 있는 구독 ID입니다.
   각 구독에 대한 Get-AzProviderFeature의 출력.

   Microsoft가 필수 보존 기간을 사용하도록 구독을 등록하고(확인)되었음을 계속 통보한 후 이 프로세스 완료를 위한 SLA(서비스 수준 계약)는 영업일로 5일로 되어 있습니다.

4. Microsoft로부터 알림을 받으면 다음과 같이 Get-AzProviderFeature 명령을 실행하여 등록 상태를 확인합니다. verified이면 Get-AzProviderFeature 명령이 등록 상태 **속성에 등록됨** **값을 반환합니다.** 각 구독에 대해 이 작업을 수행합니다.

   ```powershell
   Set-AzContext -SubscriptionId <SubscriptionId>
   Get-AzProviderFeature -ProviderNamespace Microsoft.Resources -FeatureName mandatoryRetentionPeriodEnabled
   ```

5. 프로세스를 완료하려면 Register-AzResourceProvider 명령을 실행합니다. 각 구독에 대해 이 작업을 수행합니다.

   ```powershell
   Set-AzContext -SubscriptionId <SubscriptionId>
   Register-AzResourceProvider -ProviderNamespace Microsoft.KeyVault
   ```

### <a name="create-a-premium-azure-key-vault-in-each-subscription"></a>구독마다 프리미어 Azure Key Vault 만들기

핵심 소프트웨어를 만드는 단계는 Azure Key [Vault](https://azure.microsoft.com/documentation/articles/key-vault-get-started/)시작에 문서화되어 있으며 이는 Azure PowerShell 설치 및 실행, Azure 구독에 연결, 리소스 그룹 만들기 및 해당 리소스 그룹에 키 상이 판결생성을 안내합니다.
  
키 상이스를 만들 때는 Standard 또는 Premium 중 SKU를 선택해야 합니다. Standard SKU를 사용하면 소프트웨어를 통해 Azure Key Vault 키를 보호할 수 있습니다. HSM(하드웨어 보안 모듈) 키 보호가 없고, Premium SKU는 키 Vault 키를 보호하는 데 HSM을 사용할 수 있도록 해줍니다. 고객 키는 SKU를 사용하는 키 상취를 수락합니다. 하지만 Microsoft는 개발자가 Premium SKU만 사용하도록 권장합니다. 키 가어있는 연산 비용은 동일합니다. 따라서 유일한 비용 차이는 각 HSM 보호 키의 월 순위와 같습니다. 자세한 [내용은 Key Vault 가격 책정을](https://azure.microsoft.com/pricing/details/key-vault/) 참조하세요.
  
> [!IMPORTANT]
> 프로덕션 데이터에 Premium SKU 키 vaults 및 HSM 보호 된 키를 사용하고 테스트 및 유효성 검사용으로는 표준 SKU 키 오류 및 키만 사용합니다.
  
고객 키를 사용할 각 Microsoft 365 서비스에 대해, 만들었은 두 개의 각 Azure 구독에 키 매개 변수를 만드세요. 예를 들어 Exchange Online과 비즈니스용 Skype 전용 또는 SharePoint Online 및 비즈니스용 OneDrive 전용에 한합니다. 하지만 한 쌍의 오류만 만들게 됩니다. Exchange Online 및 SharePoint Online 모두에 대한 고객 키를 사용하려면 두 쌍의 키 오류를 만듭니다.
  
취자를 연결할 데이터 암호화 정책의 용도를 반영하는 키 저장소에 대한 명명 규칙을 사용합니다. 명명 규칙 권장 사항은 아래 모범 사례 섹션을 참조하세요.
  
각 데이터 암호화 정책에 대해 쌍으로 연결된 설치 모음을 만듭니다. Exchange Online의 경우 정책을 사서함에 할당할 때 데이터 암호화 정책의 범위가 선택됩니다. 사서함에는 정책이 하나만 할당될 수 있습니다. 하나의 정책에 여러 정책을 만들 수 있습니다. SharePoint Online의 경우 정책 범위는 지리적 위치 또는 지리적 위치에 있는 조직 내의 모든 _데이터입니다._

키 자격함을 만들려면 키 자격이 없지만 저장소 용량이(매우 작은) 및 Key Vault 로깅(사용하도록 설정된 경우)이 하므로 이러한 그룹도 만들면 됩니다. Microsoft는 별도의 관리자를 사용하여 모든 관련된 고객 키 리소스를 관리하는 관리자 집합에 따라 각 리소스 그룹을 관리하는 것이 좋다는 권장 사항입니다.
  
> [!IMPORTANT]
> 가용성을 최대화하려면 키 저장소가 Microsoft 365 서비스와 가까이 지역에 있어야 합니다. 예를 들어 Exchange Online 조직이 북미에 있는 경우 키 음성을 북미에 배치합니다. Exchange Online 조직이 유럽에 있는 경우 유럽에 주요 vault를 배치합니다.<br/>키 매개 변수로 일반적인 접두사 사용: 여기에는 키 vault와 키(예: 모음이 북미에 위치할 Contoso SharePoint 서비스의 경우)의 사용 및 범위를 간략하게 포함할 수 있습니다. 이름 쌍은 Contoso-O365SP-NA-VaultA1 및 Contoso-O365SP-NA-VaultA2입니다. Vault 이름은 Azure 내에서 전역적으로 고유문자열이므로, 원하는 이름은 다른 Azure 고객이 이미 클레임하는 경우 원하는 이름의 변형을 사용해 보아해야 할 수 있습니다. 2017년 7월 부과 이름을 변경할 수 없습니다. 따라서 설치에 대한 서면을 작성하고 두 번째 사람을 사용하여 계획이 올바르게 실행되었는지 확인하는 것이 가장 좋습니다.<br/>가능하면 페어링되지 않은 영역에서 휴가를 만드세요. 쌍이 있는 Azure 지역은 서비스 오류 도메인 간의 고가용성을 제공합니다. 따라서 지역 쌍은 다른 지역의 백업 지역으로 간과같이 확인될 수 있습니다. 즉 한 지역에 배치되는 Azure 리소스는 페어링된 영역을 통해 내결함성을 자동으로 보증합니다. 이러한 이유로 지역이 쌍으로 지정되는 데이터 암호화 정책에서 사용되는 두 개의 손에 대한 지역을 선택하면 총 두 가용성 지역을 만가지 유도하는 것입니다. 대부분의 지역에는 두 개의 지역만 사용하므로 아직 페어링되지 않은 영역을 선택할 수 없습니다. 가능한 경우 데이터 암호화 정책과 함께 사용되는 두 벤트에 대해 페어링되지 않은 두 지역을 선택합니다. 이 경우 총 네 가지 지역의 가용성 지역이 도움이 됩니다. 자세한 내용은 현재 지역 쌍 목록에 대한 Azure 페어링된 지역인 비즈니스용 연속성 및 [BCDR(재해 복구)을](https://docs.microsoft.com/azure/best-practices-availability-paired-regions) 참조하세요.
  
### <a name="assign-permissions-to-each-key-vault"></a>각 키 상의에 사용 권한 할당

각 키 오류에 대해 구현에 따라 고객 키에 대해 별도의 세 가지 권한 집합을 정의해야 합니다. 예를 들어 다음의 각 권한에 대해 권한을 하나씩 정의해야 합니다.
  
- **조직에 대한 키 취결함에** 대한 일상 적별 관리를 수행하는 주요 문제가 있는 경우 이러한 작업에는 백업, 만들기, 가져오기, 가져오기, 목록 및 복원이 포함됩니다.

  > [!IMPORTANT]
  > 키 매개 변수 관리자에게 할당된 권한 집합에는 키를 삭제할 수 있는 권한이 포함되지 않습니다. 이것은 의도적이며 중요한 한 가지 예입니다. 따라서 데이터를 영구적으로 삭제하는 것이므로 암호화 키를 삭제하는 작업은 일반적으로 수행되지 않습니다. 기본적으로 키 모음관리자에게 이 사용 권한을 부여하지 않도록 하는 것이 가장 좋습니다. 대신 초보 자료는 키 자격 증명을 유지하고 나중에 결과에 대한 명확한 지식을 이해한 다음 약간의 권한을 관리자에게 할당하십시오.
  
  조직의 사용자에게 이러한 사용 권한을 할당하려면 Azure PowerShell을 사용하여 Azure 구독에 로그인합니다. 지침은 Azure [PowerShell로 로그인을 참조하세요.](https://docs.microsoft.com/powershell/azure/authenticate-azureps)

- Set-AzKeyVaultAccessPolicy cmdlet을 실행하여 필요한 권한을 할당합니다.

   ```powershell
   Set-AzKeyVaultAccessPolicy -VaultName <vault name> -UserPrincipalName <UPN of user> -PermissionsToKeys create,import,list,get,backup,restore
   ```

   예시:

   ```powershell
   Set-AzKeyVaultAccessPolicy -VaultName Contoso-O365EX-NA-VaultA1 -UserPrincipalName alice@contoso.com -PermissionsToKeys create,import,list,get,backup,restore
   ```

- Azure Key **Vault 자체에서 권한을 변경할 수** 있는 주요 Vault 절차입니다. 이러한 권한을 변경하려면 직원이 팀을 떠나거나 여기에 참여하거나, 핵심 문제가 될 경우 관리자가 키를 삭제 또는 복원하기 위한 권한이 제대로 필요하다는 경우를 예로 들 수 있습니다. 이 주요 Vault 작업자가 키 나누기에 대한 **Contributor** 고객 역할을 부여해야 합니다. Azure Resource Manager를 사용하여 이 역할을 할당할 수 있습니다. 자세한 단계는 역할 [기반 액세스 제어를 사용하여 Azure 구독 리소스에 대한 액세스 관리를 참조하세요.](https://docs.microsoft.com/azure/active-directory/role-based-access-control-configure) 구독을 만드는 관리자가 이 액세스는 암시적으로 가지며 다른 관리자를 추가 자료 역할에 할당하는 기능도 있습니다.

- 고객 키를 Exchange Online 및 비즈니스용 Skype와 함께 사용하려면 Exchange Online 및 비즈니스용 Skype를 대신하여 키 상석자를 사용할 수 있는 권한을 Microsoft 365에 부여해야 합니다. 마찬가지로 SharePoint Online 및 비즈니스용 OneDrive에서 고객 키를 사용하려면 Microsoft 365에 대한 권한을 추가하여 SharePoint Online 및 비즈니스용 OneDrive를 대신하여 키 상이를 이용하라는 권한을 추가해야 합니다. Microsoft 365에 대한 권한을 제공하려면 다음 구문을 사용하여 **Set-AzKeyVaultAccessPolicy** cmdlet을 실행합니다. 

   ```powershell
   Set-AzKeyVaultAccessPolicy -VaultName <vault name> -PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName <Office 365 appID>
   ```

   여기서,

    - *vault name은* 만든 키 버트의 이름입니다.

    - Exchange Online 및 비즈니스용 Skype의 경우 *Office 365 appID를 다음으로 바꾸기*`00000002-0000-0ff1-ce00-000000000000`

    - SharePoint Online, 비즈니스용 OneDrive 및 Teams 파일의 경우 *Office 365 appID를 다음으로 바꿀 수 있습니다.*`00000003-0000-0ff1-ce00-000000000000`

  예: Exchange Online 및 비즈니스용 Skype에 대한 사용 권한 설정:

   ```powershell
   Set-AzKeyVaultAccessPolicy -VaultName Contoso-O365EX-NA-VaultA1 -PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName 00000002-0000-0ff1-ce00-000000000000
   ```

  예제: SharePoint Online, 비즈니스용 OneDrive 및 Teams 파일에 대한 사용 권한 설정:

   ```powershell
   Set-AzKeyVaultAccessPolicy -VaultName Contoso-O365SP-NA-VaultA1 -PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName 00000003-0000-0ff1-ce00-000000000000
   ```

### <a name="enable-and-then-confirm-soft-delete-on-your-key-vaults"></a>키 취미있는 경우 소미삭제를 사용하도록 설정하고 확인합니다.

키를 신속하게 복구할 수 있는 경우 특히 또는 악의적으로 삭제한 키로 인한 서비스 중단이 발생하는 경우가 줄어드는 경우가 있습니다. 고객 키로 키를 사용하려면 먼저 Soft Delete라는 이 구성을 사용하도록 해야 합니다. 일시 삭제를 사용하도록 설정해두면 백업에서 복원하지 않아도 90일 이내에 키 또는 오류가 발생할 수 있습니다.
  
키 매개 파일에서 Soft 삭제를 사용하려면 아래 단계를 완료하세요.
  
1. Windows Powershell을 사용하여 Azure 구독에 로그인합니다. 지침은 Azure [PowerShell로 로그인을 참조하세요.](https://docs.microsoft.com/powershell/azure/authenticate-azureps)

2. [Get-AzKeyVault cmdlet을 실행합니다.](https://docs.microsoft.com/powershell/module/az.keyvault/get-azkeyvault) 이 *예제에서는 이름은 삭제를* 사용하도록 설정하기 위한 키 모음의 이름입니다.

   ```powershell
   $v = Get-AzKeyVault -VaultName <vault name>
   $r = Get-AzResource -ResourceId $v.ResourceId
   $r.Properties | Add-Member -MemberType NoteProperty -Name enableSoftDelete -Value 'True'
   Set-AzResource -ResourceId $r.ResourceId -Properties $r.Properties
   ```

3. **Get-AzKeyVault** cmdlet을 실행하여 키 변경에 대해 소프트 삭제가 구성되어 있는지 확인합니다. 키 오류에 대해 소프트 삭제가 제대로 구성되어 있으면 _Soft Delete Enabled 속성이_ True 값을 **반환합니다.**

   ```powershell
   Get-AzKeyVault -VaultName <vault name> | fl
   ```

### <a name="add-a-key-to-each-key-vault-either-by-creating-or-importing-a-key"></a>키를 만들거나 가져오는 방법으로 각 키 매개 키 변경 에키를 추가합니다.

Azure Key Vault에 키를 추가하는 방법은 두 가지가 있습니다. Key Vault에서 직접 키를 만들거나 키를 가져올 수 있습니다. Key Vault에서 직접 키를 만드는 것은 복잡도가 없습니다. 키를 가져오면 전체 키 생성 방식을 제어할 수 있습니다.
  
키 매개 변수로 직접 키를 만들려면 다음과 [같이 Add-AzKeyVaultKey](https://docs.microsoft.com/powershell/module/az.keyvault/add-azkeyvaultkey) cmdlet을 실행합니다.
  
```powershell
Add-AzKeyVaultKey -VaultName <vault name> -Name <key name> -Destination <HSM|Software> -KeyOps wrapKey,unwrapKey
```

여기서,

- *vault* name은 키를 만들 키 모음의 이름입니다.

- *키 이름은* 새 키로 사용할 이름입니다.

  > [!TIP]
  > 키 vaults에 대해 위에 설명한 대로 유사한 명명 규칙을 사용하여 키 이름 지정 이렇게 하면 키 이름만 표시하는 도구에서는 문자열에 대해 설명이 필요합니다.
  
- HSM으로 키를 보호하려면 **HSM을** Destination 매개 변수의 값으로 지정하고, 그렇지 않으면 _Software를_ **지정합니다.**

예를 들면 다음과 같습니다.
  
```powershell
Add-AzKeyVaultKey -VaultName Contoso-O365EX-NA-VaultA1 -Name Contoso-O365EX-NA-VaultA1-Key001 -Destination Software -KeyOps wrapKey,unwrapKey
```

키 자격을 직접 키 자격에 가져오려면 nCipher nShield 하드웨어 보안 모듈이 필요합니다.
  
일부 조직에서는 키를 입증하기 위해 이 접근 방법을 선사한 후 이 방법에서 다음을 제공합니다.
  
- 가져오기에 사용되는 도구 집합에는 생성하는 키를 암호화하는 데 사용되는 키 KEK(키 교환 키)를 내보낼 수 없고 nCipher에서 제조한 일반 HSM 내에서 생성되는 nCipher의 증명이 포함됩니다.

- 이 도구 집합에는 nCipher에 의해 적정된 HSM 제조업체에서도 Azure Key Vault 보안 세계를 생성한다는 증명이 nCipher의 증명을 포함합니다. 이 증명은 Microsoft가 제네인 NCipher 하드웨어도 사용한다고 생각합니다.

보안 그룹을 확인하여 위의 증명이 필요한지 확인합니다. 온-프레미스로 키를 만들고 키 권한 으로 가져오는 자세한 단계는 [Azure Key Vault에 대한 HSM 보호 키를 생성하고 전송하는 방법을 참조하세요.](https://azure.microsoft.com/documentation/articles/key-vault-hsm-protected-keys/) Azure 지침을 사용하여 각 키 상취에 키를 만듭니다.
  
### <a name="check-the-recovery-level-of-your-keys"></a>키의 복구 수준 확인

Microsoft 365를 사용하려면 Azure Key Vault 구독이 취소 안 함으로 설정되고 고객 키에서 사용하는 키에 소재 삭제를 설정하도록 되어 있는지 확인해야 합니다. 키의 복구 수준을 확인하여 이를 확인할 수 있습니다.
  
키의 복구 수준을 확인하려면 Azure PowerShell에서 다음과 같이 Get-AzKeyVaultKey cmdlet을 실행합니다.
  
```powershell
(Get-AzKeyVaultKey -VaultName <vault name> -Name <key name>).Attributes
```

복구 _수준 속성이_ **Recoverable+ProtectedSubscription 값**이외의 값을 반환하는 경우 이 항목을 검토하고 구독을 취소하지 않음 목록에 추가하고 각 키 변경 시 점에 소재 삭제를 사용할 수 있도록 설정되었는지 확인해야 합니다.
  
### <a name="back-up-azure-key-vault"></a>Azure Key Vault 백업

키를 생성하거나 키를 변경한 후 바로 백업을 수행하고 온라인 및 오프라인으로 백업 복사본을 저장합니다. 오프라인 복사본은 물리적 안전한 저장소 시각이나 상용 저장소 시각 같은 네트워크에 연결되어서는 안 됩니다. 적어도 하나 이상의 백업 복사본은 재해가 발생하는 경우 액세스할 수 있는 위치에 저장되어야 합니다. 백업 Blob이 단지 복원되는 한가지 유일한 방법은 Key Vault 키를 영구적으로 삭제하거나 나서 운영할 수 없도록 렌더링한다는 점에서 유일한 방법입니다. Azure Key Vault 외부에서 Azure Key Vault로 가져온 키는 고객 키를 사용하는 데 필요한 메타데이터가 외부 키에 존재하지 않기 때문에 백업으로 제정되지 않습니다. 고객 키가 포함된 복원 작업에는 Azure Key Vault에서 가온 백업만 사용할 수 있습니다. 따라서 키를 업로드하거나 만들면 Azure Key Vault의 백업이 필요합니다.
  
Azure Key Vault 키의 백업을 만들려면 [다음과 같이 Backup-AzKeyVaultKey](https://docs.microsoft.com/powershell/module/az.keyvault/backup-azkeyvaultkey) cmdlet을 실행합니다.

```powershell
Backup-AzKeyVaultKey -VaultName <vault name> -Name <key name>
-OutputFile <filename.backup>
```

출력 파일에 접미사가 사용되는지 `.backup` 확인합니다.
  
이 cmdlet의 결과 출력 파일은 암호화되며 Azure Key Vault 이외의 에서 사용할 수 없습니다. 백업은 백업을 가도한 Azure 구독으로만 복원할 수 있습니다.
  
> [!TIP]
> 출력 파일에 대해 취미 이름과 키 이름을 조합하여 선택합니다. 그러면 파일 이름이 자체 설명됩니다. 이 백업 파일 이름도 통합되지 않도록 합니다.
  
예시:
  
```powershell
Backup-AzKeyVaultKey -VaultName Contoso-O365EX-NA-VaultA1 -Name Contoso-O365EX-NA-VaultA1-Key001 -OutputFile Contoso-O365EX-NA-VaultA1-Key001-Backup-20170802.backup
```

### <a name="validate-azure-key-vault-configuration-settings"></a>Azure Key Vault 구성 설정 확인

DEP에서 키를 사용하기 전에 유효성 검사를 수행하는 것은 선택 사항이지만 사용하는 것이 좋습니다. 특히 이 항목에 설명된 것 이외의 다른 키 및 이전 사용자 키를 설정하는 단계를 사용하는 경우에는 고객 키를 구성하기 전에 Azure Key Vault 리소스의 상태를 확인해야 합니다.
  
키가 get, wrapKey 및 unwrapKey 작업을 사용하도록 설정되어 있는지 확인하려면
  
다음과 [같이 Get-AzKeyVault](https://docs.microsoft.com/powershell/module/az.keyvault/get-azkeyvault) cmdlet을 실행합니다.
  
```powershell
Get-AzKeyVault -VaultName <vault name>
```

출력에서 액세스 정책과 Exchange Online ID(GUID) 또는 SharePoint Online ID(GUID)가 적절하게 맞는지 확인합니다. 위의 사용 권한 모두 키에 대한 권한 아래에 표시해야 합니다.
  
액세스 정책 구성이 잘못된 경우 다음과 같이 Set-AzKeyVaultAccessPolicy cmdlet을 실행합니다.
  
```powershell
Set-AzKeyVaultAccessPolicy -VaultName <vault name> -PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName <Office 365 appID>
```

예를 들어 Exchange Online 및 비즈니스용 Skype의 경우 다음과 같습니다.
  
```powershell
Set-AzKeyVaultAccessPolicy -VaultName Contoso-O365EX-NA-VaultA1 
-PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName 00000002-0000-0ff1-ce00-000000000000
```

예를 들어 SharePoint Online 및 비즈니스용 OneDrive의 경우 다음을 수행합니다.
  
```powershell
Set-AzKeyVaultAccessPolicy -VaultName Contoso-O365SP-NA-VaultA1
-PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName 00000003-0000-0ff1-ce00-000000000000
```

키에 대해 만료 날짜가 설정되지 않도록 하려면 [다음과 같이 Get-AzKeyVaultKey](https://docs.microsoft.com/powershell/module/az.keyvault/get-azkeyvault) cmdlet을 실행합니다.
  
```powershell
Get-AzKeyVaultKey -VaultName <vault name>
```

만료된 키로 인해 고객 키와 작동이 시도된 키를 사용할 수 없는 경우 서비스가 중단될 수 있습니다. 고객 키와 함께 사용되는 키에 만료 날짜는 없는 것이 좋습니다. 설정되면 만료 날짜를 제거할 수 없지만 다른 날짜로 변경할 수 있습니다. 만료 날짜를 설정한 키를 사용하려면 만료 값을 12/31/9999로 변경합니다. 만료 날짜가 만료 날짜가 9999년 12월 31일이 아니면 Microsoft 365 유효성 검사를 통과하지 못합니다.
  
만료 날짜를 12/31/9999 이외의 값으로 변경하려면 [다음과 같이 Update-AzKeyVaultKey](https://docs.microsoft.com/powershell/module/az.keyvault/update-azkeyvaultkey) cmdlet을 실행합니다.
  
```powershell
Update-AzKeyVaultKey -VaultName <vault name> -Name <key name> -Expires (Get-Date -Date "12/31/9999")
```

> [!CAUTION]
> 고객 키와 함께 사용하는 암호화 키의 만료 날짜를 설정하지 마세요.
  
### <a name="obtain-the-uri-for-each-azure-key-vault-key"></a>각 Azure Key Vault 키의 URI 가져오기

Azure의 모든 단계를 완료하여 키 변경과 키 추가를 마치면 다음 명령을 실행하여 각 키 모음에서 키의 URI를 가져오십시오. 각 DEP를 나중에 만들고 할당할 때 이러한 URI를 사용하므로 해당 정보를 안전한 장소에 저장해야 합니다. 각 키 모음에 대해 이 명령을 한 번 실행해야 합니다.
  
Azure PowerShell에서:
  
```powershell
(Get-AzKeyVaultKey -VaultName <vault name>).Id
```

## <a name="office-365-setting-up-customer-key-for-exchange-online-and-skype-for-business"></a>Office 365: Exchange Online 및 비즈니스용 Skype에 대한 고객 키 설정

시작하기 전에 Azure Key Vault를 설정하는 데 필요한 작업을 완료해야 합니다. 자세한 [내용은 Azure Key Vault 및 Microsoft FastTrack의 전체 작업을](#complete-tasks-in-azure-key-vault-and-microsoft-fasttrack-for-customer-key) 참조하세요.
  
Exchange Online 및 비즈니스용 Skype에 사용할 고객 키를 설정하려면 Exchange Online에 원격으로 연결하여 조직을 지원하고 다음 단계를 Windows PowerShell.
  
### <a name="create-a-data-encryption-policy-dep-for-use-with-exchange-online-and-skype-for-business"></a>Exchange Online 및 비즈니스용 Skype에 사용할 DEP(데이터 암호화 정책) 만들기

DEP는 Azure Key Vault에 저장된 키 집합과 연결되어 있습니다. Microsoft 365의 사서함에 DEP를 할당합니다. 그러면 Microsoft 365는 정책에 식별된 키를 사용하여 사서함을 암호화합니다. DEP를 만들려면 앞서 가온 키 Vault URI가 필요합니다. 지침은 [각 Azure Key Vault 키에 대한 URI 가져오기를](#obtain-the-uri-for-each-azure-key-vault-key) 참조하세요.
  
기한이지 기다해 주세요! DEP를 만들 때는 두 개의 다른 Azure Key Vaults에 있는 두 개의 키를 지정합니다. 이러한 키가 두 개의 개별 Azure 지역에 있는지 확인하여 지리적 중복성을 보보입니다.
  
DEP를 만들려면 다음 단계를 수행합니다.
  
1. 로컬 컴퓨터에서 조직의 전역 관리자 권한이 있는 회사 또는 학교 계정을 사용하여 다음 최소 Windows PowerShell [PowerShell에](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell) Windows PowerShell 합니다.

2. DEP를 만들려면 다음 명령을 입력하여 New-DataEncryptionPolicy cmdlet을 사용합니다.

   ```powershell
   New-DataEncryptionPolicy -Name <PolicyName> -Description "Policy Description" -AzureKeyIDs <KeyVaultURI1>, <KeyVaultURI2>
   ```

   여기서,

   - *PolicyName은* 정책에 사용할 이름입니다. 이름에는 공백을 포함할 수 없습니다. 예를 들면 USA_mailboxes.

   - *정책 설명은* 정책에 대한 설명을 기알 어떤 정책에 대한 설명입니다. 설명에 공백을 포함할 수 있습니다. 예를 들면 "미국, 지사의 사서함에 대한 루트 키".

   - *KeyVaultURI1은* 정책의 첫 번째 키에 대한 URI입니다. 예를 들면 <https://contoso_EastUSvault01.vault.azure.net/keys/USA_key_01>와 같습니다.

   - *KeyVaultURI2는* 정책의 두 번째 키에 대한 URI입니다. 예를 들면 <https://contoso_EastUS2vault01.vault.azure.net/keys/USA_Key_02>와 같습니다. 두 URI를 쉼표와 공백으로 구분합니다.

   예제:
  
   ```powershell
   New-DataEncryptionPolicy -Name USA_mailboxes -Description "Root key for mailboxes in USA and its territories" -AzureKeyIDs https://contoso_EastUSvault01.vault.azure.net/keys/USA_key_01, https://contoso_EastUS2vault01.vault.azure.net/keys/USA_Key_02
   ```

구문과 매개 변수에 대한 자세한 내용은 [New-DataEncryptionPolicy를 참조하세요.](https://docs.microsoft.com/powershell/module/exchange/new-data-encryptionpolicy)

### <a name="assign-a-dep-to-a-mailbox"></a>사서함에 DEP 할당

Set-Mailbox cmdlet을 사용하여 사서함에 DEP를 할당합니다. 정책을 할당하면 Microsoft 365에서 DEP에 지정된 키를 사용하여 사서함을 암호화할 수 있습니다.
  
```powershell
Set-Mailbox -Identity <MailboxIdParameter> -DataEncryptionPolicy <PolicyName>
```

여기서 *MailboxIdParameter는* 사서함을 지정합니다. Set-Mailbox cmdlet에 대한 자세한 내용은 [Set-Mailbox를 참조하십시오.](https://docs.microsoft.com/powershell/module/exchange/set-mailbox)

하이브리드 [최신 인증이 있는 iOS 및 Android용 Outlook을 사용하는](https://docs.microsoft.com/exchange/clients/outlook-for-ios-and-android/use-hybrid-modern-auth)온-프레미스 사서함의 경우 Exchange Online 테넌트와 동기화되는 온-프레미스 사서함 데이터에 Set-MailUser cmdlet을 사용하여 DEP를 할당할 수 있습니다.

```powershell
Set-MailUser -Identity <MailUserIdParameter> -DataEncryptionPolicy <PolicyName>
```

여기서 *MailUserIdParameter는* 메일 사용자(메일 사용이 가능한 사용자로도 알려진)를 지정합니다. Set-MailUser cmdlet에 대한 자세한 내용은 [Set-MailUser를 참조하십시오.](https://docs.microsoft.com/powershell/module/exchange/set-mailuser)
  
### <a name="validate-mailbox-encryption"></a>사서함 암호화 유효성 검사

사서함을 암호화하는 데 시간이 걸릴 수 있습니다. 처음 할당 시 사서함을 암호화하기 전에 사서함을 한 데이터베이스에서 다른 데이터베이스로 완전히 이동해야 합니다. DEP를 변경하거나 사서함에 DEP를 처음 할당한 후에 암호화의 유효성을 검사하기 전에 72시간을 기다리는 것이 좋습니다.
  
Get-MailboxStatistics cmdlet을 사용하면 사서함암호화 여부를 확인합니다.
  
```powershell
Get-MailboxStatistics -Identity <GeneralMailboxOrMailUserIdParameter> | fl IsEncrypted
```

IsEncrypted 속성은 사서함이 암호화되어 있으면 **값 true를** 반환하고, 사서함이 암호화되지 않은 경우 **False의** 값을 반환합니다.

사서함 이동을 완료하기 위한 시간은 사서함의 크기와 DEP를 처음으로 할당한 사서함 수에 따라 달라지기를 의미합니다. DEP가 할당된 시간부터 일주일 후에 사서함이 암호화되지 않은 경우 Microsoft에 문의하세요.

## <a name="office-365-setting-up-customer-key-for-sharepoint-online-onedrive-for-business-and-teams-files"></a>Office 365: SharePoint Online, 비즈니스용 OneDrive 및 Teams 파일에 대한 고객 키 설정

시작하기 전에 Azure Key Vault를 설정하는 데 필요한 작업을 완료해야 합니다. 자세한 [내용은 Azure Key Vault 및 Microsoft FastTrack의 전체 작업을](#complete-tasks-in-azure-key-vault-and-microsoft-fasttrack-for-customer-key) 참조하세요.
  
SharePoint Online, 비즈니스용 OneDrive 및 Teams 파일에 대한 고객 키를 설정하려면 SharePoint Online과 원격으로 연결하여 다음 단계를 Windows PowerShell.
  
### <a name="create-a-data-encryption-policy-dep-for-each-sharepoint-online-and-onedrive-for-business-geo"></a>각 SharePoint Online 및 비즈니스용 OneDrive 지역에 대한 DEP(데이터 암호화 정책) 만들기

Azure Key Vault에 저장된 키 집합과 DEP를 연결합니다. 단일 지리적 위치(지리적이라고도 하는)의 모든 데이터에 DEP를 적용합니다. Office 365의 Multi-Geo 기능을 사용하는 경우, 지역별로 다른 키를 사용할 수 있는 DEP를 하나 만듭니다. 다중 지역을 사용하지 않는 경우 조직에서 SharePoint Online, 비즈니스용 OneDrive 및 Teams 파일의 사용을 위해 DEP를 하나 만들 수 있습니다. Microsoft 365는 DEP에 식별된 키를 사용하여 해당 지역에서 데이터를 암호화합니다. DEP를 만들려면 앞서 가온 키 Vault URI가 필요합니다. 지침은 [각 Azure Key Vault 키에 대한 URI 가져오기를](#obtain-the-uri-for-each-azure-key-vault-key) 참조하세요.
  
기한이지 기다해 주세요! DEP를 만들 때는 두 개의 다른 Azure Key Vaults에 있는 두 개의 키를 지정합니다. 이러한 키가 두 개의 개별 Azure 지역에 있는지 확인하여 지리적 중복성을 보보입니다.
  
DEP를 만들려면 클라우드 관리 기능을 사용하여 SharePoint Online에 원격으로 Windows PowerShell.
  
1. 로컬 컴퓨터에서 조직에서 전역 관리자 권한을 가있는 회사 또는 학교 계정을 사용하여 [SharePoint Online Powershell에 연결합니다.](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps)

2. Microsoft SharePoint Online 관리 셸에서 다음과 같이 Register-SPODataEncryptionPolicy cmdlet을 실행합니다.

   ```powershell
   Register-SPODataEncryptionPolicy -Identity <SPOAdminSiteUrl> -PrimaryKeyVaultName <PrimaryKeyVaultName> -PrimaryKeyName <PrimaryKeyName> -PrimaryKeyVersion <PrimaryKeyVersion> -SecondaryKeyVaultName <SecondaryKeyVaultName> -SecondaryKeyName <SecondaryKeyName> -SecondaryKeyVersion <SecondaryKeyVersion>
   ```

   DEP를 등록하면 해당 지역의 데이터에서 암호화가 시작됩니다. 이 프로세스를 완료하려면 다소 시간이 걸릴 수 있습니다.

### <a name="validate-file-encryption"></a>파일 암호화 유효성 검사

 SharePoint Online, 비즈니스용 OneDrive 및 Teams 파일의 암호화가 유효성을 검사하려면 [SharePoint Online PowerShell에](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell?view=exchange-ps)연결한 다음 Get-SPODataEncryptionPolicy cmdlet을 사용하여 테넌트의 상태를 확인합니다. _고객 키_ 암호화가 사용하도록 **설정되었고** 모든 사이트의 파일이 암호화된 경우 State 속성은 등록된 값을 반환합니다. 암호화가 계속 진행 중인 경우 이 cmdlet은 어떤 사이트에서 완료하는지에 대한 정보를 제공합니다.

## <a name="related-articles"></a>관련 문서

- [고객 키를 사용한 서비스 암호화](customer-key-overview.md)

- [고객 키 관리](customer-key-manage.md)

- [고객 키 또는 가용성 키 롤 또는 회전](customer-key-availability-key-roll.md)

- [Availability 키에 대해 알아보기](customer-key-availability-key-understand.md)

- [서비스 암호화](office-365-service-encryption.md)
