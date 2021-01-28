---
title: 응용 프로그램 수준에서 고객 키 설정
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
description: Exchange Online, 비즈니스용 Skype, SharePoint Online, 비즈니스용 OneDrive 및 Teams 파일에 대한 Microsoft 365 고객 키를 설정하는 방법을 자세히 알아보고
ms.openlocfilehash: 94702cecb37686c3996c5ed70b1810a825bb2ff6
ms.sourcegitcommit: b3bb5bf5efa197ef8b16a33401b0b4f5663d3aa0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/28/2021
ms.locfileid: "50032615"
---
# <a name="set-up-customer-key-at-the-application-level"></a>응용 프로그램 수준에서 고객 키 설정

고객 키를 사용하여 조직의 암호화 키를 제어한 다음 Microsoft 데이터 센터의 미사용 데이터를 암호화하는 데 사용하도록 Microsoft 365를 구성합니다. 즉, 고객 키를 사용하면 고객이 키로 속한 암호화 계층을 추가할 수 있습니다. 미사용 데이터에는 SharePoint Online 및 비즈니스용 OneDrive에 저장되어 있는 사서함과 파일에 저장된 Exchange Online 및 비즈니스용 Skype의 데이터를 포함합니다.

Office 365에 대한 고객 키를 사용하려면 먼저 Azure를 설정해야 합니다. 이 문서에서는 필요한 Azure 리소스를 만들고 구성하기 위해 따라야 하는 단계에 대해 설명한 다음 Office 365에서 고객 키를 설정하기 위한 단계를 제공합니다. Azure 설치를 완료한 후 조직의 사서함 및 파일에 할당할 정책 및 키를 결정할 수 있습니다. 정책을 할당하지 않는 사서함 및 파일은 Microsoft에서 제어 및 관리하는 암호화 정책을 사용합니다. 고객 키에 대한 자세한 내용은 [Office 365의 고객](customer-key-overview.md)키를 사용하여 서비스 암호화를 참조하세요.
  
> [!IMPORTANT]
> 이 문서의 모범 사례를 따르는 것이 좋습니다. 이러한 호출은 **TIP** 및 **IMPORTANT로 호출합니다.** 고객 키를 사용하면 전체 조직만큼 범위가 될 수 있는 루트 암호화 키를 제어할 수 있습니다. 즉, 이러한 키로 실수하면 광범위한 영향을 미칠 수 있으며 서비스가 중단되거나 데이터가 취소되지 않을 수 있습니다.
  
## <a name="before-you-set-up-customer-key"></a>고객 키를 설정하기 전에

시작하기 전에 조직에 적합한 라이선싱이 준비해야 합니다. 클라우드 서비스 공급자 또는 클라우드 서비스 공급자를 사용하여 기업계약 송장된 Azure 구독을 사용합니다. 결제 플랜 또는 신용 카드를 사용하여 구입한 Azure 구독은 고객 키에 지원되지 않습니다. 2020년 4월 1일부터 Office 365의 고객 키는 Office 365 E5, M365 E5, M365 E5 규정 준수 및 M365 E5 정보 보호 & 관리 SKUS에서 제공됩니다. Office 365 Advanced Compliance SKU는 더 이상 새 라이선스를 조달할 수 없습니다. 기존 Office 365 고급 준수 라이선스는 계속 지원됩니다.

