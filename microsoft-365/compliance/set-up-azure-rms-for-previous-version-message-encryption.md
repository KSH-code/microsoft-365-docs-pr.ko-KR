---
title: 이전 버전의 메시지 암호화에 대해 Azure 권한 관리 설정
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 10/30/2018
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.localizationpriority: medium
search.appverid:
- MET150
- MOE150
ms.assetid: 2cba47b3-f09e-4911-9207-ac056fcb9db7
description: 이전 버전의 Office 365 메시지 암호화 권한 관리(Microsoft Azure 권한 관리)에 따라 Windows Azure Active Directory 있습니다.
ms.openlocfilehash: c94497069d929dd3819e3ced915c8e778e983c10
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2021
ms.locfileid: "60159607"
---
# <a name="set-up-azure-rights-management-for-the-previous-version-of-message-encryption"></a>이전 버전의 메시지 암호화에 대해 Azure 권한 관리 설정

이 항목에서는 이전 버전의 OME(Azure Information Protection)에서 사용하기 위해 Azure Information Protection의 일부인 RMS(Azure 권한 관리)를 활성화하고 설정하기 위해 따라야 하는 Office 365 메시지 암호화 설명합니다.

## <a name="this-article-only-applies-to-the-previous-version-of-ome"></a>이 문서는 이전 버전의 OME에만 적용됩니다.

아직 조직을 새 OME 기능으로 이동하지 않았지만 이미 OME를 배포한 경우 이 문서의 정보가 조직에 적용됩니다. 조직에 적절한 새 OME 기능으로 이동하는 계획을 세우는 것이 좋습니다. 자세한 내용은 [Set up new Office 365 메시지 암호화 capabilities을 참조하십시오.](set-up-new-message-encryption-capabilities.md) 새 기능이 먼저 작동되는 방식에 대한 자세한 내용은 [Office 365 메시지 암호화.](ome.md) 이 문서의 나머지부분에서는 새 OME 기능을 릴리스하기 전에 OME 동작을 참조합니다.

## <a name="prerequisites-for-using-the-previous-version-of-office-365-message-encryption"></a>이전 버전의 Office 365 메시지 암호화
<a name="warmprereqs"> </a>

Office 365 메시지 암호화(OME)는 Azure RMS(Azure 권한 관리)에 따라 달라 습니다. Azure RMS는 Azure Information Protection에서 사용하는 보호 기술입니다. OME를 사용하려면 조직에 Azure 권한 관리 구독이 Exchange Online Exchange Online Protection 구독을 포함해야 합니다.
  
- 구독에 포함된 내용에 대해 잘 모를 경우 메시지 정책, 복구 및 규정 Exchange Online 서비스 [설명을 참조하세요.](/office365/servicedescriptions/exchange-online-service-description/message-policy-and-compliance)

- Azure 권한 관리가 있지만 Exchange Online 또는 Exchange Online Protection 설정되어 있지 않은 경우 이 문서에서는 Azure 권한 관리를 활성화하는 방법을 설명한 다음 Azure 권한 관리에서 작동할 수 있는 OME를 설정하는 가장 좋은 방법에 대해 설명합니다.

- OME를 설정한 방법에 따라 Exchange Online 또는 Exchange Online Protection Azure 권한 관리에서 작동할 수 있도록 이미 OME를 설정한 경우 바로 OME 및 새 기능을 사용할 준비가 될 수 있습니다. 이 문서에서는 OME를 올바르게 설정해야 하는지, 설정을 변경해야 하는 경우 어떻게 해야 하는지, 설치를 변경하지 않을 경우 어떻게 될지 결정하는 방법에 대해 설명합니다. 예를 들어 새 기능을 사용하려면 OME와 함께 Azure RMS를 사용해야 합니다. 새 기능을 프레미스 Active Directory RMS와 함께 사용할 수 없습니다.

## <a name="activate-azure-rights-management-for--the-previous-version-of-ome-in-office-365"></a>OME의 이전 버전에 대해 Azure 권한 관리 Office 365

