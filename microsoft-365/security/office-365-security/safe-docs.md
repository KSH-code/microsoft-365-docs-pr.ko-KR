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
ms.openlocfilehash: 47bb6c66d51575c91b829e9688a074aaf9a18ab5
ms.sourcegitcommit: a1846b1ee2e4fa397e39c1271c997fc4cf6d5619
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/09/2021
ms.locfileid: "50166654"
---
# <a name="safe-documents-in-microsoft-365-e5"></a>Microsoft 365 E5에서 안전한 문서

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**적용 대상**
- [Microsoft Defender for Office 365 요금제 2](https://go.microsoft.com/fwlink/?linkid=2148715)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

안전한 문서는 Microsoft 365 E5 또는 Microsoft 365 E5 Security의 기능으로, [끝점용 Microsoft Defender를](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) 사용하여 보호된 보기에서 연 문서 및 파일을 검사합니다. [](https://support.microsoft.com/office/d6f09ac7-e6b9-4495-8e43-2bbcdbcb6653)

## <a name="what-do-you-need-to-know-before-you-begin"></a>시작하기 전에 알아야 할 사항은 무엇인가요?

- 안전한 문서는 *Microsoft 365 E5 또는 Microsoft 365 E5* *보안* 라이선스가 있는 사용자만 사용할 수 있습니다. 이러한 라이선스는 Office 365용 Microsoft Defender 요금제에 포함되지 않습니다.

- 안전한 문서는 엔터프라이즈용 Microsoft 365 앱(이전의 Office 365 ProPlus) 버전 2004 이상에서 지원됩니다.

- <https://protection.office.com>에서 보안 및 규정 준수 센터를 엽니다. **ATP** 안전한 첨부 파일 페이지로 직접 이동하기 위해 를 을 을 <https://protection.office.com/safeattachmentv2> 니다.

- Exchange Online PowerShell에 연결하려면 [Exchange Online PowerShell에 연결](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)을 참조하세요.

- 이 문서의 절차를 수행하려면 먼저 보안 및 준수 센터에서 사용 권한을 할당받아야 합니다.
  - 안전한 문서 설정을 구성하려면 조직 관리 또는  보안 관리자 역할 그룹의 **구성원이** 되어야 합니다.
  - 안전 문서 설정에 대한 읽기 전용 액세스 권한을 사용하려면  전역 읽기 사용자 또는 보안 읽기 권한이 있는 역할 그룹의 **구성원이** 되어야 합니다.

  자세한 내용은 [보안 및 준수 센터의 사용 권한](permissions-in-the-security-and-compliance-center.md)을 참조하세요.

  > [!NOTE]
  > 
  > - Microsoft 365 관리 센터의 해당 Azure Active Directory 역할에 사용자를 추가하면 사용자에게 보안 및 준수 센터에서 필요한 권한 _및_ Microsoft 365의 다른 기능에 대한 권한이 부여됩니다. 자세한 내용은 [관리자 역할 정보](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles)를 참조하세요.
  >
  > - [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups)의 **보기 전용 조직 관리** 역할 그룹도 기능에 대한 읽기 전용 권한을 부여합니다.

### <a name="how-does-microsoft-handle-your-data"></a>Microsoft는 데이터를 어떻게 처리하나요?

보호를 유지하기 위해 안전한 문서는 분석을 위해 [Microsoft Defender for Endpoint 클라우드로](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) 파일을 전송합니다. 끝점용 Microsoft Defender가 데이터를 처리하는 방법에 대한 자세한 내용은 끝점 데이터 저장소 및 개인 정보 보호용 [Microsoft Defender에서](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy)찾을 수 있습니다.

안전한 문서에서 보낸 파일은 분석에 필요한 시간(일반적으로 24시간 미만)이 지난 시간 동안 Defender에 보존되지 않습니다.

## <a name="use-the-security--compliance-center-to-configure-safe-documents"></a>보안 및 & 센터를 사용하여 안전한 문서 구성

1. 보안 & 준수 센터에서 **위협** 관리 \>  \> **정책 ATP** 안전한 첨부 파일로 이동한 다음 전역 설정을 **클릭합니다.**

2. 전역 **설정이** 나타나면 플라이아웃에서 다음 설정을 구성합니다.

   - **Office 클라이언트에 대해** 안전한 문서 켜기: 토글을 오른쪽으로 이동하여 기능을 ![ 켜기: 토글합니다. ](../../media/scc-toggle-on.png)

   - **안전한 문서에서** 파일을 악의적인 것으로 식별한 경우에도 사용자가 보호된 보기를 클릭할 수 있도록 허용: 이 옵션을 해제(토글을 왼쪽으로 유지: 토글 해제)하는 것이 좋습니다. ![ ](../../media/scc-toggle-off.png)

   작업을 마쳤으면 **저장** 을 클릭합니다.

   ![안전한 첨부 파일 페이지에서 전역 설정을 선택한 후의 안전한 문서 설정](../../media/safe-docs.png)

### <a name="use-exchange-online-powershell-to-configure-safe-documents"></a>Exchange Online PowerShell을 사용하여 안전한 문서 구성

다음 구문을 사용합니다.

```powershell
Set-AtpPolicyForO365 -EnableSafeDocs <$true | $false> -AllowSafeDocsOpen <$true | $false>
```

- _EnableSafeDocs_ 매개 변수는 전체 조직에 대해 안전한 문서를 사용하도록 설정하거나 사용하지 않도록 합니다.
- _AllowSafeDocsOpen_ 매개 변수는 문서가 악성으로 식별된 경우 사용자가 보호된 보기(즉, 문서를 여는 경우)를 허용하거나 허용하지 않습니다.

이 예에서는 전체 조직에 대해 안전한 문서를 사용할 수 있도록 하여 사용자가 보호된 보기에서 악의적인 것으로 확인된 문서를 열지 못하게 합니다.

```powershell
Set-AtpPolicyForO365 -EnableSafeDocs $true -AllowSafeDocsOpen $false
```

구문과 매개 변수에 대한 자세한 내용은 [Set-AtpPolicyForO365를 참조하십시오.](https://docs.microsoft.com/powershell/module/exchange/set-atppolicyforo365)

### <a name="how-do-i-know-this-worked"></a>작동 여부는 어떻게 확인합니까?

안전한 문서를 사용하도록 설정하고 구성해야 하는지 확인을 위해 다음 단계를 수행합니다.

- 보안 & 준수 센터에서 **위협** 관리 \>  \> **정책 ATP**   안전한 첨부 파일로 이동하고 전역 설정을 클릭한 다음 **Office** 클라이언트에 대해 안전한 문서 켜기 기능을 확인하고 안전한 문서가 파일을 악의적인 설정으로 식별하는 경우에도 사용자가 보호된 보기를 클릭할 수 있도록 허용합니다.

- Exchange Online PowerShell에서 다음 명령을 실행하고 속성 값을 검증합니다.

  ```powershell
  Get-AtpPolicyForO365 | Format-List *SafeDocs*
  ```

- 다음 파일을 통해 안전한 문서 보호를 테스트할 수 있습니다. 이러한 문서는 맬웨어 방지 EICAR.TXT 바이러스 백신 솔루션을 테스트하기 위한 파일과 유사합니다. 파일이 해로운 것은 아니며 안전한 문서 보호를 트리거합니다.

  - [SafeDocsDemo.docx](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/SafeDocsDemo.docx)
  - [SafeDocsDemo.pptx](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/SafeDocsDemo.pptx)
  - [SafeDocsDemo.xlsx](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/SafeDocsDemo.xlsx)
