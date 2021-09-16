---
title: Office 365용 Microsoft Defender의 안전 문서
ms.author: chrisda
author: chrisda
manager: dansimp
ms.reviewer: kshi
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: ''
ms.collection:
- M365-security-compliance
description: 금고 문서 또는 Microsoft 365 E5 문서에 대해 Microsoft 365 E5 Security.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 74b01872a1b5aee75730f203fec9b2b0ebf77fdc
ms.sourcegitcommit: 4740e69326eb7f8302eec7bab5bd516d498e4492
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/16/2021
ms.locfileid: "59400909"
---
# <a name="safe-documents-in-microsoft-365-e5"></a>Microsoft 365 E5에서 안전한 문서

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**적용 대상**
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

금고 문서는 [끝점용 Microsoft Defender의](/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) 클라우드 백 엔드를 사용하여 에 대해 보호된 보기 또는 Application Guard에서 연 Office 문서를 스캔하는 고급 [Office.](https://support.microsoft.com/topic/9e0fb9c2-ffad-43bf-8ba3-78f785fdba46) [](https://support.microsoft.com/office/d6f09ac7-e6b9-4495-8e43-2bbcdbcb6653)

사용자는 문서 보호를 위해 로컬 장치에 Endpoint용 Defender가 금고 없습니다. 사용자는 금고 요구 사항이 모두 충족되는 경우 문서 보호를 사용할 수 있습니다.

- 금고 문서는 이 문서에 설명된 바와 같이 조직에서 사용하도록 설정됩니다.
- 필수 라이선스 계획의 라이선스가 사용자에게 할당됩니다. 금고 문서는 Office 365 **SafeDocs(또는** **SAFEDOCS** 또는 **bf6f5520-59e3-4f82-974b-7dbbc4fd27c7)** 서비스 계획(서비스라고도 알려)에 의해 제어됩니다. 이 서비스 계획은 다음 라이선싱 계획(라이선스 계획, Microsoft 365 또는 제품)에서 사용할 수 있습니다.
  - Microsoft 365 A5 교직원용 교육
  - Microsoft 365 A5 학생용 지원
  - Microsoft 365 E5
  - Microsoft 365 E5 Security

  금고 Microsoft Defender for Office 365 문서가 포함되어 있지 않습니다.

  자세한 내용은 라이선스에 대한 제품 이름 및 [서비스 계획 식별자를 참조하세요.](/azure/active-directory/enterprise-users/licensing-service-plan-reference)

- 이러한 버전은 엔터프라이즈용 Microsoft 365 앱(Office 365 ProPlus) 버전 2004 이상을 사용하고 있습니다.

## <a name="what-do-you-need-to-know-before-you-begin"></a>시작하기 전에 알아야 할 내용은 무엇인가요?

- <https://security.microsoft.com>에서 Microsoft 365 Defender 포털을 엽니다. 첨부 파일 **페이지로** 직접 금고 를 <https://security.microsoft.com/safeattachmentv2> 사용하세요.

- Exchange Online PowerShell에 연결하려면 [Exchange Online PowerShell에 연결](/powershell/exchange/connect-to-exchange-online-powershell)을 참조하세요.

- 이 문서의 절차를 **Exchange Online** 수행하려면 먼저 사용 권한이 필요합니다.
  - 문서 금고 구성하려면 조직 관리 또는 보안 관리자 역할  그룹의 **구성원이** 되어야 합니다.
  - 문서 설정에 금고 읽기 전용으로 액세스하려면 전역 읽기 그룹 또는  보안 읽기 읽기 권한이 있는 역할 그룹의 **구성원이** 되어야 합니다.

  자세한 내용은 [Exchange Online의 사용 권한](/exchange/permissions-exo/permissions-exo)을 참조하세요.

  > [!NOTE]
  >
  > - Microsoft 365 관리 센터의 해당 Azure Active Directory 역할에 사용자를 추가하면 사용자에게 필요한 권한 _및_ Microsoft 365의 다른 기능에 대한 권한이 부여됩니다. 자세한 내용은 [관리자 역할 정보](../../admin/add-users/about-admin-roles.md)를 참조하세요.
  >
  > - [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups)의 **보기 전용 조직 관리** 역할 그룹도 기능에 대한 읽기 전용 권한을 부여합니다.

### <a name="how-does-microsoft-handle-your-data"></a>Microsoft는 데이터를 어떻게 처리하나요?

보호를 유지하기 위해 금고 문서를 분석하기 위해 [Microsoft Defender for Endpoint](/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) 클라우드로 파일을 전송합니다. 끝점용 Microsoft Defender가 데이터를 처리하는 방법에 대한 자세한 내용은 Endpoint 데이터 저장소 및 개인 정보 [보호용 Microsoft Defender에서](/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy)찾을 수 있습니다.

금고 전송된 파일은 분석에 필요한 시간(일반적으로 24시간 미만)이 지난 시간 동안 Defender에 보존되지 않습니다.

## <a name="use-the-microsoft-365-defender-portal-to-configure-safe-documents"></a>Microsoft 365 Defender 포털을 사용하여 금고 구성

1. Microsoft 365 Defender 포털을 열고 정책 섹션의 **전자** 메일 & 공동 작업 정책& 규칙 위협 금고 정책으로 \>  \>  \>  이동하십시오. 

2. 첨부 **금고 페이지에서** 전역 설정을 **클릭합니다.**

3. 전역 **설정** 플라이아웃이 나타나면 다음 설정을 구성합니다.
   - **금고 클라이언트에** 대한 Office 설정 : 토글을 오른쪽으로 이동하여 기능을 ![ 켜기: 토글합니다. ](../../media/scc-toggle-on.png) .
   - **사용자가 파일을** 악성으로 식별한 경우에도 금고 보기를 클릭할 수 있도록 허용 : 이 옵션을 해제한 후(토글을 왼쪽으로 그대로 두기: ![ 토글 해제). ](../../media/scc-toggle-off.png)

   작업을 마친 후 **저장** 을 클릭합니다.

   ![금고 첨부 파일 페이지에서 전역 설정을 선택한 금고 문서화합니다.](../../media/safe-docs-global-settings.png)

### <a name="use-exchange-online-powershell-to-configure-safe-documents"></a>PowerShell Exchange Online 사용하여 문서 금고 구성

PowerShell을 사용하여 문서를 구성하는 금고 PowerShell에서 다음 구문을 Exchange Online 합니다.

```powershell
Set-AtpPolicyForO365 -EnableSafeDocs <$true | $false> -AllowSafeDocsOpen <$true | $false>
```

- _EnableSafeDocs_ 매개 변수는 전체 조직에 대해 금고 또는 사용하지 않도록 설정합니다.
- _AllowSafeDocsOpen_ 매개 변수는 문서가 악의적인 것으로 확인된 경우 사용자가 보호된 보기(즉, 문서를 여는 경우)를 허용하거나 허용하지 않습니다.

이 예에서는 금고 문서에 대해 문서를 저장하고 사용자가 보호된 보기에서 악의적인 것으로 확인된 문서를 열지 못하게 합니다.

```powershell
Set-AtpPolicyForO365 -EnableSafeDocs $true -AllowSafeDocsOpen $false
```

구문과 매개 변수에 대한 자세한 내용은 [Set-AtpPolicyForO365를 참조하십시오.](/powershell/module/exchange/set-atppolicyforo365)

### <a name="configure-individual-access-to-safe-documents"></a>문서에 대한 금고 구성

금고 기능에 대한 액세스를 선택적으로 허용하거나 차단하려면 다음 단계를 수행합니다.

1. 이 문서의 금고 설명한 Microsoft 365 Defender PowerShell에서 Exchange Online PowerShell에서 문서 편집을 하게 합니다.
2. Azure AD PowerShell을 사용하여 Disable specific Microsoft 365 services for specific users [for a specific licensing plan에](/microsoft-365/enterprise/disable-access-to-services-with-microsoft-365-powershell#disable-specific-microsoft-365-services-for-specific-users-for-a-specific-licensing-plan)설명된 바와 같이 특정 사용자에 대해 금고 문서를 사용하지 않도록 설정합니다.

  PowerShell에서 사용하지 않도록 설정할 서비스 계획의 이름은 **SAFEDOCS입니다.**

자세한 내용은 아래 항목을 참조하세요.

- [PowerShell을 Microsoft 365 라이선스 및 서비스 보기](/microsoft-365/enterprise/view-licenses-and-services-with-microsoft-365-powershell)
- [PowerShell을 Microsoft 365 계정 라이선스 및 서비스 세부 정보 보기](/microsoft-365/enterprise/view-account-license-and-service-details-with-microsoft-365-powershell)
- [라이선스에 대한 제품 이름 및 서비스 계획 식별자](/azure/active-directory/enterprise-users/licensing-service-plan-reference)

### <a name="onboard-to-the-microsoft-defender-for-endpoint-service-to-enable-auditing-capabilities"></a>감사 기능을 사용하도록 설정하기 위해 끝점용 Microsoft Defender 서비스에 온보딩

감사 기능을 사용하려면 로컬 장치에 끝점용 Microsoft Defender가 설치되어야 합니다. 끝점용 Microsoft Defender를 배포하려면 다양한 배포 단계를 거치야 합니다. 온보드 후 사이트 포털에서 감사 기능을 구성할 Microsoft 365 Defender 있습니다.

자세한 내용은 [끝점 서비스용 Microsoft Defender에 온보딩을 참조합니다.](/microsoft-365/security/defender-endpoint/onboarding) 추가 도움이 필요한 경우 Endpoint 온보딩 문제에 [대한 Microsoft Defender 문제 해결을 참조합니다.](/microsoft-365/security/defender-endpoint/troubleshoot-onboarding)

### <a name="how-do-i-know-this-worked"></a>작동 여부는 어떻게 확인합니까?

문서를 사용하도록 설정하고 구성한 금고 다음 단계를 수행합니다.

- Microsoft 365 Defender 포털의 정책 섹션 전역 설정에서 전자 메일 & 공동 **작업** 정책 & 규칙 위협 \>  \>  \> **정책금고**  \>    첨부 파일로 이동하고, Office 클라이언트에 대해 금고 문서 켜기 및 문서가 파일을 악성 설정으로 식별하는 경우에도 금고 보기를 클릭할 수 있도록 허용을 확인합니다.

- PowerShell에서 Exchange Online 명령을 실행하고 속성 값을 검증합니다.

  ```powershell
  Get-AtpPolicyForO365 | Format-List *SafeDocs*
  ```

- 다음 파일은 문서 보호를 테스트하는 금고 있습니다. 이러한 파일은 맬웨어 방지 EICAR.TXT 바이러스 백신 솔루션을 테스트하기 위한 파일과 유사합니다. 파일은 해로운 파일은 아니며 문서 보호를 금고 트리거합니다.

  - [SafeDocsDemo.docx](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/SafeDocsDemo.docx)
  - [SafeDocsDemo.pptx](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/SafeDocsDemo.pptx)
  - [SafeDocsDemo.xlsx](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/SafeDocsDemo.xlsx)