조직의 사용자가 보내는 메시지에 정보 보호를 적용하고 Azure 권한 관리 서비스에서 보호된 메시지와 파일을 열 수 있도록 Azure 권한 관리를 활성화해야 합니다. 자세한 내용은 Azure 권한 관리 [활성화를 참조하세요.](/azure/information-protection/activate-service) 정품 인증을 완료한 후 여기로 돌아가 이 문서의 작업을 계속 진행합니다.
  
## <a name="set-up-the-previous-version-of-ome-to-use-azure-rms-by-importing-trusted-publishing-domains-tpds"></a>신뢰할 수 있는 게시 도메인(TPD)을 가져와서 Azure RMS를 사용할 이전 버전의 OME 설정

TPD는 조직의 권한 관리 설정에 대한 정보를 포함하는 XML 파일입니다. 예를 들어 TPD에는 인증서 및 라이선스 서명 및 암호화에 사용되는 SLC(서버 라이선스 인증서), 라이선스 및 게시에 사용되는 URL에 대한 정보가 포함되어 있습니다. 조직에 TPD를 가져오는 데 사용할 수 Windows PowerShell.
  
> [!IMPORTANT]
> 이전에는 AD RMS(Active Directory Rights Management Service)에서 조직으로 TPD를 가져올 수 있습니다. 그러나 이렇게 하면 새 OME 기능을 사용할 수 없는 것이 며 권장되지 않습니다. 조직이 현재 이러한 방식으로 구성되어 있는 경우, Microsoft는 사내 Active Directory RMS에서 클라우드 기반 Azure Information Protection으로 마이그레이션할 계획을 만드는 것이 좋습니다. 자세한 내용은 [AD RMS에서 Azure Information Protection으로 마이그레이션을 참조하세요.](/information-protection/plan-design/migrate-from-ad-rms-to-azure-rms) Azure Information Protection으로의 마이그레이션을 완료해야 새 OME 기능을 사용할 수 있습니다.
  
 **Azure RMS에서 TPD를 가져오기 위해**
  
1. [커넥트 PowerShell을 Exchange Online 를 사용할 수 있습니다.](/powershell/exchange/connect-to-exchange-online-powershell)

2. 조직의 지리적 위치에 해당하는 키 공유 URL을 선택하십시오.

|**위치**|**키 공유 위치 URL**|
|:-----|:-----|
|북미  <br/> |https://sp-rms.na.aadrm.com/TenantManagement/ServicePartner.svc  <br/> |
|유럽 연합  <br/> |https://sp-rms.eu.aadrm.com/TenantManagement/ServicePartner.svc  <br/> |
|아시아  <br/> |https://sp-rms.ap.aadrm.com/TenantManagement/ServicePartner.svc  <br/> |
|남미  <br/> |https://sp-rms.sa.aadrm.com/TenantManagement/ServicePartner.svc  <br/> |
|Office 365 Government(정부 커뮤니티 클라우드)  <br/> 이 RMS 키 공유 위치는 정부 SKUS용 Office 365 구입한 고객을 위해 예약되어 있습니다.  <br/> |https://sp-rms.govus.aadrm.com/TenantManagement/ServicePartner.svc  <br/> |
  
3. 다음과 같이 [Set-IRMConfiguration](/powershell/module/exchange/set-irmconfiguration) cmdlet을 실행하여 키 공유 위치를 구성합니다. 

   ```powershell
   Set-IRMConfiguration -RMSOnlineKeySharingLocation "<RMSKeySharingURL >"
   ```
  
   예를 들어 조직이 북미에 있는 경우 키 공유 위치를 구성합니다.

   ```powershell
   Set-IRMConfiguration -RMSOnlineKeySharingLocation "https://sp-rms.na.aadrm.com/TenantManagement/ServicePartner.svc"
   ```

