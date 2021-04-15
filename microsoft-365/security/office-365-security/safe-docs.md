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
description: Microsoft 365 E5 또는 Microsoft 365 E5 보안의 안전한 문서에 대해 자세히 알아보습니다.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 1186c7856d0b979c483cf6dd1c0a010ab582e2ce
ms.sourcegitcommit: 437bdbf3f99610869811e80432a59b5f244f7a87
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2021
ms.locfileid: "51644755"
---
# <a name="safe-documents-in-microsoft-365-e5"></a>Microsoft 365 E5에서 안전한 문서

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**적용 대상**
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

안전한 문서는 끝점용 [Microsoft Defender를](/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) 사용하여 Office용 보호된 보기 또는 Application Guard에서 열 수 있는 문서 및 [](https://support.microsoft.com/office/d6f09ac7-e6b9-4495-8e43-2bbcdbcb6653) 파일을 검사하는 Microsoft 365 E5 또는 Microsoft 365 E5 보안의 [기능입니다.](https://support.microsoft.com/topic/9e0fb9c2-ffad-43bf-8ba3-78f785fdba46)

## <a name="what-do-you-need-to-know-before-you-begin"></a>시작하기 전에 알아야 할 사항은 무엇인가요?

- 안전한 문서는 *Microsoft 365 E5 또는 Microsoft 365 E5* *보안* 라이선스가 있는 사용자만 사용할 수 있습니다. 이러한 라이선스는 Microsoft Defender for Office 365 계획에 포함되어 있지 않습니다.

- 안전한 문서는 엔터프라이즈용 Microsoft 365 앱(이전의 Office 365 ProPlus) 버전 2004 이상에서 지원됩니다.

- <https://protection.office.com>에서 보안 및 준수 센터를 엽니다. ATP 안전한 첨부 파일 페이지로 직접 **이동하기** 위해 를 를 니다. <https://protection.office.com/safeattachmentv2>

- Exchange Online PowerShell에 연결하려면 [Exchange Online PowerShell에 연결](/powershell/exchange/connect-to-exchange-online-powershell)을 참조하세요.

- 이 게시물의 절차를 수행하려면 먼저 **Exchange Online** 에서 사용 권한을 할당받아야 합니다.
  - 안전한 문서 설정을 구성하려면 조직 관리 또는  보안 관리자 역할 그룹의 **구성원이** 되어야 합니다.
  - 안전 문서 설정에 대한 읽기 전용 액세스의 경우 전역  읽기 사용자 또는 보안 읽기 권한이 있는 역할 그룹의 **구성원이** 되어야 합니다.

  자세한 내용은 [Exchange Online의 사용 권한](/exchange/permissions-exo/permissions-exo)을 참조하세요.

  > [!NOTE]
  >
  > - Microsoft 365 관리 센터의 해당 Azure Active Directory 역할에 사용자를 추가하면 사용자에게 필요한 권한 _및_ Microsoft 365의 다른 기능에 대한 권한이 부여됩니다. 자세한 내용은 [관리자 역할 정보](../../admin/add-users/about-admin-roles.md)를 참조하세요.
  >
  > - [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups)의 **보기 전용 조직 관리** 역할 그룹에도 기능에 대한 읽기 전용 권한을 부여합니다.

### <a name="how-does-microsoft-handle-your-data"></a>Microsoft는 데이터를 어떻게 처리하나요?

보호를 유지하기 위해 안전한 문서는 분석을 위해 [Microsoft Defender for Endpoint 클라우드로](/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) 파일을 전송합니다. 끝점용 Microsoft Defender가 데이터를 처리하는 방법에 대한 자세한 내용은 Endpoint 데이터 저장소 및 개인 정보 [보호용 Microsoft Defender에서](/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy)찾을 수 있습니다.

안전한 문서에서 보낸 파일은 분석에 필요한 시간(일반적으로 24시간 미만)이 지난 시간 동안 Defender에 보존되지 않습니다.

## <a name="use-the-security--compliance-center-to-configure-safe-documents"></a>보안 및 & 센터를 사용하여 안전한 문서 구성

1. 보안 & 준수 센터에서 위협  관리 정책 \>  \> **ATP 안전한** 첨부 파일로 이동한 다음 전역 설정을 **클릭합니다.**

2. 전역 **설정** 플라이아웃이 나타나면 다음 설정을 구성합니다.

   - **Office 클라이언트에 대한** 안전한 문서 켜기 : 토글을 오른쪽으로 이동하여 기능을 ![ 켜기: 토글합니다. ](../../media/scc-toggle-on.png)

   - **안전한 문서에서** 파일을 악성으로 식별하는 경우에도 사용자가 보호된 보기를 클릭할 수 있도록 허용 : 이 옵션을 해제한 후(토글을 왼쪽으로 유지: 토글 해제) 하는 것이 ![ 좋습니다. ](../../media/scc-toggle-off.png)

   작업을 마쳤으면 **저장** 을 클릭합니다.

   ![안전한 첨부 파일 페이지에서 전역 설정을 선택한 후의 안전한 문서 설정입니다.](../../media/safe-docs.png)

### <a name="use-exchange-online-powershell-to-configure-safe-documents"></a>Exchange Online PowerShell을 사용하여 안전한 문서 구성

다음 구문을 사용합니다.

```powershell
Set-AtpPolicyForO365 -EnableSafeDocs <$true | $false> -AllowSafeDocsOpen <$true | $false>
```

- _EnableSafeDocs 매개_ 변수는 전체 조직에 대해 안전한 문서를 사용하도록 설정하거나 사용하지 않도록 합니다.
- _AllowSafeDocsOpen_ 매개 변수는 문서가 악의적인 것으로 확인된 경우 사용자가 보호된 보기(즉, 문서를 여는 경우)를 허용하거나 허용하지 않습니다.

이 예에서는 전체 조직에 대해 안전한 문서를 사용할 수 있도록 하여 사용자가 보호된 보기에서 악의적인 것으로 확인된 문서를 열지 못하게 합니다.

```powershell
Set-AtpPolicyForO365 -EnableSafeDocs $true -AllowSafeDocsOpen $false
```

구문과 매개 변수에 대한 자세한 내용은 [Set-AtpPolicyForO365를 참조하십시오.](/powershell/module/exchange/set-atppolicyforo365)

### <a name="onboard-to-the-microsoft-defender-for-endpoint-service-to-enable-auditing-capabilities"></a>감사 기능을 사용하도록 설정하기 위해 끝점 서비스용 Microsoft Defender에 온보딩

끝점용 Microsoft Defender를 배포하려면 다양한 배포 단계를 거치야 합니다. 온보드 후 보안 및 준수 센터에서 감사 기능을 & 수 있습니다.

자세한 내용은 [끝점 서비스용 Microsoft Defender에 온보딩을 참조합니다.](/microsoft-365/security/defender-endpoint/onboarding) 추가 도움이 필요한 경우 끝점 온보딩 문제에 [대한 Microsoft Defender 문제 해결을 참조하시기 바랍니다.](/microsoft-365/security/defender-endpoint/troubleshoot-onboarding)

### <a name="how-do-i-know-this-worked"></a>작동 여부는 어떻게 확인합니까?

안전한 문서를 사용하도록 설정하고 구성하는지 확인하기 위해 다음 단계를 수행합니다.

- 보안 & 준수 센터에서 위협  관리 정책 \>  \> **ATP 안전한**   첨부 파일로 이동하고, 전역 설정을 클릭하고, **안전한** 문서가 파일을 악의적인 설정으로 식별하는 경우에도 사용자가 보호된 보기를 클릭할 수 있도록 허용을 확인합니다.

- Exchange Online PowerShell에서 다음 명령을 실행하고 속성 값을 검증합니다.

  ```powershell
  Get-AtpPolicyForO365 | Format-List *SafeDocs*
  ```

- 다음 파일을 통해 안전한 문서 보호를 테스트할 수 있습니다. 이러한 문서는 맬웨어 방지 EICAR.TXT 바이러스 백신 솔루션을 테스트하기 위한 파일과 유사합니다. 파일이 해로운 것은 아니며 안전한 문서 보호를 트리거합니다.

  - [SafeDocsDemo.docx](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/SafeDocsDemo.docx)
  - [SafeDocsDemo.pptx](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/SafeDocsDemo.pptx)
  - [SafeDocsDemo.xlsx](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/SafeDocsDemo.xlsx)