이 문서의 개념과 절차를 이해하기 위해 [Azure Key Vault 설명서를 검토하세요.](https://docs.microsoft.com/azure/key-vault/) 또한 Azure에서 사용되는 용어(예: Azure [AD 테넌트)에 익숙해지겠습니다.](https://docs.microsoft.com/previous-versions/azure/azure-services/jj573650(v=azure.100)#what-is-an-azure-ad-tenant)

FastTrack은 고객 키를 등록하는 데 사용되는 필요한 테넌트 및 서비스 구성 정보를 수집하는 데만 사용됩니다. 고객 주요 제품은 FastTrack을 통해 게시됩니다. 따라서 사용자와 파트너가 동일한 방법을 사용하여 필요한 정보를 제출할 수 있습니다. FastTrack을 사용하면 제품에서 제공하는 데이터를 쉽게 보관할 수 있습니다.
  
설명서 이외에 더 많은 지원이 필요한 경우 MCS(Microsoft Consulting Services), PFE(프리미어 필드 엔지니어링) 또는 Microsoft 파트너에게 지원을 요청하세요. 설명서를 포함하여 고객 키에 대한 피드백을 제공하기 위해 사용자 의견, 제안 및 관점을 customerkeyfeedback@microsoft.com.
  
## <a name="overview-of-steps-to-set-up-customer-key"></a>고객 키 설정 단계 개요

고객 키를 설정하기 위해 나열된 순서대로 이러한 작업을 완료합니다. 이 문서의 나머지에서는 각 작업에 대한 자세한 지침을 제공하거나 프로세스의 각 단계에 대한 추가 정보로 연결되는 링크를 제공합니다.
  
**Azure 및 Microsoft FastTrack에서:**
  
Azure PowerShell에 원격으로 연결하여 이러한 대부분의 작업을 완료합니다. 최상의 결과를 얻기 위해 Azure PowerShell 버전 4.4.0 이상을 사용하세요.
  
- [새 Azure 구독 2개 만들기](#create-two-new-azure-subscriptions)

- [필수 보존 기간을 사용하기 위해 Azure 구독 등록](#register-azure-subscriptions-to-use-a-mandatory-retention-period)

  등록에는 영업일 1~5일이 걸릴 수 있습니다.

- [Office 365에 대한 고객 키 정품 인증 요청 제출](#submit-a-request-to-activate-customer-key-for-office-365)

두 개의 새 Azure 구독을 만든 후 Microsoft FastTrack 포털에서 호스팅되는 웹 양식을 완료하여 적절한 고객 키 제품 요청을 제출해야 합니다. **FastTrack 팀은 고객 키에 대한 지원을 제공하지 않습니다. Office는 단순히 FastTrack** 포털을 사용하여 양식을 제출하고 고객 키에 대한 관련 제안을 추적하는 데 도움이 됩니다.

- [각 구독에서 프리미엄 Azure Key Vault 만들기](#create-a-premium-azure-key-vault-in-each-subscription)

- [각 키 자격 증명 모음에 사용 권한 할당](#assign-permissions-to-each-key-vault)

- [키 자격 증명 모음에서 소프트 삭제를 사용하도록 설정한 다음 확인](#enable-and-then-confirm-soft-delete-on-your-key-vaults)

- [키를 만들거나 가져와서 각 키 자격 증명 모음에 키 추가](#add-a-key-to-each-key-vault-either-by-creating-or-importing-a-key)

- [키의 복구 수준 확인](#check-the-recovery-level-of-your-keys)

- [Azure Key Vault 백업](#back-up-azure-key-vault)

- [Azure Key Vault 구성 설정 유효성 검사](#validate-azure-key-vault-configuration-settings)

- [각 Azure Key Vault 키에 대한 URI 획득](#obtain-the-uri-for-each-azure-key-vault-key)

**Office 365에서:**
  
Exchange Online 및 비즈니스용 Skype:
  
- [Exchange Online 및 비즈니스용 Skype에서 사용할 DEP(데이터 암호화 정책) 만들기](#create-a-data-encryption-policy-dep-for-use-with-exchange-online-and-skype-for-business)

- [사서함에 DEP 할당](#assign-a-dep-to-a-mailbox)

- [사서함 암호화 유효성 검사](#validate-mailbox-encryption)

SharePoint Online 및 비즈니스용 OneDrive:
  
- [각 SharePoint Online 및 비즈니스용 OneDrive 지리적 데이터에 대한 DEP(데이터 암호화 정책) 만들기](#create-a-data-encryption-policy-dep-for-each-sharepoint-online-and-onedrive-for-business-geo)

- [SharePoint Online, 비즈니스용 OneDrive 및 Teams 파일에 대한 파일 암호화 유효성 검사](#validate-file-encryption)

## <a name="complete-tasks-in-azure-key-vault-and-microsoft-fasttrack-for-customer-key"></a>Azure Key Vault 및 고객 키에 대한 Microsoft FastTrack의 작업 완료

Azure Key Vault에서 이러한 작업을 완료합니다. Exchange Online 및 비즈니스용 Skype 또는 SharePoint Online, 비즈니스용 OneDrive 및 Teams 파일 또는 Office 365에서 지원되는 모든 서비스에 대해 고객 키를 설정하려는지 여부에 관계없이 이러한 단계를 완료해야 합니다.
  
### <a name="create-two-new-azure-subscriptions"></a>새 Azure 구독 2개 만들기

고객 키에는 두 개의 Azure 구독이 필요합니다. 모범 사례로, 고객 키와 함께 사용할 새 Azure 구독을 만드는 것이 좋습니다. Azure Key Vault 키는 동일한 Azure Active Directory(Microsoft Azure Active Directory) 테넌트의 응용 프로그램에만 권한을 부여할 수 있으며, DEP가 할당될 조직에서 사용되는 동일한 Azure AD 테넌트를 사용하여 새 구독을 만들어야 합니다. 예를 들어 조직에서 전역 관리자 권한이 있는 직장 또는 학교 계정을 사용할 수 있습니다. 자세한 단계는 [조직으로 Azure에 등록을 참조하세요.](https://azure.microsoft.com/documentation/articles/sign-up-organization/)
  
> [!IMPORTANT]
> 고객 키에는 각 DEP(데이터 암호화 정책)에 대해 두 개의 키가 필요합니다. 이를 위해 Azure 구독을 두 개 만들어야 합니다. 조직의 개별 구성원이 각 구독에서 하나의 키를 구성하는 것이 좋습니다. 이러한 Azure 구독만 사용하여 Office 365의 암호화 키를 관리해야 합니다. 이렇게 하여 운영자 중 한 명이 실수로 의도적으로 또는 악의적으로 삭제하거나 책임이 있는 키를 잘못 관리한 경우 조직을 보호합니다.
>

조직에 대해 만들 수 있는 Azure 구독 수에는 실질적으로 제한이 없습니다. 이러한 모범 사례를 따라 사용자 오류의 영향을 최소화하면서 고객 키에서 사용하는 리소스를 관리할 수 있습니다.
  
### <a name="submit-a-request-to-activate-customer-key-for-office-365"></a>Office 365에 대한 고객 키 정품 인증 요청 제출

Azure 단계를 완료한 후 Microsoft FastTrack 포털에서 제안 요청을 [제출해야 합니다.](https://fasttrack.microsoft.com/) FastTrack 웹 포털을 통해 요청을 제출하면 Microsoft는 Azure Key Vault 구성 데이터 및 사용자가 제공한 연락처 정보를 검증합니다. 제안 양식에서 조직의 공인 책임자에 대한 선택은 고객 키 등록을 완료하는 데 중요하고 필요합니다. 조직의 담당자는 고객 키 데이터 암호화 정책에 사용되는 모든 키를 해지하고 삭제하기 위한 모든 요청의 진위를 보장합니다. Exchange Online 및 비즈니스용 Skype에 대한 고객 키를 활성화하려면 이 단계를 한 번, 두 번째로 SharePoint Online 및 비즈니스용 OneDrive에 대한 고객 키를 활성화해야 합니다.
  
고객 키를 활성화하기 위한 제안을 제출하려면 다음 단계를 완료합니다.
  
1. 조직에서 전역 관리자 권한이 있는 직장 또는 학교 계정을 사용하여 [Microsoft FastTrack](https://fasttrack.microsoft.com/)포털에 로그인합니다.

2. 로그인한 후 대시보드를 **검색합니다.**

3. 탐색 **모음에서** 배포를  선택하거나 정보 카드  배포에서 모든 배포 리소스 보기를 선택하고 현재 혜택 목록을 검토합니다. 

4. 다음에 적용되는 제품 정보 카드를 선택하세요.

   - **Exchange Online 및 비즈니스용 Skype:** Exchange Online **제품용 암호화 키 요청 도움말을** 선택하세요.

   - **SharePoint Online, OneDrive 및 Teams 파일:** **Sharepoint 및 OneDrive** 제품용 요청 암호화 키 도움말을 선택하세요.

5. 제품 세부 정보를 검토한 후 **2단계를 계속합니다.**

6. 제품 양식에 적용 가능한 모든 세부 정보와 요청된 정보를 입력합니다. 조직의 임원들이 암호화 키와 데이터의 영구적이지 않을 수 없는 파기 승인을 승인할 수 있는 선택에 특히 주의해야 합니다. 양식을 완료한 후 제출을 **선택하십시오.**

### <a name="register-azure-subscriptions-to-use-a-mandatory-retention-period"></a>필수 보존 기간을 사용하기 위해 Azure 구독 등록

루트 암호화 키의 일시적 또는 영구적 손실은 서비스 작업에 지장이나 심지어는 비극적일 수 있으며 데이터가 손실될 수 있습니다. 이러한 이유로 고객 키와 함께 사용되는 리소스에는 강력한 보호가 필요합니다. 고객 키와 함께 사용되는 모든 Azure 리소스는 기본 구성을 넘어 보호 메커니즘을 제공합니다. 필수 보존 기간 동안 Azure 구독에 태그를 지정하거나 *등록할 수 있습니다.* 필수 보존 기간은 Azure 구독의 즉시 취소 및 취소를 방지합니다. 필수 보존 기간 동안 Azure 구독을 등록하는 데 필요한 단계는 Microsoft 365 팀과 공동 작업해야 합니다. 이 프로세스는 영업일 1~5일이 걸릴 수 있습니다. 이전에는 필수 보존 기간을 "취소 금지"라고도 합니다.
  
Microsoft 365 팀에 문의하기 전에 고객 키와 함께 사용하는 각 Azure 구독에 대해 다음 단계를 수행해야 합니다. 시작하기 전에 [Azure PowerShell Az](https://docs.microsoft.com/powershell/azure/new-azureps-module-az) 모듈을 설치해야 합니다.
  
1. Azure PowerShell로 로그인합니다. 자세한 내용은 [Azure PowerShell로 로그인을 참조하세요.](https://docs.microsoft.com/powershell/azure/authenticate-azureps)

2. Register-AzProviderFeature cmdlet을 실행하여 필수 보존 기간을 사용하기 위해 구독을 등록합니다. 각 구독에 대해 이 작업을 완료합니다.

   ```powershell
   Set-AzContext -SubscriptionId <SubscriptionId>
   Register-AzProviderFeature -FeatureName mandatoryRetentionPeriodEnabled -ProviderNamespace Microsoft.Resources
   ```

3. 프로세스를 완료하기 위해 Microsoft에 문의합니다. SharePoint 및 비즈니스용 OneDrive 팀에 문의할 수 [spock@microsoft.com.](mailto:spock@microsoft.com) Exchange Online 및 비즈니스용 Skype의 경우 에지 [exock@microsoft.com.](mailto:exock@microsoft.com) 전자 메일에 다음 정보를 포함하세요.

   **제목:** 고객 키 \<*Your tenant's fully qualified domain name*\>

   **본문:** 필수 보존 기간을 완료할 구독 Get-AzProviderFeature 각 구독에 대한 출력을 포함합니다.

   이 프로세스 완료를 위한 SLA(서비스 수준 계약)는 Microsoft가 필수 보존 기간을 사용하기 위해 구독을 등록했다는 알림을(확인)한 후 영업일 5일입니다.

4. Microsoft로부터 등록이 완료된다는 알림을 받으면 다음과 같이 Get-AzProviderFeature 등록 상태를 확인하면 됩니다. 확인된 Get-AzProviderFeature 명령은 등록 상태 속성에 **대해 Registered** 값을 **반환합니다.** 각 구독에 대해 이 단계를 완료합니다.

   ```powershell
   Set-AzContext -SubscriptionId <SubscriptionId>
   Get-AzProviderFeature -ProviderNamespace Microsoft.Resources -FeatureName mandatoryRetentionPeriodEnabled
   ```

5. 프로세스를 완료하기 위해 Register-AzResourceProvider 실행합니다. 각 구독에 대해 이 단계를 완료합니다.

   ```powershell
   Set-AzContext -SubscriptionId <SubscriptionId>
   Register-AzResourceProvider -ProviderNamespace Microsoft.KeyVault
   ```

### <a name="create-a-premium-azure-key-vault-in-each-subscription"></a>각 구독에서 프리미엄 Azure Key Vault 만들기

키 자격 증명 모음을 만드는 단계는 Azure PowerShell 설치 및 시작, Azure 구독 연결, 리소스 그룹 만들기 및 해당 리소스 그룹에서 키 자격 증명 모음 만들기를 안내하는 [Azure Key Vault](https://azure.microsoft.com/documentation/articles/key-vault-get-started/)시작에 설명되어 있습니다.
  
키 자격 증명 모음을 만들 때 SKU(Standard 또는 Premium)를 선택해야 합니다. Standard SKU를 사용하면 Azure Key Vault 키를 소프트웨어로 보호할 수 있습니다. HSM(하드웨어 보안 모듈) 키 보호가 없습니다. Premium SKU는 키 자격 증명 모음 키를 보호하기 위해 HSM을 사용할 수 있습니다. Customer Key는 SKU 중 하나를 사용하는 주요 자격 증명 모음을 수락합니다. 그러나 Microsoft는 Premium SKU만 사용하는 것이 좋습니다. 두 유형의 키 중 하나를 사용하는 작업의 비용은 동일하기 때문에 비용의 유일한 차이는 각 HSM으로 보호되는 키에 대한 월별 비용입니다. 자세한 [내용은 Key Vault 가격을](https://azure.microsoft.com/pricing/details/key-vault/) 참조합니다.
  
> [!IMPORTANT]
> 프로덕션 데이터에는 Premium SKU 키 자격 증명 모음 및 HSM으로 보호된 키를 사용하며 테스트 및 유효성 검사를 위해 표준 SKU 키 자격 증명 모음 및 키만 사용하십시오.
  
고객 키를 사용할 각 Microsoft 365 서비스에 대해 만든 두 Azure 구독 각각에 키 자격 증명 모음을 생성합니다. 예를 들어 Exchange Online 및 비즈니스용 Skype만 또는 SharePoint Online 및 비즈니스용 OneDrive의 경우 한 쌍의 자격 증명 모음만 만들 수 있습니다. Exchange Online 및 SharePoint Online 둘 다에 대해 고객 키를 사용하도록 설정하려면 두 쌍의 키 자격 증명 모음을 생성합니다.
  
자격 증명 모음을 연결하려는 DEP의 의도된 사용을 반영하는 주요 자격 증명 모음에 대한 이름 규칙 사용 이름 규칙 권장 사항은 아래의 모범 사례 섹션을 참조하세요.
  
각 데이터 암호화 정책에 대해 쌍으로 구분된 자격 증명 모음 집합을 만들 수 있습니다. Exchange Online의 경우 사서함에 정책을 할당할 때 데이터 암호화 정책의 범위가 선택됩니다. 사서함에는 정책이 하나만 할당될 수 있으며 최대 50개 정책을 만들 수 있습니다. SharePoint Online 정책의 범위에는 지리적 위치 또는 지리적 위치에 있는 조직 내의 모든 데이터가 _포함됩니다._

키 자격 증명 모음을 만들려면 Azure 리소스 그룹을 만들어야 합니다. 키 자격 증명 모음에는 저장 용량(작은 용량)이 필요하고 키 자격 증명 모음 로깅이 필요한 경우 저장된 데이터도 생성됩니다. 최상의 방법은 별도의 관리자를 사용하여 각 리소스 그룹을 관리하고 모든 관련 고객 키 리소스를 관리할 관리자 집합과 연계된 관리를 사용하는 것이 좋습니다.
  
> [!IMPORTANT]
> 가용성을 최대화하기 위해 주요 자격 증명 모음은 Microsoft 365 서비스에 가까운 지역에 있습니다. 예를 들어 Exchange Online 조직이 북미에 있는 경우 주요 자격 증명 모음을 북미에 저장합니다. Exchange Online 조직이 유럽에 있는 경우 주요 자격 증명 모음을 유럽에 두는 것이 좋습니다.
> 
> 키 자격 증명 모음에 대해 공통된 도우미를 사용하며 키 자격 증명 모음 및 키의 사용 및 범위 약어를 포함합니다(예: 자격 증명 모음이 북미에 있는 Contoso SharePoint 서비스의 경우 가능한 이름 쌍은 Contoso-O365SP-NA-VaultA1 및 Contoso-O365SP-NA-VaultA2)입니다. 자격 증명 모음 이름은 Azure 내에서 전역적으로 고유한 문자열이기 때문에 다른 Azure 고객이 원하는 이름을 이미 요구하는 경우 원하는 이름의 변형을 시도해야 할 수 있습니다. 2017년 7월 현재 자격 증명 모음 이름은 변경할 수 없습니다. 따라서 설치 계획을 서면으로 작성하고 두 번째 사람을 사용하여 계획이 올바르게 실행되고 있는지 확인하는 것이 가장 좋습니다.
> 
> 가능한 경우 페어링되지 않은 지역에서 자격 증명 모음을 만드십시오. 페어링된 Azure 지역은 서비스 오류 도메인 전체에서 고가용성을 제공합니다. 따라서 지역 쌍은 서로의 백업 지역으로 생각할 수 있습니다. 즉, 한 지역에 배치된 Azure 리소스가 페어링된 지역을 통해 내결결성을 자동으로 얻게 됩니다. 이러한 이유로 지역이 페어링된 데이터 암호화 정책에서 사용되는 두 자격 증명 모음에 대한 지역을 선택하면 총 두 개의 가용성 영역만 사용 중입니다. 대부분의 지역에는 두 개의 지역만 있으므로 페어링되지 않은 지역을 선택할 수 없습니다. 가능한 경우 데이터 암호화 정책과 함께 사용되는 두 자격 증명 모음에 대해 쌍으로 설정되지 않은 두 지역을 선택하십시오. 이 혜택은 총 네 가지 가용성 영역의 이점입니다. 자세한 내용은 [BCDR(비즈니스](https://docs.microsoft.com/azure/best-practices-availability-paired-regions) 연속성 및 재해 복구): 현재 지역 쌍 목록은 Azure 페어링된 지역을 참조하세요.
  
### <a name="assign-permissions-to-each-key-vault"></a>각 키 자격 증명 모음에 사용 권한 할당

구현에 따라 각 키 자격 증명 모음에 대해 세 가지 개별 권한 집합을 정의해야 합니다. 예를 들어 다음 각 권한 집합에 대해 하나의 사용 권한 집합을 정의해야 합니다.
  
- **조직의 키** 자격 증명 모음을 매일 관리하기 위한 주요 자격 증명 모음 관리자 이러한 작업에는 백업, 만들기, 가져오기, 가져오기, 목록 및 복원이 포함됩니다.

  > [!IMPORTANT]
  > 키 자격 증명 모음 관리자에게 할당된 권한 집합에는 키 삭제 권한이 포함되어 있지 않습니다. 이는 의도적인 것이고 중요한 사례입니다. 암호화 키를 삭제하는 작업은 일반적으로 수행되지 않습니다. 이렇게 하면 데이터가 영구적으로 삭제됩니다. 이 권한은 기본적으로 주요 자격 증명 모음 관리자에게 부여하지 않는 것이 가장 좋습니다. 대신 주요 자격 증명 모음 참가자에 대해 이 정보를 예약하고 결과에 대한 명확한 이해가 있는 경우 단기적으로 관리자에게만 할당합니다.
  
  조직의 사용자에게 이러한 권한을 할당하려면 Azure PowerShell을 사용하여 Azure 구독에 로그인합니다. 자세한 내용은 [Azure PowerShell로 로그인을 참조하세요.](https://docs.microsoft.com/powershell/azure/authenticate-azureps)

- Set-AzKeyVaultAccessPolicy cmdlet을 실행하여 필요한 사용 권한을 할당합니다.

   ```powershell
   Set-AzKeyVaultAccessPolicy -VaultName <vault name> -UserPrincipalName <UPN of user> -PermissionsToKeys create,import,list,get,backup,restore
   ```

   예제:

   ```powershell
   Set-AzKeyVaultAccessPolicy -VaultName Contoso-O365EX-NA-VaultA1 -UserPrincipalName alice@contoso.com -PermissionsToKeys create,import,list,get,backup,restore
   ```

- Azure **Key Vault** 자체에 대한 사용 권한을 변경할 수 있는 주요 자격 증명 모음 참가자입니다. 직원이 팀을 떠나거나 팀에 합류할 때 이러한 사용 권한을 변경해야 합니다. 드물지만 키 자격 증명 모음 관리자에게 키를 삭제하거나 복원할 수 있는 권한이 합법적으로 필요한 경우도 사용 권한을 변경해야 합니다. 주요 자격 증명 모음 참가자 집합은  키 자격 증명 모음에 대한 참가자 역할을 부여해야 합니다. Azure Resource Manager를 사용하여 이 역할을 할당할 수 있습니다. 자세한 단계는 Role-Based 액세스 제어를 사용하여 Azure 구독 리소스에 [대한 액세스를 관리합니다.](https://docs.microsoft.com/azure/active-directory/role-based-access-control-configure) 구독을 만드는 관리자는 이 액세스 권한을 암시적으로 사용할 수 있으며 참가자 역할에 다른 관리자를 할당할 수 있습니다.

- Exchange Online 및 비즈니스용 Skype와 함께 고객 키를 사용하려는 경우 Exchange Online 및 비즈니스용 Skype 대신 키 자격 증명 모음을 사용할 수 있는 권한을 Microsoft 365에 부여해야 합니다. 마찬가지로, SharePoint Online 및 비즈니스용 OneDrive에서 고객 키를 사용하려는 경우 SharePoint Online 및 비즈니스용 OneDrive 대신 키 자격 증명 모음을 사용할 수 있는 Microsoft 365에 대한 권한을 추가해야 합니다. Microsoft 365에 대한 사용 권한을 부여하려면 다음 구문을 사용하여 **Set-AzKeyVaultAccessPolicy** cmdlet을 실행합니다.

   ```powershell
   Set-AzKeyVaultAccessPolicy -VaultName <vault name> -PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName <Office 365 appID>
   ```

   여기서,

    - *자격 증명* 모음 이름은 만든 키 자격 증명 모음의 이름입니다.

    - Exchange Online 및 비즈니스용 Skype의 경우 *Office 365 appID를*`00000002-0000-0ff1-ce00-000000000000`

    - SharePoint Online, 비즈니스용 OneDrive 및 Teams 파일의 경우 *Office 365 appID를*`00000003-0000-0ff1-ce00-000000000000`

  예: Exchange Online 및 비즈니스용 Skype에 대한 사용 권한 설정:

   ```powershell
   Set-AzKeyVaultAccessPolicy -VaultName Contoso-O365EX-NA-VaultA1 -PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName 00000002-0000-0ff1-ce00-000000000000
   ```

  예: SharePoint Online, 비즈니스용 OneDrive 및 Teams 파일에 대한 사용 권한 설정:

   ```powershell
   Set-AzKeyVaultAccessPolicy -VaultName Contoso-O365SP-NA-VaultA1 -PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName 00000003-0000-0ff1-ce00-000000000000
   ```

### <a name="enable-and-then-confirm-soft-delete-on-your-key-vaults"></a>키 자격 증명 모음에서 소프트 삭제를 사용하도록 설정한 다음 확인

키를 빠르게 복구할 수 있는 경우 실수로 또는 악의적으로 삭제된 키로 인해 확장된 서비스가 사용되지 않습니다. 고객 키와 함께 키를 사용하려면 먼저 소프트 삭제라고 하는 이 구성을 사용하도록 설정해야 합니다. 소프트 삭제를 사용하도록 설정하면 삭제 후 90일 이내에 키나 자격 증명 모음을 백업에서 복원하지 않고도 복구할 수 있습니다.
  
키 자격 증명 모음에서 소프트 삭제를 사용하도록 설정하려면 다음 단계를 완료합니다.
  
1. Azure 구독에 로그인하여 Windows PowerShell. 자세한 내용은 [Azure PowerShell로 로그인을 참조하세요.](https://docs.microsoft.com/powershell/azure/authenticate-azureps)

2. [Get-AzKeyVault](https://docs.microsoft.com/powershell/module/az.keyvault/get-azkeyvault) cmdlet을 실행합니다. 이 예에서 *자격* 증명 모음 이름은 소프트 삭제를 사용하도록 설정하는 키 자격 증명 모음의 이름입니다.

   ```powershell
   $v = Get-AzKeyVault -VaultName <vault name>
   $r = Get-AzResource -ResourceId $v.ResourceId
   $r.Properties | Add-Member -MemberType NoteProperty -Name enableSoftDelete -Value 'True'
   Set-AzResource -ResourceId $r.ResourceId -Properties $r.Properties
   ```

3. **Get-AzKeyVault** cmdlet을 실행하여 키 자격 증명 모음에 대해 소프트 삭제가 구성되어 있는지 확인 키 자격 증명 모음에 대해 소프트 삭제가 제대로 구성되어 있는 경우 _Soft Delete Enabled_ 속성은 True 값을 **반환합니다.**

   ```powershell
   Get-AzKeyVault -VaultName <vault name> | fl
   ```

### <a name="add-a-key-to-each-key-vault-either-by-creating-or-importing-a-key"></a>키를 만들거나 가져와서 각 키 자격 증명 모음에 키 추가

Azure Key Vault에 키를 추가하는 방법에는 두 가지가 있습니다. 키 자격 증명 모음에서 직접 키를 만들거나 키를 가져올 수 있습니다. 키 자격 증명 모음에서 직접 키를 만드는 것은 덜 복잡하지만 키를 가져오면 키 생성 방법을 완전히 제어할 수 있습니다. RSA 키를 사용 합니다. Azure Key Vault는 타원형 곡선 키로 래핑 및 래핑을 지원하지 않습니다.
  
키 자격 증명 모음에서 직접 키를 만들 수 있도록 [Add-AzKeyVaultKey](https://docs.microsoft.com/powershell/module/az.keyvault/add-azkeyvaultkey) cmdlet을 다음과 같이 실행합니다.
  
```powershell
Add-AzKeyVaultKey -VaultName <vault name> -Name <key name> -Destination <HSM|Software> -KeyOps wrapKey,unwrapKey
```

여기서,

- *자격 증명* 모음 이름은 키를 만들 키 자격 증명 모음의 이름입니다.

- *키 이름은* 새 키를 지정하려는 이름입니다.

  > [!TIP]
  > 키 자격 증명에 대해 위에서 설명한 대로 유사한 명명 규칙을 사용하여 키의 이름을 지정합니다. 이렇게 하면 키 이름만 표시하는 도구에서 문자열이 자체 설명을 합니다.
  
HSM을 사용하여 키를 보호하려는 경우 **HSM을** _Destination_ 매개 변수 값으로 지정해야 합니다. 그렇지 않으면 **Software를 지정합니다.**

예를 들면 다음과 같습니다.
  
```powershell
Add-AzKeyVaultKey -VaultName Contoso-O365EX-NA-VaultA1 -Name Contoso-O365EX-NA-VaultA1-Key001 -Destination HSM -KeyOps wrapKey,unwrapKey
```

키를 키 자격 증명 모음으로 직접 가져오기 위해 nCipher nShield 하드웨어 보안 모듈이 필요합니다.
  
일부 조직에서는 키의 검증을 설정하기 위해 이 방법을 선호하며, 이 방법을 통해 다음 증명도 제공합니다.
  
- 가져오기에 사용되는 도구et에는 생성한 키를 암호화하는 데 사용되는 KEK(키 Exchange 키)를 내보낼 수 없는 것으로 nCipher에서 제작한 정품 HSM 내에서 생성되었다는 것을 nCipher의 의증이 포함되어 있습니다.

- 이 도구 모음에는 nCipher에서 Azure Key Vault 보안 월드가 nCipher에서 제조한 정품 HSM에서도 생성되었다는 증명이 포함되어 있습니다. 이 증명은 Microsoft가 정품 nCipher 하드웨어도 사용하고 있는 것을 증명합니다.

보안 그룹에 확인하여 위의 의거가 필요한지 여부를 판단합니다. Azure Key Vault에 대한 [HSM으로](https://azure.microsoft.com/documentation/articles/key-vault-hsm-protected-keys/)보호된 키를 생성하고 전송하는 방법을 참조하세요. Azure 지침을 사용하여 각 키 자격 증명 모음에 키를 만들 수 있습니다.
  
### <a name="check-the-recovery-level-of-your-keys"></a>키의 복구 수준 확인

Microsoft 365를 사용하려면 Azure Key Vault 구독이 Do Not Cancel으로 설정되고 고객 키에서 사용하는 키가 소프트 삭제를 사용하도록 설정되어 있습니다. 키의 복구 수준을 확인하여 구독 설정을 확인할 수 있습니다.
  
키의 복구 수준을 확인하면 Azure PowerShell에서 다음과 Get-AzKeyVaultKey cmdlet을 실행합니다.
  
```powershell
(Get-AzKeyVaultKey -VaultName <vault name> -Name <key name>).Attributes
```

Recovery _Level_ 속성이 **Recoverable+ProtectedSubscription** 값 외의 값을 반환하는 경우 구독을 취소 금지 목록에 추가하고 각 키 자격 증명 모음에서 소프트 삭제를 사용하도록 설정해야 합니다.
  
### <a name="back-up-azure-key-vault"></a>Azure Key Vault 백업

키를 만들거나 변경한 직후 온라인과 오프라인에서 백업을 수행하고 백업 복사본을 저장합니다. 오프라인 복사본은 물리적 안전 또는 상업용 저장소 시설과 같은 네트워크에 연결되어 있지 않습니다. 재해 발생 시 액세스할 수 있는 위치에 백업 복사본을 하나 이상 저장해야 합니다. 키 자격 증명 모음 키를 영구적으로 삭제하거나 그렇지 않으면 사용할 수 없는 경우 백업 Blob은 키 자료를 복원하는 유일한 수단입니다. Azure Key Vault 외부에서 Azure Key Vault로 가져온 키는 고객 키에 필요한 메타데이터가 외부 키와 함께 존재하지 않습니다. Azure Key Vault에서 사용한 백업만 고객 키를 사용하여 복원 작업에 사용할 수 있습니다. 따라서 키를 업로드하거나 만든 후 Azure Key Vault의 백업을 만들어야 합니다.
  
Azure Key Vault 키의 백업을 만들 경우 다음과 같이 [Backup-AzKeyVaultKey](https://docs.microsoft.com/powershell/module/az.keyvault/backup-azkeyvaultkey) cmdlet을 실행합니다.

```powershell
Backup-AzKeyVaultKey -VaultName <vault name> -Name <key name>
-OutputFile <filename.backup>
```

출력 파일에 접미사가 사용되도록 `.backup` 합니다.
  
이 cmdlet에서 생성되는 출력 파일은 암호화되며 Azure Key Vault 외부에서는 사용할 수 없습니다. 백업은 백업을 수행한 Azure 구독으로만 복원할 수 있습니다.
  
> [!TIP]
> 출력 파일의 경우 자격 증명 모음 이름과 키 이름을 조합하여 선택하십시오. 이렇게 하면 파일 이름이 자체 설명으로 지정됩니다. 또한 백업 파일 이름이 충돌하지 않도록 합니다.
  
예제:
  
```powershell
Backup-AzKeyVaultKey -VaultName Contoso-O365EX-NA-VaultA1 -Name Contoso-O365EX-NA-VaultA1-Key001 -OutputFile Contoso-O365EX-NA-VaultA1-Key001-Backup-20170802.backup
```

### <a name="validate-azure-key-vault-configuration-settings"></a>Azure Key Vault 구성 설정 유효성 검사

DEP에서 키를 사용하기 전에 유효성을 검사하는 것은 선택 사항이지만 매우 권장됩니다. 단계에 따라 이 문서에 설명된 키와 자격 증명 모음을 설정하는 경우 고객 키를 구성하기 전에 Azure Key Vault 리소스의 상태의 유효성을 검사합니다.
  
키에 사용 가능한 및 작업이 `get` `wrapKey` `unwrapKey` 활성화되어 있는지 확인:
  
[Get-AzKeyVault](https://docs.microsoft.com/powershell/module/az.keyvault/get-azkeyvault) cmdlet을 다음과 같이 실행합니다.
  
```powershell
Get-AzKeyVault -VaultName <vault name>
```

출력에서 액세스 정책과 Exchange Online ID(GUID) 또는 SharePoint Online ID(GUID)를 적절하게 찾아 봐야 합니다. 위의 세 사용 권한은 모두 키에 대한 사용 권한 아래에 표시되어야 합니다.
  
액세스 정책 구성이 올바르지 않은 경우 다음과 Set-AzKeyVaultAccessPolicy cmdlet을 실행합니다.
  
```powershell
Set-AzKeyVaultAccessPolicy -VaultName <vault name> -PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName <Office 365 appID>
```

예를 들어 Exchange Online 및 비즈니스용 Skype의 경우:
  
```powershell
Set-AzKeyVaultAccessPolicy -VaultName Contoso-O365EX-NA-VaultA1 
-PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName 00000002-0000-0ff1-ce00-000000000000
```

예를 들어 SharePoint Online 및 비즈니스용 OneDrive의 경우:
  
```powershell
Set-AzKeyVaultAccessPolicy -VaultName Contoso-O365SP-NA-VaultA1
-PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName 00000003-0000-0ff1-ce00-000000000000
```

키에 대한 만료 날짜가 설정되어 있지 않은지 확인하기 위해 다음과 같이 [Get-AzKeyVaultKey](https://docs.microsoft.com/powershell/module/az.keyvault/get-azkeyvault) cmdlet을 실행합니다.
  
```powershell
Get-AzKeyVaultKey -VaultName <vault name>
```

고객 키는 만료된 키를 사용할 수 없습니다. 만료된 키로 시도한 작업이 실패하고 서비스 작동이 종료될 수 있습니다. 고객 키와 함께 사용되는 키에는 만료 날짜가 없는 것이 좋습니다. 일단 설정된 만료 날짜는 제거할 수 없지만 다른 날짜로 변경할 수 있습니다. 만료 날짜가 설정된 키를 사용하려면 만료 값을 9999년 12월 31일로 변경합니다. 만료 날짜가 9999년 12월 31일이 아닌 날짜로 설정된 키는 Microsoft 365 유효성 검사를 통과하지 못합니다.
  
9999년 12월 31일이 아니라 다른 값으로 설정된 만료 날짜를 변경하기 위해 다음과 같이 [Update-AzKeyVaultKey](https://docs.microsoft.com/powershell/module/az.keyvault/update-azkeyvaultkey) cmdlet을 실행합니다.
  
```powershell
Update-AzKeyVaultKey -VaultName <vault name> -Name <key name> -Expires (Get-Date -Date "12/31/9999")
```

> [!CAUTION]
> 고객 키와 함께 사용하는 암호화 키에 만료 날짜를 설정하지 않습니다.
  
### <a name="obtain-the-uri-for-each-azure-key-vault-key"></a>각 Azure Key Vault 키에 대한 URI 획득

키 자격 증명 모음을 설정하고 키를 추가한 후 다음 명령을 실행하여 각 키 자격 증명 모음의 키에 대한 URI를 얻습니다. 나중에 각 DEP를 만들고 할당할 때 이러한 URIS를 사용하여 이 정보를 안전한 장소에 저장해야 합니다. 각 키 자격 증명 모음에 대해 이 명령을 한 번 실행합니다.
  
Azure PowerShell에서:
  
```powershell
(Get-AzKeyVaultKey -VaultName <vault name>).Id
```

## <a name="office-365-setting-up-customer-key-for-exchange-online-and-skype-for-business"></a>Office 365: Exchange Online 및 비즈니스용 Skype에 대한 고객 키 설정

시작하기 전에 Azure Key Vault를 설정하는 데 필요한 작업을 완료해야 합니다. 자세한 [내용은 Azure Key Vault 및 고객 키에 대한 Microsoft FastTrack의 전체 작업을](#complete-tasks-in-azure-key-vault-and-microsoft-fasttrack-for-customer-key) 참조하세요.
  
Exchange Online 및 비즈니스용 Skype에 대한 고객 키를 설정하기 위해 Exchange Online에 원격으로 연결하여 이 단계를 Windows PowerShell.
  
### <a name="create-a-data-encryption-policy-dep-for-use-with-exchange-online-and-skype-for-business"></a>Exchange Online 및 비즈니스용 Skype에서 사용할 DEP(데이터 암호화 정책) 만들기

DEP는 Azure Key Vault에 저장된 키 집합과 연결됩니다. Microsoft 365의 사서함에 DEP를 할당합니다. 그런 다음 Microsoft 365는 정책에 식별된 키를 사용하여 사서함을 암호화합니다. DEP를 만들하려면 앞서 획득한 키 자격 증명 모음 UR이 필요합니다. 지침은 [각 Azure Key Vault 키에](#obtain-the-uri-for-each-azure-key-vault-key) 대한 URI 획득을 참조하세요.
  
기억하세요! DEP를 만들 때 두 개의 서로 다른 Azure Key Vault에 두 개의 키를 지정합니다. 두 개의 별도 Azure 지역에서 이러한 키를 만들어 지리적 중복을 보장합니다.
  
DEP를 만들 수 있는 단계는 다음과 같습니다.
  
1. 로컬 컴퓨터에서 조직의 전역 관리자 권한이 있는 직장 또는 학교 계정을 사용하여 Exchange [Online PowerShell에](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell) Windows PowerShell 창에 연결합니다.

2. DEP를 만들 New-DataEncryptionPolicy 명령을 입력하여 이 cmdlet을 사용 합니다.

   ```powershell
   New-DataEncryptionPolicy -Name <PolicyName> -Description "Policy Description" -AzureKeyIDs <KeyVaultURI1>, <KeyVaultURI2>
   ```

   여기서,

   - *PolicyName은* 정책에 사용할 이름입니다. 이름에는 공백을 포함할 수 없습니다. 예를 들어 USA_mailboxes.

   - *정책 설명은* 정책의 내용 기억에 도움이 되는 정책에 대한 사용자에게 친숙한 설명입니다. 설명에 공백을 포함할 수 있습니다. 예를 들어 "미국의 사서함과 해당 지역의 루트 키"를 예로 들 수 있습니다.

   - *KeyVaultURI1은* 정책의 첫 번째 키에 대한 URI입니다. 예를 들면 <https://contoso_EastUSvault01.vault.azure.net/keys/USA_key_01>와 같습니다.

   - *KeyVaultURI2는* 정책의 두 번째 키에 대한 URI입니다. 예를 들면 <https://contoso_EastUS2vault01.vault.azure.net/keys/USA_Key_02>와 같습니다. 2개의 URIS를 COMMA와 공백으로 구분합니다.

   예제:
  
   ```powershell
   New-DataEncryptionPolicy -Name USA_mailboxes -Description "Root key for mailboxes in USA and its territories" -AzureKeyIDs https://contoso_EastUSvault01.vault.azure.net/keys/USA_key_01, https://contoso_EastUS2vault01.vault.azure.net/keys/USA_Key_02
   ```

구문과 매개 변수에 대한 자세한 내용은 [New-DataEncryptionPolicy를 참조하십시오.](https://docs.microsoft.com/powershell/module/exchange/new-data-encryptionpolicy)

### <a name="assign-a-dep-to-a-mailbox"></a>사서함에 DEP 할당

이 cmdlet을 사용하여 사서함에 DEP를 Set-Mailbox 합니다. 정책을 할당하면 Microsoft 365는 DEP에 식별된 키로 사서함을 암호화할 수 있습니다.
  
```powershell
Set-Mailbox -Identity <MailboxIdParameter> -DataEncryptionPolicy <PolicyName>
```

여기서 *MailboxIdParameter는* 사용자 사서함을 지정합니다. 이 cmdlet에 대한 Set-Mailbox [Set-Mailbox를 참조하십시오.](https://docs.microsoft.com/powershell/module/exchange/set-mailbox)

하이브리드 환경에서는 Exchange Online 테넌트에 동기화되는 DEP를 Exchange Online 사서함 데이터에 할당할 수 있습니다. 이 동기화된 사서함 데이터에 DEP를 할당하기 위해 이 cmdlet을 Set-MailUser 합니다. 하이브리드 환경의 사서함 데이터에 대한 자세한 내용은 하이브리드 최신 인증을 사용하는 iOS 및 [Android용 Outlook을 사용하는 On-premises 사서함을 참조하세요.](https://docs.microsoft.com/exchange/clients/outlook-for-ios-and-android/use-hybrid-modern-auth)

```powershell
Set-MailUser -Identity <MailUserIdParameter> -DataEncryptionPolicy <PolicyName>
```

여기서 *MailUserIdParameter는* 메일 사용자(메일 사용이 가능한 사용자라고도 합니다)를 지정합니다. 이 cmdlet에 대한 Set-MailUser [Set-MailUser를 참조하십시오.](https://docs.microsoft.com/powershell/module/exchange/set-mailuser)
  
### <a name="validate-mailbox-encryption"></a>사서함 암호화 유효성 검사

사서함 암호화에는 시간이 걸릴 수 있습니다. 최초 정책 할당의 경우 서비스에서 사서함을 암호화하기 전에 사서함도 데이터베이스에서 다른 데이터베이스로 완전히 이동해야 합니다. DEP를 변경하거나 사서함에 DEP를 처음 할당할 때 암호화 유효성을 검사하기 전에 72시간을 기다리는 것이 좋습니다.
  
이 Get-MailboxStatistics cmdlet을 사용하여 사서함이 암호화되어 있는지 확인할 수 있습니다.
  
```powershell
Get-MailboxStatistics -Identity <GeneralMailboxOrMailUserIdParameter> | fl IsEncrypted
```

사서함이 암호화된 경우 IsEncrypted 속성은 **true** 값을 반환하고 사서함이 암호화되지 않은 경우 **false** 값을 반환합니다. 사서함 이동을 완료하는 시간은 처음으로 DEP를 할당하는 사서함의 수와 사서함의 크기에 따라 달라 니다. DEP를 할당한 후 1주일 후에 사서함이 암호화되지 않은 경우 Microsoft에 문의하십시오.

## <a name="office-365-setting-up-customer-key-for-sharepoint-online-onedrive-for-business-and-teams-files"></a>Office 365: SharePoint Online, 비즈니스용 OneDrive 및 Teams 파일의 고객 키 설정

시작하기 전에 Azure Key Vault를 설정하는 데 필요한 작업을 완료해야 합니다. 자세한 [내용은 Azure Key Vault 및 고객 키에 대한 Microsoft FastTrack의 전체 작업을](#complete-tasks-in-azure-key-vault-and-microsoft-fasttrack-for-customer-key) 참조하세요.
  
SharePoint Online, 비즈니스용 OneDrive 및 Teams 파일에 대한 고객 키를 설정하려면 SharePoint Online에 원격으로 연결하여 이러한 단계를 Windows PowerShell.
  
### <a name="create-a-data-encryption-policy-dep-for-each-sharepoint-online-and-onedrive-for-business-geo"></a>각 SharePoint Online 및 비즈니스용 OneDrive 지리적 데이터에 대한 DEP(데이터 암호화 정책) 만들기

DEP를 Azure Key Vault에 저장된 키 집합과 연결합니다. 지역이라고도 하는 한 지리적 위치에 있는 모든 데이터에 DEP를 적용합니다. Office 365의 Multi-Geo 기능을 사용하는 경우 지역마다 다른 키를 사용할 수 있는 기능을 사용하여 지역당 DEP를 하나씩 만들 수 있습니다. Multi-Geo를 사용하지 않는 경우 조직에서 SharePoint Online, 비즈니스용 OneDrive 및 Teams 파일에서 사용할 DEP를 하나 만들 수 있습니다. Microsoft 365는 DEP에서 식별된 키를 사용하여 지리적으로 데이터를 암호화합니다. DEP를 만들하려면 앞서 획득한 키 자격 증명 모음 UR이 필요합니다. 지침은 [각 Azure Key Vault 키에](#obtain-the-uri-for-each-azure-key-vault-key) 대한 URI 획득을 참조하세요.
  
기억하세요! DEP를 만들 때 두 개의 서로 다른 Azure Key Vault에 두 개의 키를 지정합니다. 두 개의 별도 Azure 지역에서 이러한 키를 만들어 지리적 중복을 보장합니다.
  
DEP를 만들 수 있도록 원격으로 SharePoint Online에 연결해야 Windows PowerShell.
  
1. 로컬 컴퓨터에서 조직의 전역 관리자 권한이 있는 직장 또는 학교 계정을 사용하여 [SharePoint Online PowerShell에 연결합니다.](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps&preserve-view=true)

2. Microsoft SharePoint Online 관리 셸에서 다음과 Register-SPODataEncryptionPolicy cmdlet을 실행합니다.

   ```powershell
   Register-SPODataEncryptionPolicy -Identity <adminSiteCollectionURL> -PrimaryKeyVaultName <PrimaryKeyVaultName> -PrimaryKeyName <PrimaryKeyName> -PrimaryKeyVersion <PrimaryKeyVersion> -SecondaryKeyVaultName <SecondaryKeyVaultName> -SecondaryKeyName <SecondaryKeyName> -SecondaryKeyVersion <SecondaryKeyVersion>
   ```

   예제:
  
   ```powershell
   Register-SPODataEncryptionPolicy -Identity https://contoso.sharepoint.com -PrimaryKeyVaultName 'stageRG3vault' -PrimaryKeyName 'SPKey3' -PrimaryKeyVersion 'f635a23bd4a44b9996ff6aadd88d42ba' -SecondaryKeyVaultName 'stageRG5vault' -SecondaryKeyName 'SPKey5' -SecondaryKeyVersion '2b3e8f1d754f438dacdec1f0945f251a’
   ```

   DEP를 등록하면 지리적 데이터에 대한 암호화가 시작됩니다. 암호화에는 시간이 걸릴 수 있습니다. 이 매개 변수 사용에 대한 자세한 내용은 [Register-SPODataEncryptionPolicy를 참조하세요.](https://docs.microsoft.com/powershell/module/sharepoint-online/register-spodataencryptionpolicy?view=sharepoint-ps&preserve-view=true)

### <a name="validate-file-encryption"></a>파일 암호화 유효성 검사

 SharePoint Online, 비즈니스용 OneDrive 및 Teams 파일의 암호화 유효성을 검사하려면 [SharePoint Online PowerShell에](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)연결한 다음 Get-SPODataEncryptionPolicy cmdlet을 사용하여 테넌트의 상태를 검사합니다. 고객 키 암호화를 사용하도록  설정하고 모든 사이트의 모든 파일이 암호화된 경우 _State_ 속성은 등록된 값을 반환합니다. 암호화가 아직 진행 중이면 이 cmdlet은 완료된 사이트의 백분율에 대한 정보를 제공합니다.

## <a name="related-articles"></a>관련 문서

- [고객 키를 사용한 서비스 암호화](customer-key-overview.md)

- [고객 키 관리](customer-key-manage.md)

- [고객 키 또는 가용성 키 롤 또는 회전](customer-key-availability-key-roll.md)

- [가용성 키에 대해 자세히](customer-key-availability-key-understand.md)

- [서비스 암호화](office-365-service-encryption.md)