4. -RMSOnline 스위치를 사용하여 [Import-RMSTrustedPublishingDomain](/powershell/module/exchange/import-rmstrustedpublishingdomain) cmdlet을 실행하여 Azure 권한 관리에서 TPD를 가져올 수 있습니다. 

   ```powershell
   Import-RMSTrustedPublishingDomain -RMSOnline -Name "<TPDName> "
   ```

   여기서  *TPDName은*  TPD에 사용할 이름입니다. 예를 들면 "Contoso North American TPD"입니다. 

5. Azure 권한 관리 서비스를 사용하도록 조직을 성공적으로 구성한 경우 다음과 같이 -RMSOnline 스위치를 사용하여 [Test-IRMConfiguration](/powershell/module/exchange/test-irmconfiguration) cmdlet을 실행합니다.

   ```powershell
   Test-IRMConfiguration -RMSOnline
   ```

   무엇보다 이 cmdlet은 Azure 권한 관리 서비스에 대한 연결을 확인하고 TPD를 다운로드하고 유효성을 검사합니다.

6. [Set-IRMConfiguration](/powershell/module/exchange/set-irmconfiguration) cmdlet을 다음과 같이 실행하여 Azure 권한 관리 템플릿을 다음과 같은 웹용 Outlook 사용할 수 Outlook. 

   ```powershell
   Set-IRMConfiguration -ClientAccessServerEnabled $false
   ```

7. 다음과 같이 [Set-IRMConfiguration](/powershell/module/exchange/set-irmconfiguration) cmdlet을 실행하여 클라우드 기반 전자 메일 조직에 대해 Azure 권한 관리를 사용하도록 설정하고 Azure Rights Management를 사용하도록 구성할 수 Office 365 메시지 암호화.

   ```powershell
   Set-IRMConfiguration -InternalLicensingEnabled $true
   ```

8. TPD를 가져와 Azure 권한 관리를 사용하도록 설정한지 확인을 위해 Test-IRMConfiguration cmdlet을 사용하여 Azure 권한 관리 기능을 테스트합니다. 자세한 내용은 [Test-IRMConfiguration의](/powershell/module/exchange/test-irmconfiguration)"예제 1"을 참조합니다.

## <a name="i-have-the-previous-version-of-ome-set-up-with-active-directory-rights-management-not-azure-information-protection-what-do-i-do"></a>Azure Information Protection이 아닌 Active Directory 권한 관리로 이전 버전의 OME를 설정했습니다. 어떻게 해야 합니까?
<a name="importTPDs"> </a>

Active Directory 권한 관리에서 기존 Office 365 메시지 암호화 메일 흐름 규칙을 계속 사용할 수 있지만 새 OME 기능을 구성하거나 사용할 수 없습니다. 대신 Azure Information Protection으로 마이그레이션해야 합니다. 마이그레이션 및 조직의 의미에 대한 자세한 내용은 [Ad RMS에서 Azure Information Protection으로 마이그레이션을 참조하세요.](/information-protection/deploy-use/prepare-environment-adrms)
  
## <a name="next-steps"></a>다음 단계
<a name="importTPDs"> </a>

Azure 권한 관리 설정을 완료한 후 새 OME 기능을 사용하도록 설정하려면 Azure Information Protection을 토대하여 구축된 새 Office 365 메시지 암호화 기능 [설정을 참조하세요.](./set-up-new-message-encryption-capabilities.md)
  
조직에서 새 OME 기능을 사용할 수 있도록 설정한 후 새 OME 기능으로 전자 메일 메시지를 보호하는 메일 흐름 규칙 [정의를 사용할 준비가 된 것입니다.](define-mail-flow-rules-to-encrypt-email.md)
  
## <a name="related-topics"></a>관련 항목
<a name="importTPDs"> </a>

[Office 365의 암호화](encryption.md)
  
[Office 365의 암호화에 대한 기술 관련 세부 정보](technical-reference-details-about-encryption.md)
  
[Azure 권한 관리란?](/information-protection/understand-explore/what-is-azure-rms)